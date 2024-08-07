# Glossaire de la programmation orientée objet

| Terme | Définition |
| - | - |
| Attributs | les variables décrivant l’état de l’objet |
| Méthodes | Fonctions, actions d'un objet |
| Portée | Terme qui défini qui et quoi peut avoir accès ou non à une variable https://www.learn-php.org/en/Objects |
| Instancier | Créer un objet à partir d'une classe |
| Objet | regroupement de valeurs et de fonctions, est une instance de la classe. |
| Classe | La définition d'un objet et de ses méthodes(fonctions), à partir d'un classe on peut créer plusieurs objets. |
| Héritage | L’héritage permet de passer les propriétés et méthodes d’une classe “parent” à des classes “enfants”. Evite la duplication de code. https://www.learn-php.org/en/Objects |
| Abstraction | Permet de désigner une classe qui ne doit pas être instacier et qui doit seulement servir de classe parent. Une méthode abstraite est une méthode qui n’a pas de corps (traitement) ,on définit juste la signature (le prototype de la méthode). https://www.9raytifclick.com/cours/abstraction-en-poo-et-implementation-en-python/|
| Surcharge | En programmation orientée objet, la surcharge, aussi appelée « overloading », consiste à déclarer, dans une même classe, deux méthodes de même nom mais avec des sémantiques différentes. https://www.invivoo.com/zoom-heritage-encapsulation-surcharge-polymorphisme/ |
| Interfaces | Permettent de créer du code qui spécifie quelles méthodes une classe doit implémenter, sans avoir à définir comment ces méthodes fonctionneront. https://www.php.net/manual/fr/language.oop5.interfaces.php|
| Constructor function | fonction éxécutée à l'instanciation de l'objet avec le terme "new" https://www.learn-php.org/en/Objects |
| static | Static methods can be called directly - without creating an instance of the class first. https://www.w3schools.com/php/php_oop_static_methods.asp|
| Attributs | les variables décrivant l’état de l’objet |
| Getters | fonctions servant à donner l'attribut que l'on demande https://www.easy-micro.org/getters-et-setters.php&id=1102|
| Setters | fonctions permettant d'assigner une valeur à un attribut https://www.easy-micro.org/getters-et-setters.php&id=1102 |


## $this

```
class StartrekWarrior extends Warrior {

    public int $mentalPower;

    public function __construct(int $mentalPower = 0) {
        $this->mentalPower = $mentalPower;
    }

    public function getPower (): int {
        return $this->mentalPower;
    }
} 
```


In your StartrekWarrior class, the variable $this->mentalPower is not equivalent to the variable $mentalPower. They refer to different things:

- $this->mentalPower refers to the instance variable (property) mentalPower of the StartrekWarrior class.
- $mentalPower without $this would refer to a local variable within a method, which you haven't defined in the provided code snippet.


The error when returning $mentalPower happens because $mentalPower as a local variable is not defined in the context of the getPower method. Instead, you should return $this->mentalPower, which refers to the class property.

Here's the corrected version of your class with additional necessary corrections:

- Initialize $mentalPower in the constructor.
- Fix the visibility of the property to public (if it's meant to be accessed directly) or provide getter/setter methods.
- Correct the return statement to use $this->mentalPower.

Explanation:

- Property Definition: The property public int $mentalPower; defines an instance variable mentalPower that is public.
- Constructor: The constructor __construct initializes the mentalPower property. You can pass an initial value when creating an instance of StartrekWarrior.
- Method getPower: The method getPower returns the value of the instance variable $this->mentalPower.

## TP Zoo


| Question | Réponse |
| - | - |
| C’est quoi un autoload en php ? | C'est un moyen d'inclure chaque classes dans mon code sans avoir à les inclure une à une manuellement |
| Qu’est-ce qu’un fichier .PHAR ? | une librairie qui permet de compiler toute une application dans un seul fichier.PHAR on l'appel aussi une archive php |
| Qu’est-ce que composer ? | c'est un gestionnaire de packages propre à php. |
| Quel intérêt y-a-t’il à l’utiliser ? | - Enables you to declare the libraries you depend on. - Finds out which versions of which packages can and need to be installed, and installs them (meaning it downloads them into your project). - You can update all your dependencies in one command. |
| Quelle est la version actuelle de composer ? | 2.7.7 |
| C’est quoi PSR ? | ce sont des recommandation standard des concepts de programations en PHP |
| C’est quoi PSR-4 ? | PSR-4 dictates the naming convention but also dictates how that naming convention translates to a filepath. |
