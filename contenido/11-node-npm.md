# Proyectos en Node.js: NPM y package.json

## NPM, módulos para Node.js

El entorno de Node.js, a diferencia del entorno del navegador, nos permite utilizar módulos (paquetes) _instalados_ como agregados a nuestro código. Estos módulos pudieron ser desarrollados por cualquier persona y servirnos para solucionar alguna necesidad específica sin tener que escribir todo el código que sería necesario, algo especialmente útil cuando se trata de funcionalidades complejas.

Estos módulos, a su vez, tienen su propia _evolución_, y van incorporando nuevas funcionalidades y corrigiendo errores con el tiempo. Más aún, esos módulos la mayoría de las veces funcionan incorporando a su vez otros módulos (lo que llamamos "dependencias"). Podemos imaginar lo rápido que puede complejizarse la instalación de esos módulos si tenemos que estar segurxs de instalar a su vez las dependencias y tener que estar cuidando de qué versión de cada cosa se instala para evitar incompatibilidades.

Bueno, afortunadamente no tenemos que preocuparnos por nada de eso porque junto con Node se instala una aplicación que es un **Manejador de Paquetes de Node**, más conocido por su nombre en inglés _Node Package Manager_, pero especialmente por sus siglas: **NPM**.

NPM es quien se encarga de descargar y mantener actualizados todos los módulos que querramos usar, así como sus dependencias. ¿Y de dónde desacarga esos módulos? De un gran repositorio, que podemos navegar y consultar muy fácilmente desde [el sitio de NPM](https://www.npmjs.com/).

## Crear un proyecto en NPM

Pero, ¿cómo hace NPM para llevar el control de las librerías que descargamos, saber que son parte de nuestro proyecto y mantenerlas actualizadas?. Para que esto sea posible, tenemos que indicar a NPM que estamos trabajando en un proyecto que queremos que esté bajo su órbita de control. Para esto, en una consola del sistema operativo (cmd, bash, PowerShell, etc.), desde la carpeta raíz de nuestro proyecto, utilizamos el comando `init` de npm:

```bash
npm init
```

Si lo escribimos así, va a iniciar una serie de preguntas, a las que podemos dar ENTER para que asuma los valores default que nos va a aclarar entre paréntesis, o ponerle valores distintos si así lo quisiéramos. Una vez finalizado el "cuestionario" nos va a presentar toda esa información como un JSON y nos va a preguntar si está bien. Si confirmamos, toda esa información, ese JSON que vimos, se va a guardar en un archivo que siempre tiene el mismo nombre y que NPM usa para centralizar TODA la información de nuestro proyecto: el archivo `package.json`. Ese archivo puede tener un aspecto como este:

```json
{
  "name": "web-server-test",
  "version": "1.0.0",
  "description": "Primer ejemplo de web server con Express",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "author": "",
  "license": "ISC"
}
```

## Instalación de módulos

Si nuestro proyecto requiere la instalación de módulos, podemos utilizar el comando `install` de NPM para agregarlos, identificándolos por el nombre del módulo. Por ejemplo, si queremos instalar el paquete de Express.js (una librería para servidores web, explicada más adelante), lo hacemos de la siguiente manera:

```bash
npm install express
```

Así le indicamos a NPM que instale el paquete de Express, y por defecto eso también significa que lo agregue como dependencia de nuestro proyecto. El package.json ahora se verá de esta forma:

```json
{
  "name": "web-server-test",
  "version": "1.0.0",
  "description": "Primer ejemplo de web server con Express",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1"
  }
}
```

La sección "dependencies" del package.json guardará la lista de módulos instalados y la versión que se instaló.

También se va a crear un archivo `package-lock.json` que no debemos modificar y que npm utiliza para saber qué versiones de cada módulo se instalaron para garantizar compatibilidad.

## Actualización y borrado de módulos

En cualquier momento, en la ruta donde se encuentra el package.json, podemos ejecutar el comando `npm update` para actualizar los módulos a la versión más actual (hasta dodne cumpla las *condiciones de actualización* que se hayan definido, que se indican con símbolos en la versión del módulo -para más datos leer https://semver.npmjs.com/-).

Si un módulo no está instalado, `npm update` tiene el mismo efecto que `npm install` (es decir, instala el módulo).

El comando para eliminar un módulo descargado (y su referencia en package.json) es `npm install <nombre_del_modulo>`.

## Utilización de módulos instalados

Instalarnos un módulo nos copia localmente todo el código del módulo en cuestión (y de sus dependencias). Pero para poder utilizarlo, tenemos que "traernos" ese módulo (en nuestra jerga, **importarlo**). En Node lo podemos hacer con la función `require`:

```js
const moduloImportado = require(`<nombre-del-modulo>`);
```

obteniendo en la constante `moduloImportado` lo que sea que "exporta" por defecto ese módulo. Esto hay que conocerlo para cada módulo/librería que utilicemos. Más adelante veremos el ejemplo de Express.

En versiones más nuevas de Node (y con cierto tipo de configuración del proyecto) se puede utilizar `import` para importar módulos.