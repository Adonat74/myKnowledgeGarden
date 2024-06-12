# Le SQL et les requêtes

## La base de données 

Modèle conceptuel de données :

![MCD](../images/Capture%20d’écran%20du%202024-06-12%2014-00-13.png)


## Script de création de la base de données

```SQL
USE mydb;


INSERT INTO mydb.sessions ( id_films, id_cinema, id_movie_rooms, session_date, hour)
VALUES ((select id_films from films where title = 'Pulp fiction'), 
(select id_cinema from cinema where name = 'Pathe'), 
(select id_movie_rooms from movie_rooms where number = 5 && id_cinema = 1),
"2023-12-09", 18),
((select id_films from films where title = 'Star wars'), 
 (select id_cinema from cinema where name = 'Pathe'), 
 (select id_movie_rooms from movie_rooms where number = 4 and id_cinema = 1), 
 '2023-12-27', 20);


INSERT INTO mydb.distribution (id_actors, id_films, role)
VALUES 
((select id_actors from actors where name = 'Holm'), (select id_films from films where title = 'Le cinquième élément'), "Father Vito Cornelius"),
((select id_actors from actors where name = 'Jovovich'), (select id_films from films where title = 'Le cinquième élément'), "Leeloo"),
((select id_actors from actors where name = 'Travolta'), (select id_films from films where title = 'Pulp fiction'), "Vincent Vega");


INSERT INTO mydb.actors (name, first_name, birth_date, nationality, speciality)
VALUES ("Lauby", "Chantal", '1948-03-23', "française", "comique"),
('Chabat', 'Alain', '1958-11-24', 'française', 'acteur et réalisateur'),
('Farrugia', 'Dominique', '1962-09-02', 'française', 'comique'),
('Darmon', 'Gérard', '1948-02-29', 'française', 'acteur et chanteur'),
('Hall', 'Albert', '1937-11-01', 'Américain', 'acteur polyvalent');


INSERT INTO mydb.films (title, releaseYear, genre, budget, duration)
VALUES ("Indiana Jones", 1981, "aventure", 20000000, 115),
	   ("Star wars", 1977, "aventure", 11500000, 105),
       ("Pulp fiction", 1994, "drame", 8000000, 154),
       ("Le cinquième élément", 1997, "action", 75000000, 126),
	   ("Apocalypse Now", 1979, "guerre", 31000000, 153),
	   ("La cité de la peur", 1994, "comédie", 7500000, 93),
	   ("Mon voisin Totoro", 1999, "Jeunesse", 3000000, 86);


INSERT INTO mydb.movie_rooms (id_cinema, number, nb_places)
VALUES ((select id_cinema from cinema where name = 'Cinéma Pathée'), 1, 350),
	   ((select id_cinema from cinema where name = 'Cinéma Pathée'), 2, 420),
       ((select id_cinema from cinema where name = 'Cinéma Pathée'), 3, 220),
       ((select id_cinema from cinema where name = 'Cinéma Pathée'), 4, 270),
       ((select id_cinema from cinema where name = 'Cinéma Pathée'), 5, 280),
       ((select id_cinema from cinema where name = 'cinéma Megarama'), 1, 157),
       ((select id_cinema from cinema where name = 'cinéma Megarama'), 2, 158),
       ((select id_cinema from cinema where name = 'cinéma Megarama'), 3, 120),
       ((select id_cinema from cinema where name = 'cinéma Megarama'), 4, 130),
       ((select id_cinema from cinema where name = 'La turbine'), 1, 157);
```

## Script des exercices de requêtes SQL

