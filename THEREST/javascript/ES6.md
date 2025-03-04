# Les principes de javascript

## le desctructuring

https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment

## promises

https://www.pierre-giraud.com/javascript-apprendre-coder-cours/promesse-promise/

## async / await

`async` et `await` sont des outils en JavaScript qui rendent plus facile l'utilisation des promesses, en rendant le code asynchrone plus lisible et proche du code synchrone.

### Comment `async` et `await` fonctionnent avec les promesses :

1. **`async`** : Quand tu mets le mot-clé `async` devant une fonction, cette fonction retourne automatiquement une promesse. Cela signifie que, même si tu écris du code qui semble être synchrone à l'intérieur de cette fonction, elle retournera une promesse. Par exemple :

   ```javascript
   async function fetchData() {
       return "Data received!";
   }

   fetchData().then(result => console.log(result));  // Affiche "Data received!"
   ```

   Ici, `fetchData()` retourne une promesse qui est résolue avec la valeur `"Data received!"`.

2. **`await`** : Le mot-clé `await` ne peut être utilisé qu'à l'intérieur d'une fonction `async`. Il est utilisé pour attendre qu'une promesse soit résolue. Au lieu d'utiliser `.then()` pour gérer le résultat d'une promesse, tu peux simplement attendre que la promesse soit résolue, et récupérer directement la valeur renvoyée. Par exemple :

   ```javascript
   async function fetchData() {
       let data = await getDataFromServer();  // On attend que la promesse soit résolue
       console.log(data);  // Utilise la donnée une fois qu'elle est reçue
   }

   fetchData();
   ```

   Ici, `await getDataFromServer()` va attendre que la promesse retournée par `getDataFromServer()` soit résolue, puis assigner le résultat à `data`. Ensuite, tu peux utiliser `data` comme si tu l'avais récupéré de manière synchrone.

### Exemple pratique :

Supposons que tu veux récupérer des données depuis un serveur :

Sans `async`/`await` (en utilisant `.then()` et `.catch()` pour gérer les promesses) :

```javascript
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
        console.log(data);
    })
    .catch(error => {
        console.error('Error:', error);
    });
```

Avec `async`/`await` :

```javascript
async function getData() {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error:', error);
    }
}

getData();
```

### En résumé :
- **`async`** transforme une fonction en une fonction asynchrone qui retourne une promesse.
- **`await`** est utilisé pour attendre la résolution d'une promesse de manière synchrone, simplifiant la gestion du flux de code asynchrone.

Ces deux outils rendent le code asynchrone plus simple et lisible, en éliminant le besoin de multiples `.then()` et en rendant le code plus facile à suivre.