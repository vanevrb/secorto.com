---
title: JavaScript Modular
category: dev
excerpt: Divide y vencerás, una gran verdad del desarrollo web
---

Desarrollando aplicaciones aprendemos que hay muchas maneras de dar solución a un problema, todas ellas validas, muchas puede que compartan su enfoque asi como pueden haber implementaciones con otra forma de ver el problema. El problema llega cuando se requiere dar solución a algo que anteriormente ya otros dieron solución, sin embargo hacer todo desde 0 no es conveniente dado que puede tomar mucho tiempo.

# Herramientas para hacer un javascript modular

Los módulos en javascript es una característica disponible de forma nativa a partir de ES6, sin embargo para ES5 hay herramientas que pueden ser de ayuda para este objetivo

## ES5

CommonJS
: La usada en este blog, CommonJS una implementación usada por NodeJS para la importación de módulos usando la palabra reservada require.

```javascript
var $ = require('jquery');
exports.myExample = function () {};
```

AMD
: Se usa cuando se requiere tener paquetes asíncronos ya que commonJS a pesar de ser mas sencilla tiene el inconveniente que los módulos se importan de forma Sincrónica.

```javascript
define(['jquery'] , function ($) {
    return function () {};
});
```

## ES6

Ya está implementada de forma nativa

```javascript
//------ lib.js ------
export const sqrt = Math.sqrt;
export function square(x) {
    return x * x;
}
export function diag(x, y) {
    return sqrt(square(x) + square(y));
}

//------ main.js ------
import { square, diag } from 'lib';
console.log(square(11)); // 121
console.log(diag(4, 3)); // 5
```

[②ality – JavaScript and more](http://www.2ality.com/2014/09/es6-modules-final.html)
