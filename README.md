# ionic 3
#### Este repositorio contiene comandos de ionic 3


### Instalando
```
sudo npm install -g cordoba
sudo npm install -g cordoba ionic
```


- creando una app
```
ionic start nombre_app
```
luego cd nombre_App
```
ionic serve --lab
```

- generar una página
```
ionic generate page nombre_pagina
```
Luego dentro de src/app/app.modules.ts se debe importar la página que se agrego en el paso anterior
```
import {nombre_paginaPage} from '../carpeta/nombre_pagina';
```
esto se debe repetir con cada página que se agregue

- Agregar el nombre de la página dentro de @NgModule Nombre_Pagina,
- Agregar el nombre de la página dentro de 'entryComponents Nombre_Pagina

- Probando la app en dispositivos reales
```
ionic cordoba run android --device
ionic cordoba run ios --device
```
_____________________________________________________________________________________________________
### Poner fondo de pantalla a un Actívity

1. Primero cargar las imágenes en la ruta correspondiente
```
src/assets/imgs
```

2. Dentro del activity donde se desea poner el fondo se debe crear una clase en el archivo html , dentro de la etiqueta: 
```
<ion-content padding class="nombre_clase">
```

3. Dentro de la carpeta de la página editar el archivo SCSS y dentro de las llaves de "pate-nombre_pagina" allí copiar el estilo que se aplicará al activity. Ejemplo:
```
Page-menu{
.nombre_clase{

background-image: url('../assets/imgs/fondo.jpg');
background-position:center;
background-repeat: no repeat;
background-size: contain;
              }
          }
```
_____________________________________________________________________________________________________

### Poner una imagen como boton

1. Previamente la imagen debe estar en la carpeta src/assets/imgs
2. en el html donde se quiera poner el boton se debe ingresar dentro de <ion-content padding>
```
<ion-content padding class="nombre_clase_fondo">
  <button ion-button clear class="btn_volver"(click)="volver()"></button>
```
La clase de boton se define en el archivo scss, donde se indica el fondo.
La funcion que ejecutará el boton se define en el archivo .ts
En el archivo .scss se pone la imágen del boton, y el estilo y posición que se le quiera dar:
```
.btn_volver{
background-image: url('../assets/imgs/imagen.jpg');
background-position: center;
background-repeat: no-repeat;
background-size: contain;
position: fixed;
height: 10%;
width: 50%;
bottom: 20px;
left: -7%;
          }
```
  
_____________________________________________________________________________________________________

### Archivos textscript "ts"

Similar a un archivo .js aquí se encontraran todas las funciones y la lógica de la app. Aquí un ejemplo de una funcion para pasar de un activity a otro:
```
volver(){
  this.navCtrl.push(SegundapaginaPage);
        }
```

Tener presente que la página a la que se quiere redirigir debe estar importada en la cabecera del archivo .ts en el que se está trabajando.

_____________________________________________________________________________________________________
### Estilos y funciones globales

```
src/app/app.scss
```
La hoja de estilos de arriba es GLOBAL, en caso de querer compartir un mismo estilo en varios activityes se debe poner aca.
_____________________________________________________________________________________________________

### Listar Plugins instalados

```
ionic cordova plugin                # lista todos los plugins
ionic cordova add nombre_plugin     # agrega un pligin
ionic cordova rm nombre_plugin      # borra un plugin
VARIANTES
cordova plugin ls     #lista todos los plugins
cordova plugin add    # agrega un pligin
cordova plugin rm     # borra un plugin






