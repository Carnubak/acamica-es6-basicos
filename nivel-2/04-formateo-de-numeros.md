# Formateo de números

## Introducción

ECMAScript cuenta con un [API de Internacionalización](http://norbertlindenberg.com/2012/12/ecmascript-internationalization-api/index.html), el cual
incluye el objeto
```javascript
Intl.NumberFormat
``
que permite el formateo de números.

### ES5 & ES6

#### Sintaxis
```javascript
new Intl.NumberFormat([locales][, options])
```
Donde "locales" es un parámetro opcional, el cual es un array de strings que contiene
uno o más idiomas.

El parámetro "options" es tambien opcional, y es un objeto con propiedades como estilos, moneda
entre otros, que no veremos en este capítulo.

A continuación presentamos algunos ejemplos:

```javascript
let number = 3500;
// Si no especificamos el parámetro locale, el formato del lenguaje será el usado por defecto en la interfaz de usuario de nuestra aplicación
console.log(new Intl.NumberFormat().format(number));
// → '3,500' en caso que nuestro locale por defecto sea US English
```

```javascript
let number = 123456.789;

// El idioma Alemán usa la coma para separar decimales y punto para separar milésimas.
console.log(new Intl.NumberFormat('de-DE').format(number));
// → 123.456,789
```

## Desafío

1. Intenta formatear un número a un lenguaje que no sea soportado, por ejemplo Balinés,
e incluye un lenguaje por defecto que si sea soportado, en este caso el Japonés.
Tip: recuerda que locale es un array de idiomas.

```javascript
let number = 123456.789;

console.log(new Intl.NumberFormat(['ban', 'ja-JP']).format(number));
// → 123,456.789
```
