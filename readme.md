# Módulos en JavaScript (import/export) #

## Antecedente sobre módulos ##
Al principio de la revolución de JavaScript, los programas que se escribían, comenzaron siendo bastante pequeños para hacer pequeñas tareas, ya que no habia tanta interactividad en las páginas web como la hay ahora. A medida que pasaron los años, los programas fueron siendo cada vez más complejos y completos, por lo cual se necesitaba de mejoras(Javascript).

Por lo tanto, en la nueva actualización de ES6, se agregaron los módulos en JavaScript, el cual permitia importar elementos separados del archivo principal.

## ¿Qué son los módulos en JavaScript? ##
Los Módulos, son trozos de código que podemos escribir en ficheros independientes. (Documentos independientes que se intercambian y comparten contenido)

Pueden tener clases, funciones, objetos, datos primitivos, etc.

Esta característica se incorporó en ES6.

Tiene soporte total menos en Internet Explore, lo cual no debería de preocuparnos.

## ¿Cómo es su funcionamiento? ##
Primero que nada, antes de escribir código en JavaScript, debemos de enlazar los archivos con nuestro index.html

Para que funcione los módulos, debemos en nuestra etiqueta <script></script> utilizar el atributo ``<script src="archivo.js" type="module"></script>``

Luego de esto, los módulos podrán funcionar, de lo contrario, el programa dará error.

## Cómo exportar código ? ##
Para exportar una parte de un módulo, utilizamos la palabra clave "export", de modo que indicamos que se puede utilizar fuera.

``export``

Exporta datos (variables, funciones, clases...) del fichero actual hacia otros que los importen.


## ¿Cómo importamos código? ##
Para importar código mediante un módulo, utilizamos la palabra reservada "import", es decir, que podemos usar código exportado de otro archivo.

``import``

Importa datos (variables, funciones, clases...) desde otro fichero .js al actual.

### Ejemplo básico ###

````
//main.js
import saludar , {PI} from "./constantes.js"

console.log(PI);
//3.141592653589793
````

````
//constantes.js
export const PI = PI;

export default function saludar() {
    console.log("Hola Módulos +ES6");
} 
````

Como se puede observar, el código que queremos utilizar en otro archivo js tiene la palabra "export". Cuando queremos utilizar ese código en nuestro archivo a pasar colocamos la palabra reservada "import"

Es importante cuando colocamos nuestro archivo.js que coloquemos el (./) ya que esto provoca que el archivo relativo no de errores.



## Diferencias entre módulos y scripts estándar ##
- Los módulos solo se ejecutan una vez, incluso si se les ha hecho referencia en varias etiquetas <script> 
-  las características del módulo se importan al alcance de un solo script — no están disponibles en el alcance global. Por lo tanto, solo podrás acceder a las funciones importadas en el script en el que se importan y no podrás acceder a ellas desde la consola de JavaScript, por ejemplo. Seguirás recibiendo errores de sintaxis en DevTools, pero no podrás utilizar algunas de las técnicas de depuración que esperabas utilizar.

## Exportaciones predeterminadas vs. exportaciones con nombre ##

### export predeterminado (default) ###
Diseñado para que un módulo proporcione una función predeterminada.

Cabe destacar que solo se puede utilizar una vez por archivo.

En conclusión la forma **export default** declara un elemento y lo añade como módulo de exportación por defecto.

Su sintaxis en clases y funciones expresadas:

````
//constantes.js
export default function saludar() {
    console.log("Hola Módulos +ES6");
} 

//main.js
import saludar from "./constantes.js"
````

Su sintaxis en los demás tipos:

````
const PI = Math.PI;
export default PI;
````

Todo esto se debe al Hoisting (Cómo funcionan los contextos de ejecución en JS) que tiene JavaScript. Lo manda todo arriba.

### export con nombre ###
En este caso, importamos un bloque de texto normal.

Su sintaxis es:

````
//constantes.js
export let user = "Argen";

//main.js

import {user} from "./constantes.js";
````

## Ejemplo más completo ##

````
<!-- HTML -->
    <script src="js/main.js" type="module"></script>

<!-- CONSTANTES.JS -->
export let user = "Joaquin";
let password = "qwerty";

export default function saludar() {
    console.log("Hola Módulos +ES6");
}

<!-- MAIN.JS -->
import saludar , {user, password} from "./constantes.js";

console.log(`My name is ${user} and my password is ${password}`);
console.log(saludar);
````

## Importación de todo mediante un alias (Crear un Objeto module) ##
Esta forma, nos permite poder exportar todas las características que hay dentro de un modulo.

La sintaxis es de la siguiente manera:

````
// main.js
import * as AliasCreado from './constantes.js';
console.log(`My name is ${user} and my password is ${password}`);

// constantes.js
export let user = "Joaquin";
export let password = "qwerty";
````

Esto hace que se tomen todas las exportaciones disponibles dentro de en este caso, el archivo constante.js dandole su propio espacio de nombres.


