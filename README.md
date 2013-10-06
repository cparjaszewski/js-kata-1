js-kata-1
=========

JavaScript Kata 1

Task
====

Cwiczenia na obsługę `arguments`, `bind`, `call`, `apply`, funkcje wyższego rzędu, funkcje częsciowe (tak tak, przyda się :))

#### Stwórz funkcję `map`

```js
function map(fn, array) {
  // ...
}

map(function(x){return x*x}, [1,2,3]) // -> [1,4,9]

```

#### Stwórz funkcje `bind`, która bierze funkcję, parametry i tworzy funkcję częściową, np

```js
function bind(fn /* rest */) {
  // ...
}
function pow(x) {
  return x*x;  
}

var mapToPow2 = bind(map, pow);

mapToPow2([1,2,3]) // -> [1,4,9]
```

Powinna działać dla dowolnej ilości argumentow, np

```js
function add3Numbers(x,y,z) {
  return x+y+z;
}

var add_5_and_6 = bind(add3Numbers, 5,6);
add_5_and_6(7) // -> 18
add_5_and_6(8) // -> 19
```

(* Zadanie z gwiazdką na koniec) To tez powinno działać:

```
var add_1 = bind(add3Numbers, 1);
var add_1_and_2 = bind(add_1, 2);
add_1_and_2(3) // -> 6
```


#### Stwórz funkcję `reduce`, działającą analogicznie jak `Array.prototype.reduce`

```
function reduce(fn, array, initialValue) {
  // ...
}

function plus(a,b) {
  return a+b;
}

reduce(plus, [1,2,3], 0); // -> 6

// ale tez mozemy chciec dodawać pary (btw, czy ta uwaga jest potrzebna w ogole?)
reduce(function(a,b){
  return [
    a[0]+b[0],
    a[1]+b[1]];
}, [[1,2],[3,4]]); // -> [4,6]
```

Zadbaj o to, żeby initialValue było opcjonalne jeśli argument `array` nie jest pusty.

I na koniec ostatnie zadanie, stwórz funkcję `partition`, która korzysta z `reduce` i dziala w taki sposob, ze dostając funkcję `fn` zwracającą `true/false`, tablicę `array`, ostatecznie zwraca dwie tablice z wartosciami z `array`, gdzie tablica nr `1` posiada wartosci zaaplikowane do `fn` ktore daly `true`, a tablica nr `2` dające `false`. Np:

```
function partition(fn, array) {
  return reduce(...);
}
function even(x) {
  return x%2;
}
partition(even, [1,2,3,4,5,6,7,8,9,10]) // -> [[1,3,5,7,9], [2,4,6,8,10]]
```

Jak sie z tym uporamy, to będzie wiecej praktycznych zadanek i dojdzie więcej elementow z JavaScriptu.

