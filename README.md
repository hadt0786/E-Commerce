# ECommerce

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.1.5.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## Project E-Commerce

### Step 1

1.  `ng new e-commerce`
2.  `cd/E-Commerce`
3.  `code .`
4.  `ng serve --open`
   
### Step 2 : FIREBASE

1. `www.console.firebase.google.com`
2. `Add A Project`
3. Project name : `E-Commerce`
4. `Create project`
5. Click `</>` Add Firebase to your Web App
6. Copy the 
    var config = { coppy all the properties };

### Step 3: Come to Angular project in your project

1.  `environemnt.ts` 

```
export const environemnt = {
  production: false,
  firebase : {
    paste all the properties copied from console.firebase.com
    var config = { };
  }
};

```

2.  `environemnt.prod.ts`
   
```
export const environment = {
  priduction: true,
  firebase : {
    paste all the properties copied from console.firebase.com
    var config = { };
  }
}

```
### Install Node packages

1.  `npm install --save firebase@4.2.0 angularfire2@4.2.0-rc.1`
  
### Adding to module

`app.module.ts`

```
import { AngularFireModule } from 'angular/fire2';

import { AngularFireDatabaseModule } from 'angular2/database';

import { AngularFireAuthModule } from 'angularfire2/auth';

import { environment } from './../environemnts/enviroment'; be careful about the path should not not be environemnt.prod

imports: [
  AngularFireModule.initializeApp(environemnt.firebase),
  AngularFireDatabaseModule,
  AngularFireAuthModule
]


```

`ng s -o`

### Installing Bootstrap 

Bootstrap version - 4.x

1.  `npm install --save bootstrap@4.0.0-beta`
2.  `style.css`
  
```
@import "~bootstrap/dist/css/bootstrap.css";
 path relative to node module format


```

3.  `https://getbootstrap.com/docs/4.1/examples/starter-template/`
   
   right click - `view page source`

add in `app.component.html`
   ```

  

    <nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
      <a class="navbar-brand" href="#">Navbar</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExampleDefault" aria-controls="navbarsExampleDefault" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarsExampleDefault">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#">Disabled</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="https://example.com" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
            <div class="dropdown-menu" aria-labelledby="dropdown01">
              <a class="dropdown-item" href="#">Action</a>
              <a class="dropdown-item" href="#">Another action</a>
              <a class="dropdown-item" href="#">Something else here</a>
            </div>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input class="form-control mr-sm-2" type="text" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </nav>
    <!--will put upto this code in bs-navbarcomponent>


    <main role="main" class="container">

      <div class="starter-template">
        <h1>Bootstrap starter template</h1>
        <p class="lead">Use this document as a way to quickly start any new project.<br> All you get is this text and a mostly barebones HTML document.</p>
      </div>

    </main><!-- /.container -->
   ```

`ng s -o`

4.  `style.css`

```
body {
padding-top: 8px;
}
```

5. change navigation background color
   
   `app.component.html`

modify

`    <nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
`

to 
`    <nav class="navbar navbar-expand-md navbar-light bg-light fixed-top">
`

### Step 4: Extracting Navbar Component

`ng g c bs-navbar`

`bs-navbar.component.html`

```
 <nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
      <a class="navbar-brand" href="#">Navbar</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExampleDefault" aria-controls="navbarsExampleDefault" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarsExampleDefault">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#">Disabled</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="https://example.com" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
            <div class="dropdown-menu" aria-labelledby="dropdown01">
              <a class="dropdown-item" href="#">Action</a>
              <a class="dropdown-item" href="#">Another action</a>
              <a class="dropdown-item" href="#">Something else here</a>
            </div>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input class="form-control mr-sm-2" type="text" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </nav>
```

`bs-navbar.component.ts`

**selector: 'bs-navbar'**

6. Render `app.component.html`
   
   `<bs-navbar></bs-navbar>`

### Define various routes

1.  generate a componets for public areas
   
   `home`
   `ng g c home`

   `products`
   `ng g c products`

  `shopping-cart`
   `ng g c shopping-cart`

   `check-out`
   `ng g c check-out`

  `order-success`
   `ng g c order-success`

   `my-order`
   `ng g c my-orders`

   `login`
   `ng g c login`

  `admin/admin-products`
  `ng g c admin/admin-products`

  `admin/admin-orders`
  `ng g c admin/admin-orders`

2.  Register our Routes
   
   `app.module.ts`

  ```
   import { RouterModule } from '@angular/router';


   imports : [
     RouteModule.forRoot([
       // multiple route objects
       { path : '', component: HomeComponets },
       { path : 'products', component: ProductsComponets },
       { path : 'shopping-cart', component: ShoppingCartComponets },
       { path : 'check-out', component: CheckOutComponets },
       { path : 'order-success', component: OrderSuccessComponets },
       { path : 'login', component: LoginComponets },
       { path : 'admin/orders', component: AdminOrdersComponets },
       { path : 'admin/products', component: AdminProductsComponets },
     ])
   ]

  ```  
`app.component.html`
```
<bs-nabar></bs-navbar>
<div class="container">
<router-outlet></router-outlet>
</div>
```
`bs-navbar.component.html`

```
 
<nav class="navbar navbar-expand-md navbar-light bg-light fixed-top">
  <a class="navbar-brand" routerLink="/">O</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExampleDefault" aria-controls="navbarsExampleDefault" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarsExampleDefault">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item">
        <a class="nav-link" routerLink="/shopping-cart">Shopping Cart</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" routerLink="/login">Login</a>
      </li>
      <li ngbDropdown class="nav-item dropdown">
        <a ngbDropdownToggle class="nav-link dropdown-toggle" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Username</a>
        <div ngbDropdownMenu class="dropdown-menu" aria-labelledby="dropdown01">
          <a class="dropdown-item" routerLink="/my/orders">My Orders</a>
          <a class="dropdown-item" routerLink="/admin/orders">Manage Orders</a>
          <a class="dropdown-item" routerLink="/admin/products">Manage Products</a>
          <a class="dropdown-item">Log Out</a>
        </div>
      </li>
    </ul>
  </div>
</nav>
```

### Adding a DropDown menubar

1. `ng-bootstrap`

`npm i --save @ng-bootstrap/ng-bootstrap` - version 1.0.0-beta.1

2. `app.module.ts`
  
  `import { NgbModule } from '@ng-bootstrap/ng-bootstrap';`

  imports: [
    NgbModule.forRoot()
  ]
 
  Apply on
  ``` 
  <li ngbDropdown class="nav-item dropdown" >
    <a ngbDropdown class="nav-link dropdown-toggle" href="#" id="dropdown01" ...>
    <div ngbDropdownMenu class="dropdown-menu" arial-labelledby="dropdown01">
```
### CLeaning up the navbar

1. `bs-navbar.component.html`
   
  ```

  <div ngbDropdownToggle class="dropdown-menu" arial-labelledby="dropdown01">

  <a class="dropdown-item" routerLink="my/orders ">My Orders</a>
  <a class="dropdown-item" routerLink="admin/orders">Mangae orders</a>
  <a class="dropdown-item" routerLink="/admin/products">Manage Products</a>

<a class="dropdown-item" >Logout</a>

```

### Fixing some issues

`app.module.ts`
```
imports:[
  RouterModule.forRoot([
  {path:'my.orders', component: MyOrderComponent } 
  ])
]
```

### Deploy firebase

1. `firebase --version` output -- 3.9.2
   
   `firebase login`
   insode ecoonerce 
   1. firebase init
   2. select hosting
   3.  
   if not `sudo npm i g firebase-tools`



### Project Authentication and Authorisation

