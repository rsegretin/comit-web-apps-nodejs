## JSON

* JSON significa **JavaScript Object Notation** (Notación de Objetos de JavaScript) y es un formato para intercambiar datos de forma simple
* Es fácil de leer y escribir
* En su estructura es muy parecido a un objeto literal de Javascript con algunas diferencias
* Los nombres de las propiedades se escriben entre comillas dobles y los valores de tipo string también

**Ejemplo:**
```js
let objetoEnFormatoJSON = { 
  "atributo": "valor", 
  "atributo1": 1, 
  "atributo2": [], 
  "atributo3": null, 
  "atributo4": false
};
```

* Javascript incluye un objeto `JSON` que tiene los métodos `stringify()` y `parse()`
  * **stringify:** permite pasar un objeto o valor de javascript al formato JSON
  * **parse:** toma una cadena de caracteres en formato JSON y lo transforma en un objeto de Javascript
* Gracias a estos 2 métodos se puede utilizar el formato JSON para intercambiar datos en formato de texto
* Teniendo una variable en formato JSON se accede a sus atributos de la siguiente manera:

**Ejemplo:**
```js
// Ejemplo stringify
const usuarix = {
  username: 'pepe',
  password: '12345',
  email: 'pepe@gmail.com',
  hijxs: ['maria', 'juan']
}

const usuarixJSON = JSON.stringify(usuarix); // retorna un JSON del objeto usuarix
console.log(usuarixJSON);
/*
{
  "username":"pepe",
  "password":"12345",
  "email":"pepe@gmail.com",
  "hijxs":["maria","juan"]
}
*/

// Ejemplo parse

const usuarixDeJSONaJS = JSON.parse(usuarixJSON); // retorna un objeto de Javascript
console.log(usuarixDeJSONaJS);

/*
{
  username: "pepe", 
  password: "12345", 
  email: "pepe@gmail.com", 
  hijxs: ["maria", "juan"]
}
*/
```

* En este ejemplo podemos ver que de forma muy fácil podemos transformar un objeto de Javascript a JSON y viceversa

#### Prácticas
[Ejercicio 51](../ejercicios/consignas/js-browser/ej51.md)

## AJAX
* AJAX significa **Asynchronous JavaScript and XML**.
* Es una forma de mandar y recibir datos sin tener que recargar la página.
* Utilizando AJAX podemos: 
  * Refrescar el contenido de una página sin recargarla, alterando dinámicamente su contenido (DOM)
  * Enviar información a un servidor y recibir una respuesta
* ECMAScript (Javascript) tiene un objeto llamado `XMLHttpRequest` que nos permite realizar llamados de AJAX
  * Su nombre, igual que la sigla AJAX, incluye "XML" porque es el formato en el que originalmente se manejaban los datos. Hoy día lo más habitual es usar JSON, pero también podemos encontrar el uso de XML o de datos en formato de "texto plano" (sin ningún formato específico).
  * Para disparar el pedido (request) vamos a utilizar dos métodos del objeto XMLHttpRequest: `open` para indicar la URL de destino y qué método HTTP utilizar (GET, POST, PUT, DELETE, etc.) y `send` que efectúa el request.
  * Para recibir la respuesta vamos a usar algún listener con un callback asociado a alguno de los eventos de retorno.
  * Uno de esos eventos es el `readystatechange` que nos permite manejar todo el ciclo de vida del request hasta obtener un response. Se dispara con cada cambio del "ready state", reflejado en la propiedad `readyState`, que contiene un número informando el estado del objeto:
    * 0 si no se inicializó
    * 1 si está cargando
    * 2 si ya se envió el pedido
    * 3 si esta descargando la respuesta
    * 4 si terminó
  * Si no necesitamos monitorear cada uno de esoso pasos, podemos agregar el listener al evento `load`, que se va a disparar cuando haya terminado de procesarse la respuesta.
  * Otra propiedad del objeto XMLHttpRequest es `status` y nos permite saber cual es el status code de la respuesta. Es un dato que tenemos que evaluar para saber si se pudo ejecutar correctamente la petición o no.
  * Si el `status` es 200 entonces significa que el pedido fue satisfactorio. Algunos status codes típicos de errores son 400, 401, 403, 404 y 500. Podemos encontrar una lista completa y detallada en https://developer.mozilla.org/es/docs/Web/HTTP/Status.
  * Para obtener el contenido de la respuesta utilizamos la propiedad `responseText`.
  * Si el retorno está en formato JSON, lo podemos convertir en un objeto de Javascript y utilizarlo en nuestro código. Si no hubo respuesta, será `null`.


**Ejemplo de request:**
```js
let xhr = new XMLHttpRequest();

xhr.addEventListener("readystatechange", function() {
  if (this.readyState == 4 && this.status == 200) {
    console.log(this.responseText);
  }
};

xhr.open("GET", "url", true);

xhr.send();
```

El mismo ejemplo pero con el evento "load"
```js
let xhr = new XMLHttpRequest();

xhr.addEventListener("load", function() {
  if (this.status == 200) {
    console.log(this.responseText);
  }
};

xhr.open("GET", "url", true);

xhr.send();
```

* Pueden leer más sobre AJAX en el [sitio de MDN](https://developer.mozilla.org/es/docs/AJAX)
* Pueden leer más sobre el objeto XMLHttpRequest en el [sitio de MDN](https://developer.mozilla.org/es/docs/Web/API/XMLHttpRequest)

#### Prácticas
[Ejercicio 52](../ejercicios/consignas/js-browser/ej52.md)

Más adelante pueden **investigar sobre el  método `fetch`** ([info en el sitio de MDN](https://developer.mozilla.org/es/docs/Web/API/Fetch_API/Utilizando_Fetch)), que utiliza una lógica llamada "promesas" para resolver tareas asincrónicas (como lo es una consulta AJAX).
