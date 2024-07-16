# Laravel et ses principes

## Installation

https://www.youtube.com/watch?v=szLzonMlzQk     


## Glossaire

|Termes|Définition|
| - | - |
| API | C'est une application qui définit les règles qui permettent à 2 logiciels de communiquer entre eux: les routes, les méthodes CRUD, etc... |
| REST | C'est un style d'architecture d'une API, elle est simple et standardisée |
| MVC |signifie “Modèle, Vue, Contrôleur”, c’est un patron de conception concernant l'agencement du code. Le code est segmenté selon ces trois sections : le modèle contient le code qui gère la logique métier, la vue celui qui gère l'affichage, et le contrôleur gère le lien avec l'utilisateur. |
| ORM | Permet de connecter L'API à la base donnée |
|API|efef|
|API|efef|
|API|efef|
|API|efef|


## MVC 

https://openclassrooms.com/fr/courses/4670706-adoptez-une-architecture-mvc-en-php/7847928-decouvrez-comment-fonctionne-une-architecture-mvc



### Exemple MVC php laravel


Modèle (Model)

```php
// app/Models/Book.php
namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Book extends Model
{
    protected $fillable = ['title', 'author'];

    public static function getAllBooks()
    {
        return self::all();
    }

    public static function addBook($title, $author)
    {
        return self::create(['title' => $title, 'author' => $author]);
    }

    public static function removeBook($id)
    {
        return self::destroy($id);
    }
}
```


Vue (View)
list_books.blade.php
```php
<!-- resources/views/list_books.blade.php -->
<!DOCTYPE html>
<html>
<head>
    <title>Liste des Livres</title>
</head>
<body>
    <h1>Liste des Livres</h1>
    <ul>
        @foreach ($books as $book)
            <li>{{ $book->title }} by {{ $book->author }}
                <form action="{{ url('remove_book/' . $book->id) }}" method="POST" style="display:inline;">
                    @csrf
                    @method('DELETE')
                    <button type="submit">Supprimer</button>
                </form>
            </li>
        @endforeach
    </ul>
    <form action="{{ url('add_book') }}" method="POST">
        @csrf
        <input type="text" name="title" placeholder="Titre du Livre">
        <input type="text" name="author" placeholder="Auteur">
        <button type="submit">Ajouter</button>
    </form>
</body>
</html>
```


Contrôleur (Controller)
```php
// app/Http/Controllers/BookController.php
namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Models\Book;

class BookController extends Controller
{
    public function index()
    {
        $books = Book::getAllBooks();
        return view('list_books', ['books' => $books]);
    }

    public function addBook(Request $request)
    {
        $request->validate([
            'title' => 'required|max:255',
            'author' => 'required|max:255',
        ]);

        Book::addBook($request->title, $request->author);
        return redirect('/');
    }

    public function removeBook($id)
    {
        Book::removeBook($id);
        return redirect('/');
    }
}
```

Routes
```php
// routes/web.php
use App\Http\Controllers\BookController;

Route::get('/', [BookController::class, 'index']);
Route::post('/add_book', [BookController::class, 'addBook']);
Route::delete('/remove_book/{id}', [BookController::class, 'removeBook']);
```


Explication du Flux de l'Application

-  Lancement de l'application : Le serveur Laravel démarre et écoute les requêtes HTTP.

- Afficher la liste des livres : Lorsque l'utilisateur visite l'URL /, le contrôleur index est appelé. Il récupère la liste des livres du Modèle Book et passe ces données à la Vue list_books.blade.php pour les afficher.

- Ajouter un livre : L'utilisateur remplit le formulaire et soumet les données à l'URL /add_book. Le contrôleur addBook est appelé, il récupère les données du formulaire, appelle le Modèle Book pour ajouter le nouveau livre, puis redirige l'utilisateur vers la page d'accueil pour voir la mise à jour.

- Supprimer un livre : Si l'utilisateur veut supprimer un livre, il soumet une requête DELETE à /remove_book/{id}. Le contrôleur removeBook appelle le Modèle Book pour supprimer le livre, puis redirige l'utilisateur vers la page d'accueil.


Cette architecture MVC en PHP/Laravel permet de séparer les responsabilités et de structurer l'application de manière organisée et maintenable.