# Javascript

## Librairies utiles

- Lodash.

### Copier une variable d'objets json dans une autre variable sans le même id:

```JS
let dataArraySample = JSON.parse(JSON.stringify(jsonDatas));
```


### Comment créer une object et l'insérer dans un tableau

```JS
let biggestCitiesSorted = cities.reduce((total, city) => {
    let temp = {};
    if (city.population >= 300000) {
        temp[city.nom] = city.population;
        total.push(temp);
    }
    return total;
}, []);
```