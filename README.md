# kickoff_SASS
Guía para comenzar con la implementación de SASS en happyCode


KICKOFF SASS ( SassyCSS)



Qué es un Preprocesador CSS???

Un preprocesador de CSS se puede definir como una herramienta que nos permite escribir pseudocódigo CSS que luego será compilado con NODE.JS para convertirlo CSS tal y como lo conocemos de forma habitual.

Porque usar un Preprocesador CSS???

Posibilidad de añadir funcionalidades adicionales que no son posible de utilizar en archivos CSS tradicionales, como son el uso de variables y lógica condicional
Dispondremos de una hoja de estilos más limpia, consiguiendo a la vez que sea más eficiente y fácil de mantener
Ofrece la posibilidad de reutilizar mucho código, lo que se traduce en un ahorro de tiempo y trabajo
Los cambios serán mucho más rápidos, ya que únicamente deberemos cambiar el valor de alguna variable
Ayuda a crear código compatible con todos los navegadores, lo que supone una gran ayuda para los diseñadores de sitios web
Se crea una capa de abstracción, donde no trabajaremos directamente sobre nuestro archivo CSS, ofreciendo una mayor seguridad
Posibilidad de separación absoluta del proceso de desarrollo y producción


Principales Preprocesadores de la industria???

SASS, LESS, STYLUS

SASS → Sass tiene una gran comunidad de usuarios, una amplia documentación y recursos disponibles en línea. Ofrece una amplia funcionalidad con características como variables, anidamiento de selectores, mixins y más.
Tiene dos diferentes versiones, SASS y SassyCSS:

SASS → Extensión de los ficheros .sass. Se trata de Sass en su estado puro y original. Utiliza una sintaxis identada que deja de lado el uso de llaves ({ }) y el punto y coma (;) tras cada declaración. NO PERMITE EL USO DE CSS NORMAL en su código.
 
SCSS (SassyCss) → Extensión de los ficheros .scss . En este tipo puedes utilizar prácticamente todas las características del lenguaje, pero se mantiene una sintaxis igual al CSS tradicional. Es decir, en este tipo de archivos será necesario utilizar llaves ({ }) y el punto y coma (;) tras cada declaración. PERMITE EL USO DE CSS NORMAL en su código.

LESS → Antes muy usado, en la actualidad Less tiene menos características avanzadas en comparación con Sass. Su comunidad de usuarios puede ser más pequeña y tener menos recursos disponibles en línea.
STYLUS → Stylus puede tener una comunidad más pequeña en comparación con Sass y Less, lo que podría dificultar la búsqueda de soluciones específicas.


SASS EN APLICACIÓN HTML / JS

Instalación:

Dentro de nuestro proyecto → npm install -g sass
Una vez instalado creamos en nuestra carpeta styles de nuestro proyecto y dentro una carpeta src que contendrá nuestro fichero .scss.
Ejemplo: styles/src/input.scss
En el raíz de styles creamos nuestro fichero final .css
Ej: styles/output.css
Para poder empezar a utilizar sass tenemos que compilar el fichero .scss a css!! se puede hacer de dos maneras en nuestro terminal:

1.- Solo se ejecuta una vez: sass css/src/input.scss css/output.css 

2.- Procedo watch ( Será el usado ) permanece a la escucha para que cada vez que salvemos se compile el fichero .css: 

sass --watch css/src/input.scss css/output.css

Y Ya podremos empezar a picar nuestros estilos con SCSS.

Al compilar nuestros fichero por defecto nos crea un .map que es el "rastreo" de la ubicación de los ficheros css, para desactivar esta opción ponemos:

sass --no-source-map --watch css/src/input.scss css/output.css

SASS EN SINGLE PAGE APLICATION ( REACT / ANGULAR )

Instalación:

Una vez instalado vite en nuestra aplicación desde el terminal hacemos:
npm i :D sass
Esto nos creará la dependencia de SASS en nuestro package.json.
A partir de esto podemos crear nuestras estructura de carpetas de estilos en nuestro proyecto, existen muchas formas de estructurarlas, la mejor forma que he visto es la siguiente.:
Dentro de la carpeta src de vite creamos una carpeta Styles.
Dentro de Styles creamos el fichero padre de estilos llamado styles.scss. Este fichero nos servirá como “directorio” para modular todas las css de nuestra aplicación. Será asi:

	// BASE ( estilos base para toda la aplicación, colores, márgenes, padding, estilos de lista etc ..)
	  @import ‘./base/base’
	
	// COMPONENTES ( estilos de componentes )
	  @import ‘./components/navbar’
   
	// PAGES ( estilos de páginas )
    @import ‘./pages/home’


Una vez creado el fichero styles.scss procedemos a crear las carpetas dentro de styles → base, components y pages

En ellas iremos creando los ficheros de estilos que necesitemos.

Ej: Styles/base/_base.scss → Importante llamar al fichero con guión bajo ya que es un “convencionalismo” de la industria y nos ahorra poner las extensión .scss a la hora de importarlo ( véase arriba ).

Así lo haremos para todos los fichero de estilos que queramos crear en sus diferentes funcionalidades ( base, components, pages).


Una hecho esto podemos eliminar app.css index.css de nuestra aplicación…, solo tendremos que importar el fichero padre (styles.scss) desde main.jsx

import ‘./styles/style.css.


Y Ya podremos empezar a picar nuestros estilos con SCSS en nuestro Vite.

URLS DE CONSULTA:

https://sass-lang.com/guide/

https://codingpotions.com/sass/


NOTA: NO hace falta el proceso watch ya que vite lo tiene por defecto por estar construido en NODE.JS
HappyCodding.




