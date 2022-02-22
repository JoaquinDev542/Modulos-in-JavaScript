# Módulos en JavaScript (import/export) #

## Antecedente sobre módulos ##
Al principio de la revolución de JavaScript, los programas que se escribían, comenzaron siendo bastante pequeños, para hacer pequeñas tareas, ya que no habia tanta interactividad en las páginas web como la hay ahora. A medida que pasaron los años, los programas fueron siendo cada vez más complejos y completos, por lo cual se necesitaba de mejoras(Javascript).

Por lo tanto, en la nueva actualización de ES6, se agregaron los módulos en JavaScript, el cual permitia importar elementos separados del archivo principal.

## ¿Qué son los módulos en JavaScript? ##
Los Módulos, son trozos de código que podemos escribir en ficheros independientes. (Documentos independientes que se intercambian y comparten contenido)

Pueden tener clases, funciones, objetos, datos primitivos, etc.

Esta característica se incorporó en ES6.

Tiene soporte total menos en Internet Explore, lo cual no debería de preocuparnos.

Nos permite 

## ¿Cómo es su funcionamiento? ##
Primero que nada, antes de escribir código en JavaScript, debemos de enlazar los archivos con nuestro index.html

En la etiqueta para que funciones los módulos debemos de utilizar un atributo, este es el atributo type ``<script src="main.js" type="module"></script>``

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
import {PI} from ./constantes.js

console.log(PI);
//3.141592653589793
````

````
//constantes.js
export const PI = PI;
````

Como se puede observar, el código que queremos utilizar en otro archivo js tiene la palabra "export". Cuando queremos utilizar ese código en nuestro archivo a pasar colocamos la palabra reservada "import"

## Sintaxis del import ##
````
import {nombresDeClaseEtc} from archivo.js
````

### Aplicar el Módulo a tu HTML ###
La sintaxis en la etiqueta ``<script></script>`` será la siguiente:

````
<script src="main.js" type="module"></script>
````

## Diferencias entre módulos y scripts estándar ##
- Los módulos solo se ejecutan una vez, incluso si se les ha hecho referencia en varias etiquetas <script> 
-  las características del módulo se importan al alcance de un solo script — no están disponibles en el alcance global. Por lo tanto, solo podrás acceder a las funciones importadas en el script en el que se importan y no podrás acceder a ellas desde la consola de JavaScript, por ejemplo. Seguirás recibiendo errores de sintaxis en DevTools, pero no podrás utilizar algunas de las técnicas de depuración que esperabas utilizar.
