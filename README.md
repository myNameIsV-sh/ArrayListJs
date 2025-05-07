# Manipulando e modificando Arrays

Este tutorial tem como objetivo exemplificar e visualizar na prática, alguns métodos de manipulação de Arrays que existem no JavaScript, esses métodos são: `map`, `filter` e `reduce`.

- [[#`.map()`]]
- [[#`.filter()`]]
- [[#`.reduce()`]]
##### `.map()`
Por definição, o método `map` cria um novo *array* e para cada valor/item é aplicado uma função. Na prática, é feito uma cópia do *array* e sobre essa cópia é aplicado a modificação desejada, o exemplo abaixo irá tornar as coisas mais claras.

```
let numbers = [1, 2, 3, 4, 5];  
  
let newNumbers = numbers.map((number, i) => {  
    return number + i;  
});

console.log(newNumbers); // [1, 3, 5, 7, 9]
```

No exemplo acima, o método `map` "mapeia" o *array* e para cada elemento é chamada a função `number + i`; `number` é o valor atual, enquanto `i` representa o índice desse *array*. Em outras linguagens de programação é comum utilizarmos o *loop* `for` para esse tipo de situação – utilizando o método `map` conseguimos simplificar esse processo.

**Sintaxe**
`arrayTeste.map(funcao(valorAtual, índice, array), thisValue)`

**Parâmetros Obrigatórios**
- `arrayTeste.map()` - *array* que será mapeado.
- `funcao` - função que será executada (aqui acontece o *Callback*)
- `valorAtual` - o valor que está armazenado naquele momento.

**Parâmetros Opcionais**
- `índice` - que será o índice do `valorAtual`, representando a posição do mesmo.
- `array` - o *array* original.
- `thisValue` - um novo argumento que pode ser passado utilizando o `this`.

**Considerações importantes**
- A lista original permanece inalterada.
- A função não é executada em elementos vazios.
- Lembre-se que agora existem duas listas no seu programa.
- É possível utilizar o método diretamente no *array* escrevendo `[].map`.
- A lista "mapeada" sempre terá a mesma quantidade de elementos que a original.
##### `.filter()`
O método `filter` por outro lado, ele filtra (literalmente) o *array* baseado em algum critério, a cópia do novo *array* irá conter apenas os elementos que forem válidos na verificação de condição definida, essa condição retorna `true` ou `false`.

Aqui temos um exemplo filtrando apenas os números pares dentro de um *array*:

```
const numbers = [1, 2, 3, 4, 5, 6, 7, 8];

const evenNumbers = numbers.filter((num) => {
    return num % 2 === 0;
});

console.log(evenNumbers); // [2, 4, 6, 8]
```

**Sintaxe**
`arrayTeste.filter(funcao(valorAtual, índice, array), thisValue)`

**Parâmetros Obrigatórios**
- `arrayTeste.filter()` - *array* que será filtrado.
- `funcao()` - função que será executada (mais uma vez o *Callback*)
- `valorAtual` - o valor que está armazenado naquele momento.

**Parâmetros Opcionais**
- `índice` - que será o índice do `valorAtual`, representando a posição do mesmo.
- `array` - o *array* original.
- `thisValue` - um novo argumento que pode ser passado utilizando o `this`.

**Considerações importantes**
- A lista original permanence inalterada.
- A função não é executada em elementos vazios.
- A lista filtrada terá menos elementos que a original.
- Nosso programa contém duas listas, a original e a filtrada.
##### `.reduce()`
E se quiséssemos reduzir uma grande quantidade de informações em um único valor? O método `reduce` permite que seja feito o "agrupamento" das informações em uma única variável. O *modus operandi* ainda é mesmo, a função é aplicada para cada elemento do *array*. 

```
let numbers = [10, 20, 30];

let sum = numbers.reduce((acc, num) => acc + num, 0);

console.log(sum); // 60
```

A cada iteração o acumulador (`acc`) recebe o resultado dessa acumulação, vale a pena ressaltar que por mais que não seja obrigatório informar um valor inicial, é interessante começarmos a interação pelo índice `0` afim de evitar erros, como por exemplo percorrer um *array* vazio.

**Sintaxe**
`arrayTeste.reduce(funcao(total, valorAtual, índiceAtual, array), thisValue)`

**Parâmetros Obrigatórios**
- `arrayTeste.reduce()` - *array* que será reduzido.
- `funcao()` - função que será executada em cada elemento (*Callback*)
- `total` - será o valor inicial ou o valor retornado anteriormente.
- `valorAtual` - o valor que está armazenado naquele momento.

**Parâmetros Opcionais**
- `índiceAtual` - que será o índice do `valorAtual`, representando a posição do mesmo.
- `array` - o *array* original.
- `thisValue` - um novo argumento que pode ser passado utilizando o `this`.

**Considerações importantes**
- O *array* original não é alterado.
- Se um valor inicial não for fornecido, o "loop" irá acontecer a partir do índice 1.
- A função não é executada em elementos vazios.
- A lista será reduzida para um único valor.
- Nosso programa contém o *array* original e um novo único valor.

##### Finalização
Dessa forma vimos de uma maneira um pouco mais simples, as capacidades que esses métodos nos proporcionam, dispensando a necessidade de utilizarmos *loops* verbosos para realizarmos essas tarefas; esse pequeno artigo teve como objetivo abstrair um pouco dessas complexidades para um primeiro contato com essas funcionalidades — vale destacar os *links* abaixo contendo todas as fontes que foram utilizadas para a criação deste artigo, é importante que elas sejam consultadas posteriormente caso aja alguma dúvida, esses métodos podem ser aplicados em casos muito mais específicos, como manipulação de *strings* e "encadeamento de métodos" que não fizeram parte do escopo desse artigo.

Links:
- [How to Concatenate Strings in JavaScript? | GeeksforGeeks](https://www.geeksforgeeks.org/how-to-concatenate-strings-in-javascript/)
- [Array.prototype.map() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 
- [JavaScript Array map() Method](https://www.w3schools.com/jsref/jsref_map.asp)
- [How to Use JavaScript's Array reduce() Method – Explained with Examples](https://www.freecodecamp.org/news/how-to-use-javascript-array-reduce-method/)
- [JavaScript Array reduce() Method](https://www.w3schools.com/jsref/jsref_reduce.asp)
- [Array.prototype.reduce() - JavaScript | MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
