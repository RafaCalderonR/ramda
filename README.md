Ramda
=============

Una biblioteca funcional practica para desarrolladores Javascript.

[![Build Status](https://travis-ci.org/ramda/ramda.svg?branch=master)](https://travis-ci.org/ramda/ramda)
[![npm module](https://badge.fury.io/js/ramda.svg)](https://www.npmjs.org/package/ramda)
[![dependencies](https://david-dm.org/ramda/ramda.svg)](https://david-dm.org/ramda/ramda)
[![Gitter](https://badges.gitter.im/Join_Chat.svg)](https://gitter.im/ramda/ramda?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)



¿Por qué Ramda?
----------

<img src="https://ramdajs.com/ramdaFilled_200x235.png" 
     width="170" height="190" align="right" hspace="12" />

Ya hay varias bibliotecas excelentes con un sabor funcional. Por lo general, están destinadas a ser herramientas de uso general, adecuadas para trabajar en múltiples paradigmas.Ramda tiene un objetivo más centrado. Queriamos una biblioteca diseñada especificamente para un estilo de programación funcional, una que nunca mute los datos del usuario. 



¿Cual es la diferencia?
-----------------

Las principales características distintivas de Ramda son:

* Ramda enfatiza el estilo funcional más puro. Inmutabilidad y funciones sin efectos secundarios son el corazón de su filosofía. Esto te ayudara a hacer el trabajo de manera simple y elegante

* Las funciones Ramda implementan automáticamente el Currying. Esto te permitirá crear fácilmente nuevas funciones a partir de las antiguas al no tener la necesidad de proporcionar parametros finales.

* Los parámetros para las funciones de Ramda están organizados para que sea conveniente para el currying, los datos generalmente se suministra en último lugar.

Los dos últimos puntos juntos hacen que sea muy fácil construir funciones como secuencia de funciones más simples, cada una de las cuales transforma los datos y los pasa al siguiente. Ramda esta diseñado para admitir este estilo de codificación.



Introducción
-------------

* [Introducing Ramda](http://buzzdecafe.github.io/code/2014/05/16/introducing-ramda) by Buzz de Cafe
* [Why Ramda?](http://fr.umio.us/why-ramda/) by Scott Sauyet
* [Favoring Curry](http://fr.umio.us/favoring-curry/) by Scott Sauyet
* [Why Curry Helps](https://hughfdjackson.com/javascript/why-curry-helps/) by Hugh Jackson
* [Hey Underscore, You're Doing It Wrong!](https://www.youtube.com/watch?v=m3svKOdZijA&app=desktop) by Brian Lonsdorf
* [Thinking in Ramda](https://randycoulman.com/blog/categories/thinking-in-ramda) by Randy Coulman



Filosofía
----------
Usar Ramda debería parecerse a usar Javascript. 
Es práctico, Javascript funcional. No estamos presentando expresiones lambda
en cadena, no estamos presentando *consed lists*, ni estamos transfiriendo todas
las funciones de *Clojure*.

Nuestras estructuras de datos básicas son objetos Javascript simples, y 
nuestras colecciones habituales son matrices de Javascript. También mantenemos 
otras características nativas de Javascript, como funciones como objetos con
propiedades.

La programación funcional es en buena parte sobre objetos inmutables y funciones
sin efectos secundarios.
Si bien Ramda no *impone* esto, sí permite que este estilo tenga la menos fricción posible.

Nuestro objetivo es una implementación limpia y elegante, pero la es el rey.
Sacrificamos una gran cantidad de elegancia de implementación por una API más
limpia.

Por último, pero no menos importante, Ramda se esfuerza por el rendimiento. Una
implementación rápida y confiable gana a cualquier noción de pureza funcional. 



Instalación
------------

Para usar con node:

```bash
$ npm install ramda
```

Luego en la consola:

```javascript
const R = require('ramda');
```

Para usar directamente en el navegador:

```html
<script src="path/to/yourCopyOf/ramda.js"></script>
```

o la versión minificada:

```html
<script src="path/to/yourCopyOf/ramda.min.js"></script>
```

o de un CDN, o cdnjs:

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/ramda/0.25.0/ramda.min.js"></script>
```

o unos de los siguientes enlaces de [jsDelivr](http://jsdelivr.com):

```html
<script src="//cdn.jsdelivr.net/npm/ramda@0.25.0/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@0.25/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@latest/dist/ramda.min.js"></script>
```

(tenga en cuenta que el uso de `las ultimas versiones` supone un riesgo significativo, los cambios de la API pueden romper su código.)

Estas etiquetas de script agregan la variable `R` en el alcance global del navegador.

O puede inyectar ramda en prácticamente cualquier sitio web utilizando [the bookmarklet](https://github.com/ramda/ramda/blob/master/BOOKMARKLET.md).

**Nota para versiones > 0.25**

Las versiones de Ramda > 0.25 no tiene una exportacíon predeterminada.
Entonces, en lugar de `import R from 'ramda';`, uno tiene que usar `import * as R from 'ramda';`
O mejor aún, importe solo las funciones requeridas a través de `import { functionName } from 'ramda';`

### Build

`npm run build` crea directorios `es`, `src` y actualiza __dist/ramda.js__ and __dist/ramda.min.js__

#### Partial Builds

Es posible construir Ramda con un subconjunto de la funcionalidad para reducir su tamaño. El sistema de compilación de Ramda lo admite con banderas de comando. Por ejemplo si estás usando `R.compose`, `R.reduce`, y `R.filter` tu puedes crear una compilación parcial con:

    npm run --silent partial-build compose reduce filter > dist/ramda.custom.js

Esto requiere tener Node/io.js instalado y las dependencias de ramda instaladas (use `npm install` antes de ejecutar la compilación parcial.). 

### Instalar funciones específicas

[Instalar funciones individuales](https://bitsrc.io/ramda/ramda) cont bit, npm and yarn sin intalar toda la biblioteca

Documentación
-------------

Por favor, revise [API documentacion](https://ramdajs.com/docs/).

Tambien disponible nuestro [Cookbook](https://github.com/ramda/ramda/wiki/Cookbook) de funciones creadas a partir de Tamda que puede resultarte útiles.


El nombre
--------

Ok.. nos gustan las ovejas.  eso es todo.  Es un nombre corto, aun no
pillado. Podría haber sido `eweda`, pero entonces estaríamos obligados
a decir  _eweda lamb!_, y nadie quiere eso.



Ejecutando Test Suite
----------------------

**Consola:**

Para ejecutar las pruebas desde consola, tu necesitas tener instalado `mocha`:

    npm install -g mocha

Desde la raíz del proyecto, puedes llamar:

    mocha

Alternativamente, si ha instalado las dependencias, a través de:

    npm install

Entonces puede ejecutar las pruebas(y obtener resultados) ejecutando:

    npm test

**Navegador:**

Puedes usar [testem](https://github.com/airportyh/testem)  para
prueba en diferentes navegadores (incluso *headlessly*), con *livereloading* de
pruebas. Instale testem (`npm install -g testem`) and ejecuta `testem`. Abre el
enlace proporcionado en su navegador y verá los resultados en su terminal.

Si tienes _PhantomJS_ instalado, tu puedes ejecturar simplemente `testem -l phantomjs`.


Uso
-----------------

Para `v0.25` y superiores,  importe toda la biblioteca o elija los módulos ES directamente desde la biblioteca:

```js
import * as R from 'ramda'

const {identity} = R
R.map(identity, [1, 2, 3])
```

Desestructurar las importaciones de ramda * no necesariamente impide importar toda la biblioteca *. Puede seleccionar manualmente métodos como los siguientes, que solo tomarían las partes necesarias para que `identity` funcione:

```js
import identity from 'ramda/src/identity'

identity()
```

Sin embargo, los métodos *cherry-picking* son engorrosos. La mayoria de los bundlers como Webpack and Rollup ofrecen *tree-shaking* como una manera de borrar codios no usados y disminuir el tamaño del *bundle*, pero su rendimiento varía, discutido [aquí](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples). Aquí hay un resumen de la configuración óptima basada en la tecnología que está utilizando:

1. Webpack + Babel - use [`babel-plugin-ramda`](https://github.com/megawac/babel-plugin-ramda) to automatically cherry pick methods. Discussion [here](https://www.andrewsouthpaw.com/ramda-webpack-and-tree-shaking/), example [here](https://github.com/AndrewSouthpaw/ramda-webpack-tree-shaking-examples/blob/master/07-webpack-babel-plugin-ramda/package.json)
1. Webpack only - use `UglifyJS` plugin for treeshaking along with the `ModuleConcatenationPlugin`. Discussion [here](https://github.com/ramda/ramda/issues/2355), with an example setup [here](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/06-webpack-scope-hoisted/webpack.config.js)
1. Rollup - does a fine job properly treeshaking, no special work needed; example [here](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/07-rollup-ramda-tree-shaking/rollup.config.js)


Typings
-----------------

- [TypeScript](https://www.npmjs.com/package/@types/ramda)
- [Flow](https://github.com/flowtype/flow-typed/tree/master/definitions/npm/ramda_v0.x.x)




Traducciones
-----------------

- [Chinese(中文)](http://ramda.cn/)
- [Ukrainian(Українська)](https://github.com/ivanzusko/ramda)
- [Portuguese(BR)](https://github.com/renansj/ramda)
- [Russian(Русский)](https://github.com/Guck111/ramda)
- [Spanish(ES)](https://github.com/wirecobweb/ramda)



Agradecimientos
-----------------

Gracias a [J. C. Phillipps](http://www.jcphillipps.com) por el logo de Ramda.
Ramda logo artwork &copy; 2014 J. C. Phillipps. Licensed Creative Commons 
[CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/).
