# Welcome Synorians

This project is mainly for enhance your skills in angular and node.
Please read this page carefully and follow the instructions.

## Angular

We use angular for front end development.

Angular mainly has five major app files. Please ask your mentor about these files and their uses.

### app.component.ts
If we want to trigger some functions at the refresh or opening of the project, then we write those methods and method calls in this file.

app.component.ts calls every time when a page refresh or the project first time open in the browser. eg. of app.component.ts
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Tour of Heroes';
}


```

### app.component.html
This is the common html file of whole project, changes in this file will show in every screen of the project.
```
<h1>{{title}}</h1>
<nav>
  <a routerLink="/dashboard">Dashboard</a>
  <a routerLink="/heroes">Heroes</a>
</nav>
<router-outlet></router-outlet>
<app-messages></app-messages>

```

### app.component.scss
If we want to add CSS classes globally for every component of the project, then we write the CSS classes in this file. eg.
```
h1 {
  font-size: 1.2em;
  color: #999;
  margin-bottom: 0;
}
h2 {
  font-size: 2em;
  margin-top: 0;
  padding-top: 0;
}
nav a {
  padding: 5px 10px;
  text-decoration: none;
  margin-top: 10px;
  display: inline-block;
  background-color: #eee;
  border-radius: 4px;
}
nav a:visited, a:link {
  color: #607D8B;
}
nav a:hover {
  color: #039be5;
  background-color: #CFD8DC;
}
nav a.active {
  color: #039be5;
}
```
### app.module.ts
This is the file where we import the external packages and libraries in project.
```
import { NgModule }       from '@angular/core';
import { BrowserModule }  from '@angular/platform-browser';
import { FormsModule }    from '@angular/forms';
import { HttpClientModule }    from '@angular/common/http';
import { HttpClientInMemoryWebApiModule } from 'angular-in-memory-web-api';
import { InMemoryDataService }  from './in-memory-data.service';
import { AppRoutingModule }     from './app-routing.module';
import { AppComponent }         from './app.component';
import { DashboardComponent }   from './dashboard/dashboard.component';
import { HeroDetailComponent }  from './hero-detail/hero-detail.component';
import { HeroesComponent }      from './heroes/heroes.component';
import { HeroSearchComponent }  from './hero-search/hero-search.component';
import { MessagesComponent }    from './messages/messages.component';

@NgModule({
  imports: [
    BrowserModule,
    FormsModule,
    AppRoutingModule,
    HttpClientModule,

    // The HttpClientInMemoryWebApiModule module intercepts HTTP requests
    // and returns simulated server responses.
    // Remove it when a real server is ready to receive requests.
    HttpClientInMemoryWebApiModule.forRoot(
      InMemoryDataService, { dataEncapsulation: false }
    )
  ],
  declarations: [
    AppComponent,
    DashboardComponent,
    HeroesComponent,
    HeroDetailComponent,
    MessagesComponent,
    HeroSearchComponent
  ],
  bootstrap: [ AppComponent ]
})
export class AppModule { }

```
### app-routing.module.ts
We use this file for routing the project according their urls, eg.
```
import { NgModule }             from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

import { DashboardComponent }   from './dashboard/dashboard.component';
import { HeroesComponent }      from './heroes/heroes.component';
import { HeroDetailComponent }  from './hero-detail/hero-detail.component';

const routes: Routes = [
  { path: '', redirectTo: '/dashboard', pathMatch: 'full' },
  { path: 'dashboard', component: DashboardComponent },
  { path: 'detail/:id', component: HeroDetailComponent },
  { path: 'heroes', component: HeroesComponent }
];

@NgModule({
  imports: [ RouterModule.forRoot(routes) ],
  exports: [ RouterModule ]
})
export class AppRoutingModule {}

```
In angular we have to maintain some common variables and methods, so that we don't need to rewrite these methods in every components.
We use services for this purpose.

Some examples of the common methods and variable are
```
- HTTP calls
  - Get call
  - Post call
- Server API urls
- Common variables eg. some form object
```
These are common things you need to maintain in your every angular project
```
- Always use code indentation.
- Never repeat your code (DRY rule of coding)
- Always use services for the common methods and variables
- Try to use predefined libraries and packages for implementation of your task
- Always ask your mentor for review your code
```

#### Some common commands of Angular
```
1. npm i
   This command install all the packages present in the package.json file of the project.
2. npm i [SOME_PACKAGE_NAME]
   This command install the given package in the project.
3. npm i --save [PACKAGE_NAME]
   This command install the given package in the project and save that package in package.json file.
4. ng serve
   This command open the project in the browser on port 4200
5. ng g [COMMAND] [NAME]
   This command is use for generating the files in the project here g stands for generate.
   Some commands are
   - ng g service SERVICE_NAME
   - ng g component COMPONENT_NAME
6. ng build
   This command is use for build the project.
7. ng new PROJECT_NAME --routing --style="scss"
   This command is use for start the new project.
```
[Example project](https://angular.io/generated/zips/toh-pt6/toh-pt6.zip)

Please download this project and ask your mentor for your task.

Happy learning, Thankyou

### Synoriq Team Welcomes You