```SQL
-- use the mydb database
USE mydb;

-- Lister l’ensemble des films.
SELECT * FROM films;

-- Liste des films plus long que 2 heures
SELECT * FROM films 
WHERE duration > 120;

-- Liste des films par ordre alphabétique décroissant
SELECT * FROM films 
ORDER BY title DESC;

-- Liste des séances des 10 derniers jours
SELECT * FROM sessions 
WHERE session_date > (SELECT MAX(session_date) FROM sessions)-10;

-- Liste des films avec Harrison Ford dans son casting
SELECT title, actors.first_name, actors.name
FROM films
JOIN distribution ON films.id_films = distribution.id_films
JOIN actors ON actors.id_actors = distribution.id_actors
WHERE actors.name = 'Ford';

-- Liste des toutes les salles avec un film ayant Bruce Willis ou Harrison Ford dans son casting
SELECT cinema.name, movie_rooms.number AS 'numéro salle', films.title, actors.first_name, actors.name
FROM films
JOIN sessions ON films.id_films = sessions.id_films
JOIN movie_rooms ON movie_rooms.id_movie_rooms = sessions.id_movie_rooms
JOIN distribution ON films.id_films = distribution.id_films
JOIN actors ON actors.id_actors = distribution.id_actors
JOIN cinema ON cinema.id_cinema = sessions.id_cinema
WHERE actors.name = 'Ford' || actors.name = 'Willis';

-- Nombre de places totale pour le cinéma Mégarama
SELECT cinema.name, SUM(nb_places) AS 'nombre total place' FROM movie_rooms
JOIN cinema ON movie_rooms.id_cinema = cinema.id_cinema
WHERE cinema.name = 'Megarama';

-- Liste des films projetés dans une salle entre 100 et 200 places
SELECT cinema.name As 'cinéma', movie_rooms.number AS 'numéro salle', films.title, movie_rooms.nb_places
FROM films
JOIN sessions ON films.id_films = sessions.id_films
JOIN movie_rooms ON movie_rooms.id_movie_rooms = sessions.id_movie_rooms
JOIN cinema ON cinema.id_cinema = sessions.id_cinema
WHERE movie_rooms.nb_places BETWEEN 100 AND 200;

-- Tous les cinémas qui ont passé ou vont passer star wars
SELECT name AS 'cinéma', films.title AS 'Film title'
FROM cinema
JOIN sessions ON cinema.id_cinema = sessions.id_cinema
JOIN films ON films.id_films = sessions.id_films
WHERE films.title = 'Star wars'
GROUP BY cinema.name;

-- Nombre total de place par cinéma
SELECT SUM(nb_places) AS 'total places number'
FROM movie_rooms;

-- Budget total de tous les films par année de sortie
SELECT releaseYear, SUM(budget) FROM films
GROUP BY releaseYear;

-- Créer un film avec au moins trois projections pour le mois prochain
INSERT INTO films (title, releaseYear, genre, budget, duration)
VALUES ('Babylon', 2022, 'Comédie/Drame', 80000000, 189);

INSERT INTO actors (name, first_name, birth_date, nationality, speciality)
VALUES ('Robbie', 'Margot', '1990-07-02', 'Autralienne', 'Actrice'),
('Pitt', 'Brad', '1963-12-18', 'Américain', 'Acteur'),
('Calva', 'Diego', '1992-03-16', 'Mexicain', 'Acteur');

INSERT INTO distribution (id_actors, id_films, role)
VALUES ((SELECT id_actors FROM actors WHERE name = 'Robbie'), (SELECT id_films FROM films WHERE title = 'Babylon'), 'Nellie LaRoy'),
((SELECT id_actors FROM actors WHERE name = 'Pitt'), (SELECT id_films FROM films WHERE title = 'Babylon'), 'Jack Conrad'),
((SELECT id_actors FROM actors WHERE name = 'Calva'), (SELECT id_films FROM films WHERE title = 'Babylon'), 'Manny Torres');

INSERT INTO sessions (id_films, id_cinema, id_movie_rooms, session_date, hour)
VALUES ((SELECT id_films FROM films WHERE title = 'Babylon'), 
(SELECT id_cinema FROM cinema WHERE name = 'Pathe'), 
(SELECT id_movie_rooms FROM movie_rooms WHERE number = '2' AND id_cinema = 1), '2024-07-12', 19),
((SELECT id_films FROM films WHERE title = 'Babylon'), 
(SELECT id_cinema FROM cinema WHERE name = 'Megarama'), 
(SELECT id_movie_rooms FROM movie_rooms WHERE number = '3' AND id_cinema = 2), '2024-07-19', 21),
((SELECT id_films FROM films WHERE title = 'Babylon'), 
(SELECT id_cinema FROM cinema WHERE name = 'La turbine'), 
(SELECT id_movie_rooms FROM movie_rooms WHERE number = '1' AND id_cinema = 3), '2024-07-27', 16);

-- Ajouter un cinéma et ses salles
INSERT INTO cinema (name, address, city, phone_number, company)
VALUES ('Les Nemours', '2 Place Ste Claire', 'Annecy', '0450514438', 'Cinéma Les Nemours');

INSERT INTO movie_rooms (id_cinema, number, nb_places)
VALUES ((SELECT id_cinema FROM cinema WHERE name = 'Les Nemours'), 1, 150),
((SELECT id_cinema FROM cinema WHERE name = 'Les Nemours'), 2, 120),
((SELECT id_cinema FROM cinema WHERE name = 'Les Nemours'), 3, 90),
((SELECT id_cinema FROM cinema WHERE name = 'Les Nemours'), 4, 60);

-- Ajouter 1 000 000 au budget du film que vous avez créé
UPDATE films 
SET budget = budget+1000000
WHERE title = 'Babylon';

-- Augmenter de 5% le budget de tous les films
UPDATE films 
SET budget = budget+(budget/100*5);

-- Supprimer un film
DELETE FROM films
WHERE title = 'Mon voisin Totoro';

-- Supprimer les films n’ayant aucune projection
DELETE FROM films
WHERE films.id_films NOT IN (SELECT id_films FROM sessions);

-- Liste de tous les films qui passent aujourd’hui
SELECT title, sessions.session_date FROM films
JOIN sessions ON sessions.id_films = films.id_films
WHERE sessions.session_date = CURRENT_TIMESTAMP;

-- Durée totale de projection pour chaque cinéma
SELECT name, SUM(films.duration)
FROM cinema
JOIN sessions ON cinema.id_cinema = sessions.id_cinema
JOIN films ON sessions.id_films = films.id_films
GROUP BY cinema.name;

-- Liste de tous les films ne contenant pas Harrison Ford
SELECT title, distribution.role
FROM films
JOIN distribution ON films.id_films = distribution.id_films
WHERE films.id_films NOT IN 
	(SELECT id_films 
	FROM distribution
	WHERE distribution.id_actors IN (
		SELECT id_actors 
		FROM actors
		WHERE name = 'Ford'));

-- Liste des cinéma qui passent tous les films
SELECT name
FROM cinema
WHERE cinema.id_cinema IN 
	(SELECT id_cinema
    FROM sessions
    GROUP BY id_cinema
    HAVING COUNT(DISTINCT id_films) = (SELECT COUNT(*) FROM films));
```