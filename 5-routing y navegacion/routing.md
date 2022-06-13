lo primero es comprobar q tenemos esta clase en el index.html

<base href="/">

creanmos un nuevo fichero en app

app.routing.ts

import { ModuleWithProviders } from "@angular/core";
import { Routes, RouterModule } from "@angular/router";


// importar componentes
 import { Empleadocomponent } from "./empleado/empleado.component";
 import { Frutacomponent } from "./fruta/fruta.component";

 despues añadimos las rutas:

 const appRoutes: Routes = [
{path:'', component: Empleadocomponent},
{path: 'empleado', component: Empleadocomponent},
{path: 'fruta', component: Frutacomponent},
{path:'**', component: Empleadocomponent}

 ];

 lo siguiente seria importarlo desde el module
 import { routing, appRoutingProviders } from './app.routing';

 en los import pongo la variable routing

 y en el providers

  providers: [appRoutingProviders],

  por ultimo pondriamos la clase en nuestro app.component.html

  <router-outlet></router-outlet>