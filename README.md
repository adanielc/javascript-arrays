# javascript-arrays

--------------------------------

Una de las cosas que usualemente se olvida al ser de un perfil de backend son los metodos mas comunes de JavaScript, por eso hice un resumen de los metodos de Array de JavaScript con varios ejemplos.

--------------------------------

### Pop
Devuelve el último elemento de un array y lo elimina del array. El array original es modificado.

```javascript
const apple = ["iMac", "iMac Pro", "Mac Mini", "Mac Studio"];
const lastElement = apple.pop()
console.log(lastElement)
console.log(apple)
```
El resultado sería: 

```javascript
'Mac Studio'
[ 'iMac', 'iMac Pro', 'Mac Mini' ]
```

### Push
Añade un elemento al final del array y devuelve la nueva longitud del Array

```javascript
const apple = ["iMac", "iMac Pro", "Mac Mini", "Mac Studio"];
const value = apple.push("iPad")
console.log(value)
```
El resultado sería: 

```javascript
5
```

### Shift
Elimina el elemento 0 del Array. Devuelve el elemento.

```javascript
const shift = apple.shift();
console.log(shift)
console.log(apple)
```
El resultado sería: 

```javascript
'iMac'
[ 'iMac Pro', 'Mac Mini', 'Mac Studio' ]
```

### Unshift
Añade un elemento al principio del Array y devuelve la nueva longitud del Array

```javascript
const unshift = apple.unshift("Apple Watch")
console.log(unshift)
console.log(apple)
console.log(apple.indexOf('Apple Watch'))
```
El resultado sería: 

```javascript
5
[ 'Apple Watch', 'iMac', 'iMac Pro', 'Mac Mini', 'Mac Studio' ]
0
```

### Concat
Devuelve un Array nuevo concatenando dos o más Arrays.

```javascript
const ipad = ["iPad air", "iPad Pro", "iPad mini"];
const mac = ["Macbook", "Macbook Pro", "Mac Mini"];
const iphone = ["iPhone 13", "iPhone 13 Pro"];
const appleProducts = ipad.concat(mac, iphone);
console.log(appleProducts);
```
El resultado sería: 

```javascript
[ 'iPad air', 'iPad Pro', 'iPad mini', 'Macbook', 'Macbook Pro', 'Mac Mini', 'iPhone 13', 'iPhone 13 Pro' ]
```

### Splice
Sirve para añadir elementos en una posicion especifica en el array y podemos eliminar elementos del Array. 

Parámetros: <br>

Array.splice(start, deleteCount, item1, item2,...itemN)<br>

start: Donde se va a empezar a insertar en el Array, la cuenta empieza en 0<br>
deleteCount: la cantidad de elementos que se van a eliminar, a partir de el valor de start. 

devuelve los elementos Eliminados
Modifica el Array original. 

Ejemplo sin eliminar: 

```javascript
console.log(apple)
apple.splice(0,0,"iPod")
console.log(apple)
```
El resultado sería: 

```javascript
[ 'iMac', 'iMac Pro', 'Mac Mini', 'Mac Studio' ]
[]
[ 'iPod', 'iMac', 'iMac Pro', 'Mac Mini', 'Mac Studio' ]
```

No retorna nada, ya que no se ha eliminado nada.

Ejemplo sin eliminar: 

```javascript
console.log(apple)
apple.splice(0,2,"iPod")
console.log(apple)
```
El resultado sería: 

```javascript
[ 'iMac', 'iMac Pro', 'Mac Mini', 'Mac Studio' ]
[ 'iMac', 'iMac Pro' ]
[ 'iPod', 'Mac Mini', 'Mac Studio' ]
```
Devuelve los elementos eliminados.

### forEach

Recorre cada elemento del array. No devuelve nada

Parámetros:

```javascript
apple.forEach((value, index, array)=> {
  console.log("value "+ value)
  console.log("index "+ index)
  console.log("array "+ array)
})
```

value: El valor de esa iteración<br>
index: El índice del array<br>
array: Todo el Array, es util si necesitamos comparar algo o si no tenemos el array en el contexto de la función

El resultado sería: 

```javascript
'value iMac'
'index 0'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value iMac Pro'
'index 1'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value Mac Mini'
'index 2'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value Mac Studio'
'index 3'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
```

### Map

Recorre cada elemento del array. Devuelve un nuevo array con lo que se evalue en la funcion dentro del Map y puedes encadenar más de un Map

Parámetros:

```javascript
const result = apple.map((value, index, array)=> {
  console.log("value "+ value)
  console.log("index "+ index)
  console.log("array "+ array)
})
```

value: El valor de esa iteración<br>
index: El índice del array<br>
array: Todo el Array, es util si necesitamos comparar algo o si no tenemos el array en el contexto de la función

El resultado sería: 

```javascript
'value iMac'
'index 0'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value iMac Pro'
'index 1'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value Mac Mini'
'index 2'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
'value Mac Studio'
'index 3'
'array iMac,iMac Pro,Mac Mini,Mac Studio'
```

Encandenando dos o más Maps

```javascript
let numberArray = [1, 2, 3, 4, 5];
let returnValue = numberArray
  .map((num) => num * 2)
	.map((num) => num.toString())
  console.log(numberArray);
console.log(returnValue);
```

El resultado sería: 

```javascript
[ 1, 2, 3, 4, 5 ]
[ '2', '4', '6', '8', '10' ]
```
