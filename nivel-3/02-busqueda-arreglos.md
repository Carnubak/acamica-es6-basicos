# Búsqueda sobre arreglos

## Introducción

Entre las funcionalidades que más se destacan en ES6 para arreglos, es permitir realizar búsquedas con métodos nativos, en vez de tener que recurrir a librerías externas para el mismo fin. Los siguientes métodos introducidos en ES6 son:

- Array.prototype.find()
- Array.prototype.findIndex()

Estos métodos evaluan una función pasada como argumento para determinar el éxito o no de la búsqueda.

## Array.Prototype.find
El método find(callback[, thisArg]) retorna el valor del arreglo que satisfaga la función 'callback', o undefined en su defecto.
La función callback toma tres argumentos posibles:
- element: el elemento actual en el arreglo que esta siendo procesado.
- index: el índice del elemento actual.
- array: el arreglo con que fue llamada la función.

Se puede bindear opcionalmente el objeto 'thisArg' al correrse la función callback.

### ES5
En ES5 se puede utilizar de forma similar el método Array.prototype.some(), aunque este devuelve un valor booleano que indica si se satisface o no la función callback.

```javascript
var names = [{name: 'chris'}, {name: 'derek'}, {name: 'tony'}];

console.log(names.some(function(currentItem) {
	return currentItem.name === 'derek';
})); // true

```

### ES6
```javascript
const names = [{name: 'chris'}, {name: 'derek'}, {name: 'tony'}];

console.log(names.find(function(currentItem) {
	return currentItem.name === 'derek';
})); // {name: 'derek'}

```

## Array.Prototype.findIndex
El método findIndex(callback[, thisArg]) tiene el mismo comportamiento que la función find, a diferencia que retorna el índice del elemento que satisfaga la función callback, o -1 en su defecto.

### ES5
En ES5 existe el método array.prototype.indexOf() aunque solo acepta arreglos de tipo simple (enteros, strings).

```javascript
var names = [{name: 'chris'}, {name: 'derek'}, {name: 'tony'}];
var namesAux = ['chris', 'derek', 'tony'];

console.log(names.indexOf({name: 'derek'})); // -1
console.log(namesAux.indexOf('derek')); // 1
```

### ES6
```javascript
const names = [{name: 'chris'}, {name: 'derek'}, {name: 'tony'}];

console.log(names.findIndex(function(currentItem) {
	return currentItem.name === 'derek';
})); // 1
```

## Desafíos
In progress...