# JAVA 


## différence entre attributs et propriétées.


##  Héritage et polymorphisme.

https://openclassrooms.com/en/courses/6173501-debutez-la-programmation-avec-java/6458196-specialisez-vos-classes-avec-l-heritage-et-le-polymorphisme


## où trouver de la doc java


- jmdoudoux

- stackoverflow : être stupide pour avoir des réponses quand tu en pose une.

- github

- doc oracle

- baeldung


## Generic types

Les types génériques permettent d’écrire des classes, interfaces ou méthodes qui fonctionnent avec des types différents sans spécifier à l'avance le type exact. Cela permet de réutiliser du code tout en garantissant la sécurité des types au moment de la compilation, évitant ainsi les erreurs de conversion de types (casting).

> Déclaration d'une classe générique
``` java
public class Box<T> {
    private T content;

    public void setContent(T content) {
        this.content = content;
    }

    public T getContent() {
        return content;
    }
}
```

> utilisation d'une classe générique
``` java
Box<String> stringBox = new Box<>();
stringBox.setContent("Hello");
System.out.println(stringBox.getContent());  // Affiche: Hello

Box<Integer> intBox = new Box<>();
intBox.setContent(123);
System.out.println(intBox.getContent());  // Affiche: 123

```


## Exceptions 


## Get classes name

```java
.getClass().getSimpleName();
```



