# VueJS

### ¿Qué es VueJS?
* Es un framework para la construccion de interfaces de usuario que posee un comportamiento **reactivo**, quiere decir que los datos de las variables de JS y los datos que se muestran en el DOM estan vinculados. Si cambio algo en el JS, se verá reflejado en el DOM 
* Puede integrarse con herramientas como Laravel

### Instalación de VueJS

#### Como un CDN
Es la forma mas facil de instalar VueJS, tenemos que pegar lo siguiente en nuestro HTML 

`<script src="https://unpkg.com/vue@next"></script>`

Para aplicaciones que van a ir a produccion, nos conviene especificar la version de Vue que estamos usando para evitar que nuestro codigo se "rompa" ante cualquier actualizacion

`<script src="https://unpkg.com/vue@3.0.5/dist/vue.global.js"></script>` 

#### Con NPM (Mi Favorita!)

Es recomendado para aplicaciones mas grandes, y se integra muy bien con Webpack o Rollup. Para instalarlo corremos el siguiente comando:

`npm install vue@next` 

#### Instalacion VueCLI
El CLI es basicamente una "interfaz" en la linea de comandos que podemos instalar de forma global para crear aplicaciones de VueJS rapidamente. Si no sabés mucho sobre NodeJS, no recomiendo empezar por acá.

`yarn global add @vue/cli` | o NPM si es de tu preferencia (con Sudo para sistemas operativos basados en Unix)

## Empezamos con lo tecnico!

### Instancia de la aplicacion
Toda aplicacion de Vue comienza con un `createApp`, que inicializa una instancia

```
Vue.createApp({
	/* codigo futuro */
});
```

La instancia nos permite
* Registrar propiedades globales para que sean usadas por los componentes
* Recibir propiedades para poder interactuar con el DOM
* Podemos registrar componentes, usar ciertos modulos, etc.. 

```
const app = Vue.createApp({})
app.component('SearchInput', SearchInputComponent) // Registrar componente
app.directive('focus', FocusDirective) 
app.use(LocalePlugin) // Usar ciertos plugins
```

Como todos los metodos funcionan sobre la misma instancia `app`, podemos concatenarlos de la siguiente forma:

```
Vue.createApp({})
  .component('SearchInput', SearchInputComponent)
  .directive('focus', FocusDirective)
  .use(LocalePlugin)
```