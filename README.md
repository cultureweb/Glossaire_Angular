# Glossaire ANGULAR

Publié par Google en 2009, AngularJS est devenu l’un des frameworks JavaScript les plus populaires à ce jour. Pour être vrai, cela n'apporte aucune solution fondamentale nouvelle et révolutionnaire aux développeurs. Il est simple et facile à utiliser, simplifie grandement le processus de développement et la structure du code JavaScript. En d’autres termes, il contient tout ce dont les développeurs ont besoin lors de la création d’une application dynamique à une seule page.

### 1\_ Comment initier le projet Angular?

Démarrons en installant l’outil Angular CLI en global :
```
npm i -g @angular/cli
```
On crée une nouvelle application :
```
ng new project-name
```
**Project name** can not have underscore '_'. It can have dashes '-', small and capital letters and digits.

On va dans le répertoire de l’application générée et on lance le serveur de développement :
```
cd project-name
ng serve
```
Allez sur http://localhost:4200/ et enjoy ! Maintenant, nous devons configurer la gestion du rendu côté serveur.

### 2\_ Créer un premier component 

On crée un répertoire components et notre premier component Todos :
```
ng generate component components/Todos
```

### 3\_ Gréation des Classes

On crée un répertoire models et notre premiere Class Todo dans ce répertoire :
```
export class Todo {
    id:number;
    title:string;
    completed:boolean;
}
```
### 4\_ Importer notre Class

Importer notre class Todo dans notre component todos.ts puis y mettre quelques données en dur.
```
import { Todo } from '../../models/Todo';

export class TodosComponent implements OnInit {
  todos: Todo[];

  constructor() { }

  ngOnInit() {
    this.todos = [
      {
        id: 1,
        title: 'Todo One',
        completed: false
      },
      {
        id: 2,
        title: 'Todo Two',
        completed: true
      },
      {
        id: 3,
        title: 'Todo Three',
        completed: false
      }
    ]
  }

}
```
### 5\_Générer des components
Ensuite pour créer rapidement d'autres components :
```
ng  g c components/TodoItem
```
Cela crée automatiquement un repertoire todo-item avec tout : le TS, le HTML, CSS

### 6\_Lier les components

Dans le fichier **Todos.component.html**, il est temps de lier notre nouveau component todo-item à todos :
```
<app-todo-item *ngFor="let todo of todos" [todo]="todo"> </app-todo-item>
```

### 7/_Contenu dynamique

Remplacer maintenant le contenu dans le fichier todo.item.component.html soit **todo-item works!** créé précedement à la construction du component par :
```
{{ todo.title }}
```
