# React Essentials      
### Contenidos:

- [Javascript](#1.javascript)

- [JSX](#2.-jsx)

- [_create-react-app_](#3.-introducción-a-_create-react-app_)

- [Tu primera aplicación React](#4.-tu-primera-aplicación-react)

- [Componentes](#5.-componentes)

## 1. Javascript     
### 1.1 Variables    
Usamos **var**, **let** y **const** para declarar una variable. El alcance de var son las funciones, pero let y const son de alcance de bloque.     

### 1.2 Arrays     
En contraste a las variables, un arreglo puede almacenar multiples valores. Cada valor en un arreglo tiene un índice, y cada indice tiene una referencia a una dirección de memoria. Se puede acceder a cada valor del arreglo mediante el uso de su índice. El índice de un arreglo comienza en cero, y termina en n-1.    

Un arreglo puede ser una colección de distintos tipos, de datos ordenados y puede reordenarse. También permite almacenar datos duplicados o no almacenar dato alguno.   

#### Creando un arreglo    
Los arreglos se pueden crear de distintas formas. Es muy común usar const, en vez de let para declarar un arreglo, en este caso, no se podrá usar nuevamente el nombre del arreglo para crear variables.    
``` js
const arr1 = [] 
//creando un arreglo vacío.   
   
const arr2 = ['h','o','l','a'] 
//creando un arreglo con elementos.   
```
#### Métodos para manipular arreglos     
    
Existen diferentes métodos para manipular arreglos, Estos son algunos de los métodos más comunes:   
- **Array()**, crea un arreglo.      
- **length**, para saber el tamaño del arreglo.   
- **concat(arr)**, para concatenar dos arreglos.   
- **indexOf(n)**, para saber si un elemento está en el arreglo, entrega el índice en caso que esté, y en caso contrario, entrega -1.   
- **lastIndexOf(n)**, entrega el índice del último elemento que coincida con el parametro ingresado, si el parametro no se encuentra en el arreglo, entrega -1.   
- **slice(a,b)**, entrega una porción del arreglo. Recibe como parametros dos valores, el comienzo y el final.   
- **splice**,   
- **join**,   
- **toString**, convierte un arreglo en string.   
- **includes**,    
- **isArray**,   
- **fill**,    
- **push(a)**, agrega un elemento al final del arreglo.   
- **pop()**, remueve un elemento del final del arreglo.  
- **reverse()**, invierte el orden del arreglo.    
- **shift()**, remueve el primer elemento del arreglo.   
- **unshift(a)**, agrega un elemento al comienzo del arreglo.   

### 1.3 Condicionales    
Las declaraciones condicionales son usadas para hacer decisiones basadas en condiciones. Por defecto, las declaraciones en un script de Javascript son ejecutadas secuencialmente desde arriba hacia abajo.   
- if(condition){}
- if(condition){} else{}
- if(condition){} else if(condition){} else{}
- switch(case-value){case 1://break case 2: // break default: }
- ternary operator   

### 1.4 Loops    
En programación usamos diferentes tipos de loops para realizar tareas repetitivas. El loop se cumple hasta que la condición deje de cumplirse, pero a veces, nos gustaría interrumpirlo o saltar cierta iteración, por esta razón usamos 'break' para salir del loop y 'continue' para saltar una iteración. Javascript  tiene diferentes tipos de loops:   
- for
- while
- do while
- for of
- forEach
- for in

### 1.5 Alcance
La variable es una parte fundamental en la programación. Declaramos las variables para almacenar datos, pero estos pueden tener un alcance global, local o window.   
Cuando usamos let y const, el alcance es de bloque (local), sin embargo, si la variable es declarada fuera de los curly brackets ({}), la variable pasa a ser global.

### 1.6 Objetos
Todo puede ser un objeto. Los objetos tienen propiedades y las propiedades tienen valores, por lo que un objeto es un par clave-valor. El orden de la llave no está reservado o no hay orden. 

#### Creando un objeto
Para crear un objeto literal, usamos curly brackets.   

```js    
const person = {
    // objeto vacío
}     
const rectangle = { 
    length:20, 
    width:20,
}
```
#### Obteniendo valores de objeto
Podemos acceder a los valores de un objeto usando dos métodos:
- Usando **.** seguido del nombre clave.
- Usando square brackets
 
```js
const person = {
    firstName: 'Louis',
}
console.log(person.firstName)
console.log(person['firstName'])
```

#### Creando métodos objeto
Generalmente se emplean los métodos objeto dentro de la descripción del objeto con la finalidad de modificar u obtener los atributos del objeto.
Ej:  
```js
const person = {
    firstName = 'Louis',
    lastName = 'Litt',
    //Obteniendo información
    getFullName: function(){
        return `${this.firstName} ${this.lastName}`
    },
}
```
#### Métodos objeto
Existen diferentes métodos para manipular un objeto. Algunos de los más populares son:
- Object.assign
- Object.keys
- Object.values
- Object.entries
- hasOwnProperty

### 1.7 Funciones
Una función es un bloque de código reutilizable diseñado para realizar una tarea en específico. Una función es declarada con un nombre y seguido de un paréntesis (). El paréntesis puede tomar parámetros (llamados argumentos) o no. Para extraer valores de una función, esta debe tener **return**, y para obtener el valor debemos llamar o invocar a la funcion.   
Las funciones hacen el código, limpio y fácil de leer y testear, reutilizable, etc.   
Las funciones pueden ser declaradas o creadas de distintas maneras:
#### Declaración de funciones
```js
function functionName(){ // declaración
    // Lo que hace la función
}

functionName() // llamando a la función para que ejecute su trabajo.
```
- **Funciones de flecha:**
Las funciones de flecha o arrow function, tienen una sintaxis más corta que una expresión de función convencional, al sustituir la palabra function por => (fat arrow).
```js
const suma = (a,b) => a+b //Cuando la función es de una linea, su return es implícito
const resultado = suma(1,5) 
```
- **Funciones anónimas:**
Las funciones anónimas son aquellas que no tienen nombre.
```js
const fAnon= function(){
    console.log("soy una funcion anonima")
}
```
- **Funciones expresión:**
Las funciones expresión son funciones anónimas. 
Después de crear una funcion sin nombre, la asignamos a una variable, de esta forma, el valor que retorna la función es almacenado por la variable. 

```js
const square = function(n){
    return n*n
}
console.log(square(2)) // 4
```
- **Funciones autoinvocadas:**
Las funciones autoinvocadas son funciones anónimas que no necesitan ser llamadas para retornar un valor.
```js
;(function(n){
    console.log(n*n)
})(2) 
```

### 1.8 Funciones de alto nivel
Las funciones de alto nivel son fincione s que toman a otras funciones como sus parámetros o  que retornan a una función como valor de retorno.
La función pasada como parámetro es llamada _Callback_.   

```js
const callback = (n) => {
    return n ** 2
}
function cube(callback, n){
    return callback(n) * n 
}
```
#### Ejecutando actividades en tiempo real
- **setInterval:**
Podemos usar setInterval con funciones de alto nivel para hacer actividades continuamente en ciertos intervalos de tiempo. El método setInterval (globalscope) toma una función callback y la duración(tiempo) como parámetros, esta duración es en milisegundos y el callback será llamado en ese intervalo de tiempo.
```js
function sayHello(){ // funcion callback
    console.log('Hello') // acción de la funcion
}
setInterval(sayHello, 2000) //imprime hello cada 2 segundos
```
- **setTimeout:**
Podemos usar setTimeout con funciones de alto nivel para ejecutar acciones en algún tiempo futuro. El método toma una función callback y la duración como parámetros. La duracion es en milisegundos y la función callback espera esa cantidad de tiempo.

```js
function sayHello(){
    console.log('Hello')
}
setTimeout(sayHello,2000) //imprime hello después de esperar 2 segundos
```

### 1.9 Desestructuración y propagación
#### Desestructuración:
La desestrocturación es una forma de descomprimir arreglos y objetos, y asignarlos a una variable distinta. La desestructuración nos permite escriibir código limpio y legible.
- **desestructurar arreglos:**
Los arreglos son una lista de diferentes tipos de datos ordenados por su índice. 
Podemos acceder a cada ítem del arreglo utilizando su índice e iterando con un loop.
Si el tamaño del arreglo es pequeño es mejor acceder a sus elementos de la siguiente forma:

```js
const countries = ['Chile', 'Argentina', 'Perú']
const [chi,arg,pe] = countries
console.log(chi,arg,pe) // Chile, Argentina, Perú
```
Otros casos:

```js
const fullStack = [
    ['HTML','CSS','JS','React'],
    ['Node', 'Django', 'MongoDB']
]
const[frontend, backend] = fullstack
console.log(frontend,backend)
```
Y si no estamos interesados en cada uno de los ítems del arreglo, podemos omitir alguno usando una coma en ese índice.

```js
const countries = ['chile', 'argentina', 'peru', 'bolivia']
const [chi, arg, , bol] =  countries // se omite peru
```
También, podemos almacenar ciertos datos del arreglo en variables y el resto almacenarlo en un subarreglo
```js
const countries = [
    'Chile',
    'Argentina',
    'Peru',
    'Bolivia',
]
const [chi, ...rest] = countries
console.log(chi, rest) //Chile, ["Argentina","Peru","Bolivia"]
```
- **Desestructurar objetos:**
Consideremos el siguiente objeto:
```js
const rectangle = {
    width: 20,
    height: 10,
}
```
podemos acceder a los valores del objeto de la siguiente manera:
```js
let width = rectangle.width
let height = rectangle.height
// o también
let width = rectangle[width]
let height = rectangle[height]
```
Sin embargo, es posible acceder a estos valores desestructurando el objeto.
Cuando desestructuramos un objeto, el nombre de la variable debe ser exactamente la misma que el key del objeto.

```js
const rectangle = {
    width: 20,
    height: 10,
}
let { width, height } = rectangle
console.log(width, height, perimeter)
```
En este caso, perimeter tomará valor _undefined_, ya que no es key del objeto.

#### Operador de propagación(spread) o Rest
Cuando desestructuramos un arreglo usamos el operador de propagación(...) para obtener el resto de los elementos del arreglo.
Podemos copiar un arreglo con spread (...)
```js
const nums = [0,1,2,3,4,5,6,7,8,9]
const unidades = [...nums]
```
También, podemos copiar un objeto:
```js
const user = {
    name: 'James',
    age: '10 years',
    genre: 'Male',
}
const copiedUser = {...user}
```
# FALTA PROFUNDIZAR!!!!

### 1.10 Programación funcional
La _programación funcional_ nos permite escribir un código más corto, limpio, y también resolver problemas complejos que serían complejos de resolver de forma convencional.

#### 1. forEach
Usamos forEach cuando queremos iterar sobre un arreglo. forEach es una función de alto nivel que toma un callback como parámetro. El método se usa sólo con arreglos y se usa sólo cuando se está interesado en trabajar con cada uno de los elementos o índices del arreglo.
```js
//Ejemplo: imprimir el índice y el elemento del arreglo
const countries = ['Chile','Argentina','Peru']
countries.forEach((country, i) =>  console.log(i, country.toUpperCase()))
```
```sh 
0 "Chile"
1 "Argentina"
2 "Peru"
```
#### 2. map
Usamos el método map cuando deseamos modificar un arreglo. Usamos el método map sólo con arreglos, y este siempre retorna un arreglo.

```js
const countries = ['chile', 'china', 'peru', 'cuba']
const newCountries = countries.map(function(country){
    return country.toUpperCase()
})
console.log(newCountries)
```
De esta forma, podemos trabajar con arreglos sin utilizar ciclos for.

# FALTA PROFUNDIZAR!!!!

##### 3. filter
##### 4. reduce
##### 5. find
##### 6. findIndex
##### 7. some
##### 8. every


### 1.11 Clases
Javascript es un lenguaje con programación orientada a objetos. Todo en Javascript son objetos, con sus propiedades y métodos. **Creamos una clase para crear un objeto**. 
Una clase es como un objeto constructor, o un blueprint para crear objetos. Instanciamos una clase para crear un objeto. La clase define los atributos y comportamientos del objeto, mientras el objeto, en contraparte, representa la clase.

Una vez que creamos la clase, podemos crear un objeto de esta cuantas veces queramos. La creación de un objeto a partir de una clase se llama instanciación de clases.
#### Definiendo una clase
Para definir una clase en Javascript necesitamos la palabra clave **class**, el nombre de la clase en CamelCase y curly brackets.
```js
class ClassName{
    // codigo de clase 
}
```
#### Instanciación de clase
Significa crear un objeto a partir de una clase. Para esto necesitamos la palabra clave **new** y el nombre de la clase.
```js
class Person{ // Creamos una clase Person

}
const person = new Person() // Creamos un objeto persona
```
#### Constructor de clase
El constructor es una función incorporada que nos permite crear un blueprint para nuestros objetos. La función constructor comienza con la palabra clave **constructor*, seguido de un paréntesis. Dentro del paréntesis introduciremos las propiedades del objeto como parámetro. Usamos la palabra clave *this* para adjuntar los parámetros del constructor con la clase.

```js
class Person{
    constructor(firstName, lastName){
        console.log(this)
        this.firstName = firstName
        this.lastName = lastName
    }
}
const person = new Person()
console.log(person)
```
```sh
Person {} 
Person {firstName: undefined, lastName: undefined}
```
Cuando instanciamos, debemos entregar los valores de las propiedades.  
```js
const person1 = new Person('Pedro','Pérez')
console.log(person1)
```
```sh
Person {firstName:"Pedro", lastName:"Pérez"}
```
#### Métodos de clase
Métodos permiten trabajar con la información de nuestros objetos.
```js
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName
    this.lastName = lastName
  }
  getFullName() { // Método que obtiene un compuesto de dos key values
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
}
const person1 = new Person('Asabeneh', 'Yetayeh',)
console.log(person1.getFullName())
```
#### getter
Método que nos permite obtener los datos de un valor clave específico del objeto.
```js
class Person{
    constructor( firstName, lastName){
        this.firstName = firstName
        this.lastName = lastName
    }
    get getName(){
        return this.firstName
    }
}
const person1 = new Person('Pedro', 'Pérez')
console.log(person1.getName)
```
#### setter
Método que nos permite modificar un valor específico de algún key value del objeto. 
```js
class Person{
    constructor( firstName, lastName){
        this.firstName = firstName
        this.lastName = lastName
    }
    set getName(newName){
        this.firstName = newName
    }
}
const person1 = new Person('Pedro', 'Pérez')
person1.setName = 'Jaime'
```
#### Método static
La palabra reservada **static** define un método estático de una clase. Los métodos estáticos no son llamados en instancias de la clase. En vez, ellos son llamados por la clase misma. Estos a menudo son 
# falta profundizar!!!!


#### Herencia
Usando herencia podemos acceeder a todas las propiedades de la clase padre. Esto reduce repetición de código.
Si la clase Person es padre, entonces creemos una clase hijo, esta puede ser estudiante, maestro, programador, futbolista, etc.
```js
class Student extends Person{
    saySomething(){
        console.log("Soy el hijo de la clase padre Person")
    }
}
const s1 = new Student('Javier', 'Tapia')
console.log(s1.saySomething())
```
#### Métodos primordiales
# falta profundizar!!!!!

### 1.12 Document object Model (DOM)
El documento HTML está estructurado como un objeto Javascript. Cada elemento HTML tiene propiedades diferentes que pueden ayudarnos a manipularlo. Es posible obtener, crear, agregar o eliminar elementos HTML usando Javascript.

React no manipula directamente el DOM, a su vez, el DOM virtual de React se encargará de actualizar los cambios necesarios. Por lo tanto, no manipule directamente el DOM si está usando React. El único lugar donde debe trabajar con el DOM es en el archivo index.html.
React es una aplicacion de una sola página porque todos los componentes se mostrarán en la página index.html y no habrá ningún otro HTML en toda la aplicación React.


## 2. JSX
JSX son las siglas de Javascript XML. JSX nos permite escribit elementos HTML con código Javascript. Un elemento HTML tiene tags de apertura y cierre, contenido y atributos en el tag de apertura.
Sin embargo, algunos elementos HTML puede que no tengan contenido y tag de cierre, ellos son elementos autocerrados.
Para crear elementos HTML en React no debemos usar _createElement()_, a su vez, debemos usar elementos JSX. Por lo tanto, JSX hace sencilla la tarea de escribir y agregar elementos HTML en React. JSX será convertido a Javascript en el navevador usando un transcompilador - [babel.js](http://babeljs.io/).
Babel es una librería que transcompila JSX a Javascript puro.
```js
// Ejemplo de sintaxis JSX
const jsxElement = <h1>soy un elemento JSX</h1>
const data = <small>nov 8, 2020</small>
```
#### Elementos JSX
```js
const header = (
    <header>
        <h1>Título</h1>
        <h2>subtitulo</h2>
        <h3>subsubtitulo</h3>
        <p>parrafo</p>
        <small>8 oct, 2020</small>
    </header>
)
```
el elemento _header_ es un elemento principal para todos los elementos HTML internos y JSX debe estar envuelto por un elemento principal externo. Sin el elemento HTML _header_ u otro elemento HTML principal, el JSX anterior no es válido. 

#### Comentando un elemento JSX
```js
{ 
   /* Esto es un comentario */
}
```
#### Renderizando un elemento JSX
Para renderizar un elemento JSX a un documento HTML, debemos crear primero un index HTML. El index.html  será el único archivo HTML que tendrás en tu aplicación React. Por esta razón, decimos que cada aplicación React es una aplicación de una página.
Podemos empezar con React de dos formas.
1. usando create-react-app.
create-react-app crea una bandeja de salida estándar del proyecto React y, debido a eso, muchas personas tienen dificultades para comprender cómo funciona React.
    


2. Usando CDN(red de distribución de contenidos).
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>titulo de pagina</title>
  </head>

  <body>
    <div class="root"></div>

    <script></script>
  </body>
</html>
```
El index.html anterior tiene un div con la clase root y un script. El _div_ root es la puerta de enlace para conectar todos los componentes React al index.html. En el tag script escribiremos nuestro Javascript, pero el script _type_ será _babel_. Babel va a transpilar el react JSX a Javascript puro en el navegador. 
Añadiremos babel al script. Dentro de babel podremos escribir Javascipt, JSX y código React.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>titulo de pagina</title>
  </head>
  <body>
    <div class="root"></div>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
      // our code goes here
    </script>
  </body>
</html>
```
La librería de babel está enlazada a nuestro documento y ahora podemos hacer uso de ella. El siguiente paso es **importar React** y **ReactDOM** usando CDN o enlace. En orden para enlazar React y ReactDOM, vamos a adjuntar ambos paquetes desde CDN al body del index.html. Para testear si React está enlazado al index.html, podrías checkear usando _console.log(React)_ en la consola del navegador, deberías obtener un objeto. Si ves un objeto que contiene métodos React, entonces React está enlazado a tu proyecto mediante CDN.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>titulo de pagina</title>
  </head>

  <body>
    <div class="root"></div>

    <script
      crossorigin
      src="https://unpkg.com/react@16/umd/react.development.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
    ></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
      console.log(React)
    </script>
  </body>
</html>
```
Ahora index.html tiene todo lo que necesita para escribir código React.
Obtenemos el elemento root usando document.querySelect('.root') y asignemoslo a una variable llamada rootElement. Allí será el único lugar donde interactuaremos directamente con el DOM.

Ahora que conocemos sobre JSX y sus elementos, vamos a renderizar un elemento JSX en el navegador, para hacerlo necesitamos las librerías React y ReactDOM, también babel para transpilar el JSX a código Javascript.
El paquete ReactDOM tiene un método de renderizado. El método de renderizado toma dos argumentos: Un elemento JSX o componente y el documento Root. 
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>titulo de pagina</title>
  </head>
  <body>
    <div class="root"></div>
    <script
      crossorigin
      src="https://unpkg.com/react@16/umd/react.development.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
    ></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
      // para obtener el elemento root del html
      const rootElement = document.querySelector('.root')
      // Elemento JSX
      const jsxElement = <h1>I am a JSX element</h1>

      // Se renderiza el eleento JSX usando el paquete ReactDOM. ReactDOM tiene el método de renderizaje que toma dos argumentos.
      ReactDOM.render(jsxElement, rootElement)
    </script>
  </body>
</html>
```
Para renderizar más contenido, el elemento JSX debe tener más elementos HTML. Podemos crear un header, un título, subtitulo, parrafos, etc. Sin embargo, no debes olvidar que sólo podemos renderizar un elemento JSX a la vez.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>titulo de pagina</title>
  </head>
  <body>
    <div class="root"></div>
    <script
      crossorigin
      src="https://unpkg.com/react@16/umd/react.development.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
    ></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
      const rootElement = document.querySelector('.root')
      // JSX element
      const header = (
        <header>
          <h1>Welcome to 30 Days Of React</h1>
          <h2>Getting Started React</h2>
          <h3>JavaScript Library</h3>
          <p>Asabeneh Yetayeh</p>
          <small>Oct 2, 2020</small>
        </header>
      )
      ReactDOM.render(header, rootElement)
    </script>
  </body>
</html>
```
Creamos un elemento JSX que empaqueta todos los elementos HTML que deseamos, pero ¿Qué pasa con el footer o el main?
Para solucionar estos casos debemos aplicar el mismo principio.
```js
//Elemento JSX para el main
const main = (
  <main>
    <p>Este es un párrafo</p>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </main>
)
```
```js
// Elemento JSX para el footer
const footer = (
  <footer>
    <p>Copyright 2020</p>
  </footer>
)
```
Ahora que tenemos tres elementos JSX, debemos empaquetarlos en un elemento JSX padre o poniendolos en un array. Para incluir un elemento JSX dentro de otro se utilizan curly brackets, {} y es necesario llamar al elemento JSX dentro de estos.
```js
// Elemento JSX padre
const app = (
  <div>
    {header}
    {main}
    {footer}
  </div>
)
```
#### Style y className en JSX
Para agregar estilo a nuestros elementos JSX usamos inline style o className. Inyectamos style dentro del código usando curly brackets. Así, cada propiedad de CSS se vuelve una clave y cada valor de propiedad de CSS se convierte en un valor para el objeto.
```js
const header = (
  <header
    style={{ border: '2px solid orange', color: 'black', fontSize: '18px' }}
  >
    <h1>titulo</h1>
    <h2>subtitulo</h2>
    <h3>subsubtitulo</h3>
    <p>parrafo</p>
    <small>Oct 2, 2020</small>
  </header>
)
// También podemos escribirlo de esta manera
const style = { border: '2px solid orange', color: 'black', fontSize: '18px' }
const header = (
  <header style={style}>
    <h1>titulo</h1>
    <h2>subtitulo</h2>
    <h3>subsubtitulo</h3>
    <p>parrafo</p>
    <small>Oct 2, 2020</small>
  </header>
)
```
Para apuntar a un elemento HTML usamos un nombre tag, id, class, un atributo o otros métodos. Es muy común que la gente use class, en vez de id.
    
En elementos JSX usamos className, en vez de class porque class es una palabra reservada en Javascript, similar al caso htmlFor en vez de for.

Convengamos que id sea usado para referencias cuyo motivo sea distinto a dar estilo.   
[Ejemplo de pagina](/examples/add-style.html/)

Hasta el momento hemos usado datos estáticos en los elementos JSX, pero también podemos pasar diferentes tipos de datos como datos dinámicos. Los datos dinámicos pueden ser string, números, booleanos, matrices u objetos.
Para inyectar datos a un JSX usamos curly brackets.
```js
const welcome = 'Bienvenido'
const title = 'Aprendiendo React'
const subtitle = 'Libraria Javascript'
const authorFirstName = 'Ricardo'
const authorLastName = 'Coronado'
const date = 'Oct 10, 2020'
// Elemento JSX, header
const header = (
  <header>
    <div className='header-wrapper'>
      <h1>{welcome}</h1>
      <h2>{title}</h2>
      <h3>{subtitle}</h3>
      <p>
        Instructor: {authorFirstName} {authorLastName}
      </p>
      <small>Date: {date}</small>
    </div>
  </header>
)
```
Podemos inyectar strings, números, booleanos y arreglos al JSX, pero no podemos inyectar directamente un objeto. Debemos extraer los valores del objeto o destructurar su contenido antes de inyectar los datos al elemento JSX. 
Para darle formato a la lista de elementos debemos modificarlo antes de inyectarlo a JSX. Podemos modificar un arreglo usando _map_. Como desarrollador de React deberás adquirir un buen entendimiento sobre programación funcional (map, filter, reduce, find, some, every, etc).
```js
const techs =['HTML','CSS','Javascript']
const techFormatted = techs.map((tech)=><li>{tech}<li>)
```
El siguiente ejemplo muestra una lista de elementos con el formato apropiado.
![ejemplo](/examples/002-add-format.html)
Sin embargo, tenemos un warning en consola que dice que cada list child debería tener una única key.   
Asignemos a cada ítem una key única para remover el warning.
```js
const techs = ['HTML','CSS','Javascript']
const techFormatted = tech.map((tech)=> <li key={tech}>{tech}</li>)
```
## 3. Introducción a _create-react-app_ 
En el capítulo 2 aprendimos sobre JSX y accedimos a los paquetes React y ReactDOM usando CND. Sin embargo, usaremos el paquete create-react-app para generar un proyecto React. El porqué radica en que nos permite ahorrar bastante tiempo y trabajo, ya que create-react-app tiene todo lo que necesitamos para desarrollar.    

Partiremos explicando cada una de las herramientas que lo componen.

### Node
Node es sistema en tiempo de ejecución de Javascript que permite a Javascript ejecutarse en el servidor. Una aplicación React comienza por defecto en localhost 3000. Create-react-app tiene configurado un server node para la aplicación React. Es por esto que necesitamos node y sus módulos.    
Para saber la versión de node que tienes instalada en tu computador, deberás abrir un terminal y escribir lo siguiente:
```sh
$ node -v
```
### Módulo
Una o varias funciones que pueden ser exportadas e importadas cuando sea necesario, pueden incluirse en un proyecto. En React, no usamos link para acceder a módulos o paquetes, sino que lo importamos
```js
//math.js
export const addTwo = (a,b)=> a+b
export const multiply = (a,b)=> a*b
export const substract = (a,b)=> a-b

export default (function doSomeMath()){
    return{
        addTwo,
        multiply,
        subtract,
    }
})()
```
Ahora, importemos los módulos _math.js_ en otro archivo:
```js
// index.js
// Para importar doSomeMath desde math.js con o sin extensión
import doSomeMath from './math.js'
// Para importar los otros módulos
// Ya que los otros módulos no fueron umportados como default, debemos destructurar
import { addTwo, multiply, subtract} from './math.js'
import * as everything from 'math.js' //Para importar todo lo restante
console.log(addTwo(2,5))
console.log(doSomeMath.addTwo(5,5))
console.log(everything)
```
### Paquetes
Un paquete es un módulo o colección de módulos. React, ReactDOM son paquetes.
### Node Package Manager (NPM)
NPM nos permite usar, crear y destribuir paquetes Javascript.
### Extensiones de VSCode útiles
- Prettier
- ESLint
- Bracket Pair Colorizer
- ES7 React/Redux/GraphQL/React-Native snippets
### Create React App
Para crear un proyecto React puedes usar una de las siguientes vías:
Abres un terminal y escribes el siguiente comando:
```sh
$ npx create-react-app nombre-proyecto
```
Pero si no te gusta escribir npx cada vez que creas un proyecto, deberás instalar el paquete create-react-app gobalmente en tu computador usando el siguiente comando:
```sh 
$ npm install -g create-react-app
$ create-react-app nombre-proyecto
```
## 4. Tu primera aplicación React
Primero deberás trasladarte por terminal a la carpeta donde deseas almacenar tu proyecto. Luego:
```sh
$ npx create-react-app nombre-proyecto
$ cd nombre-proyecto
$ npm start
```
Ahora tu aplicación debería correr en localhost 3000. Modifica App.js escribiendo algún texto, verás que la página muestra las modificaciones instantáneamente.   

Para detener el server, presiona Ctrl + C en el terminal.  
    
Analicemos el template que ha creado create-react-app. En el template hay tres carpetas: node_modules, public y src. En adición, hay .gitignore, README.md, package.json y yarn.lock o package-lock.json.   
- node_modules, guarda todos los paquetes necesarios para las aplicaciones React.
- Public
    - index.html, es el único archivo HTML que tenemos en la aplicacion.
    - favicon.ico, un archivo icon.
    - other images, open graph images(son imagenes que estás visibles cuando un link comparte en redes sociales).
    - robots.txt, información, si es que la página permite web scraping.
- src
    - App.css y index.css, son archivos css
    - index.js, un archivo js que nos permite conectar todos los componentes con el index.html
    - App.js, un archivo donde usualmente se importa la mayoria de los componentes de presentación
    - serviceWorker.js, es usado para agregar funciones de aplicaciones web progresivas.
    - setupTest.js, para escribir casos de testing. 
- package.json, lista de paquetes que la aplicación usa.
- .gitignore, permite que archivos y carpetas no sean pusheadas a Github
- README.md, archivo Markdown para escribir documentación.
- yarn.lock o package-lock.json, significa bloquear la version del paquete.    

Lo siguiente que vamos a hacer es borrar todos los archivos que no vayamos a necesitar por el momento.
De la carpeta public, borraremos todos los archivos, con excepción de index.html. De la carpeta src, borraremos todo, excepto index.js.   
    
Escribamos en el archivo index.js. Primero que todo debemos importar React y ReactDOM. React nos permite escribir código JSX y ReactDOM para renderizar el código JSX en el DOM. ReactDOM tiene un método de renderizaje.

```js 
// En index.js
import React from 'react'
import ReactDOM from 'react-dom'

const jsxElement = <h1> Este es un elemento JSX </h1>
const rootElement = document.getElementById('root')

ReactDOM.render(jsxElement, rootElement)
```
Y en index.html escribiremos lo siguiente:
```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      href="https://fonts.googleapis.com/css?family=Montserrat:300,400,500|Roboto:300,400,500&display=swap"
      rel="stylesheet"
    />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <title>mi aplicacion react</title>
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```
Para ejecutar tu aplicación debes ejecutar el siguiente comando:
```sh
$ npm start
```
Escribamos más elementos JSX y para luego renderizarlos en el navegador.
```js
const header = (
    <header>
        <h1>Bienvenido</h1>
        <h2>Iniciando el desarrollo con React</h2>
        <h3>Una librería de Javascript</h3>
    </header>
)
const main = (
  <main>
    <p>Prerequisite to get started react.js:</p>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </main>
)
const footer = (
  <footer>
    <p>Copyright 2020</p>
  </footer>
)
const app = (
  <div>
    {header}
    {main}
    {footer}
  </div>
)
```
### Importando imgs, video, audio, etc
Para importar imágenes  debes crear una carpeta en src y guardar imágenes adentro. Luego, importas:
```js
import funnyImage from './images/funnyimage.png'
```
Luego, para utilizarla, sólo basta con llamar su nombre:

```js
const user = (
  <div>
    <img src={funnyImage} alt="funny image"/>
  </div>
)
```
## 5. Componentes
Un componente React es una pequeña pieza reusable de código, es la responsable de la aplicación UI. Una aplicación React es un cúmulo de componentes y usamos funciones o clases en Javascript para hacerlas.     
Si usamos una función, el componente será un componente funcional, pero si usamos una clase, el componente será 'basado en clases'.    
Los componentes pueden ser: 
- Componentes funcionales/ Componentes de presentación / Componente sin estado / Componentes tontos
- Componentes de clase / Componente contenedor / Componente con estado / Componente inteligente

La clasificación de componentes anterior no sirve para las nuevas versiones de React, pero si, es buna para conocer la definición formal y cómo funcionaban las versiones anteriores.    
De esta forma, cambiemos todo el JSX a componentes. Las componentes en React son funciones o clases de Javascript que retornan JSX. El nombre del componente debe comenzar con una letra mayúscula y, en caso de ser un nombre compuesto de dos palabras, debe ir en formato camelcase. 

### Visión general de las componentes
Recordemos las funciones y clases de Javascript.
```js
// FUNCIONES!!!
const getUserInfo = (firstName, lastName, country, title, skills) => {
  return `${firstName} ${lastName} , a ${title} developer based in ${country}.
  He knows ${skills.join(
    ','
  )}`
}
// Y cuando llamamos a esta función necesitamos parámetros
const skills = {'HTML', 'CSS', 'JS', 'React'}
console.log(
  getUserInfo('Ricardo', 'Coronado', 'Chile', 'Fullstack developer', skills)
)
```
```js
// CLASES
class Parent {
  constructor(firstName, lastName, country, title){
    this.firstName = firstName
    this.lastName  = lastName
    this.country = country
    this.title = title
  }
  getPersonInfo(){
    return `${this.firstName} ${this.lastName}, a ${this.title} developer base in ${this.country}`
  }
  parentMethod(){
    // code goes here 
  }
}
const p1 = new Parent('Ricardo','Coronado','Chile','Fullstack developer')
class Child extends Parent{
  constructor(firstName, lastName, country, title, skills){
    super(firstName, lastName, country, title)
    this.skills = skills
    // vinculamos los parámetros secundarios con la palabra clave this a este objeto secundario
  }
  getSkills(){
    let len = this.skills.length
    return len > 0 ? this.skills.join(' ') : 'No skills found'
  }
  childMethod(){
    // code goes here
  
  }
}
const skills = {'HTML', 'CSS', 'JS', 'React'}
const child = new Child(
  'Ricardo',
  'Coronado',
  'Chile',
  'Fullstack developer',
  skills
)
```
### Creando componentes react
Usando una función de Javascript, podemos hacer componentes funcionales React.
``` js
// sintaxis de componente react
// puede ser una función de flecha, una función declaración o expresion
const jsx = <tag> Content </tag>
const ComponentName = () => {
  return jsx
}
```
La siguiente expresión es un elemento JSX
```js
// Elemento JSX, header
const header = ()
  <header style={headerStyles}>
    <div className='header-wrapper'>
      <h1> Bienvenido </h1>
      <h2> Iniciando React </h2>
      <h3> Libreria javascript </h3>
      <p> Ricardo Coronado </p>
      <small> oct 17, 2020 </small>
    </div>
  </header>
)
//componente react
const Header = () => {
  return header
}
```
### Renderizando componentes
Cambiemos todo el JSX que tenemos y generemos componenetes de estos. Cuando llamamos a un elemento JSX usamos curly brackets y cuando llamamos a componentes lo hacemos de la siguiente forma: <ComponentName />. Si pasamos un atributo, cuando llamamos al nombre del componente, lo llamamos props (<ComponentName propsName == {'data-type'} />).      
Vamos a renderizar primero el componente _header_.
```js 
//index.js
import React from 'react'
import ReactDOM from 'react-dom'

// Header Component
const Header = () => (
  <header>
    <div className='header-wrapper'>
      <h1> Bienvenido </h1>
      <h2> Iniciando React </h2>
      <h3> Libreria javascript </h3>
      <p> Ricardo Coronado </p>
      <small> oct 17, 2020 </small>
    </div>
  </header>
)

const rootElement = document.getElementById('root')
// we render the JSX element using the ReactDOM package
ReactDOM.render(<Header />, rootElement)
```
Ahora, creemos un componente App, esto va a envolver el Header, Main y Footer. Luego, el componente App va a renderizar el DOM.

```js
// index.js
import React from 'react'
import ReactDOM from 'react-dom'
import ricardoImage from './images/ricardo.png'

// Header Component
const Header = () => (
  <header>
    <div className='header-wrapper'>
      <h1>Hola</h1>
      <h2>Aprediendo React</h2>
      <h3>Una libreria de JavaScript</h3>
      <p>Ricardo Coronado</p>
      <small>Oct 3, 2020</small>
    </div>
  </header>
)

// User Card Component
const UserCard = () => (
  <div className='user-card'>
    <img src={ricardoImage} alt='ricardo image' />
    <h2>Ricardo Coronado</h2>
  </div>
)

// TechList Component
const TechList = () => {
  const techs = ['HTML', 'CSS', 'JavaScript']
  const techsFormatted = techs.map((tech) => <li key={tech}>{tech}</li>)
  return techsFormatted
}

// Main Component
const Main = () => (
  <main>
    <div className='main-wrapper'>
      <p>Prerequisitos para aprender react.js:</p>
      <ul>
        <TechList />
      </ul>
      <UserCard />
    </div>
  </main>
)

// Footer Component
const Footer = () => (
  <footer>
    <div className='footer-wrapper'>
      <p>Copyright 2020</p>
    </div>
  </footer>
)

// The App, or the parent or the container component
const App = () => (
  <div className='app'>
    <Header />
    <Main />
    <Footer />
  </div>
)

const rootElement = document.getElementById('root')
// we render the App component using the ReactDOM package
ReactDOM.render(<App />, rootElement)
```
### Inyectando datos a JSX en un componente React
