# Javascript:page_with_curl:

Detalhes que não sabia sobre o javascript

- Suas regras são alteradas pelo **ECMAScript** 
- É multipadagima

## Função autoinvocavel

É uma função auto-invocada que você declara, mesmo como anônima, e que, no momento da declaração, você pode invocá-la.
Com esse tipo de função é possível fugir do escopo global do browser, limitando-se apenas ao escopo local da função. Veja:

```
(function() {
    console.log('Será executado na hora e fugirá do escopo global')
 }) () //Invocação da função  
```

```
let result = (function () { 
 let nome = "Bene"; 
 return nome; 
 })();

// Imediatamente gera a saída:
 result; // 'Bene' 
```

Tudo que for manipulado dentro da função somente atuará no escopo local da função, isolando-se do escopo mais abrangente.

## Arguments

O objeto `arguments`  é como um objeto Array correspondendo aos argumentos passados para uma função.
Ele é uma variável local disponível dentro de todas as funções. Você pode referenciar os argumentos de uma função dentro da função usando o objeto `arguments`. Esse objeto contém um registro para cada argumento fornecido para a função, com o índice do primeiro registro começando em 0. Por exemplo, se são passados três argumentos para uma função, você pode referenciá-los como a seguir: 

```
arguments[0]
arguments[1]
arguments[2]
```

## Usando a Sintaxe Spread com Arguments

Você também pode usar o método Array.from() ou o operador spread (en-US) para converter argumentos em um Array real:

```
var args = Array.from(arguments);
var args = [...arguments];
```

## Spread

Com a Spred você consegue por exemplo passar cada elemento de um array como paramentro em uma função, veja o exemplo:

```
function sum(x, y, z) {
	return x + y + z;
}

const numbers = [1, 2, 3];
console.log(sum(...numbers));
```

## REST

O contrario acontece quando utilizamos  o rest, veja:

```
function confereTamanho(...args) {
	console.log(args.length);
}

confereTamanho(); //0
confereTamanho(1, 2); //2
confereTamanho(3, 4, 5); //3
```

## For In e For Of

Tanto **for in** quanto **for of** vão iterar em uma lista, para nos entregar valores das mesmas
Porém o for in nos retorna os índices de cada elemento, já o for of nos retorna nos elementos da lista
Isso pode ser facilmente observado no código a seguir:

```
let arr = ["Matheus", 30, 1.78];

for (let i in arr) {
   console.log(i); // "0", "1", "2"
}

for (let i of arr) {
   console.log(i); // Matheus, 30, 1.78
}
```

## Switch/ Case

Nessa estrutura as condicionais equivalem a um ===

## Arrow Function

As arrow functions não fazem hoisting, então não tem como chamar a função antes de declarar a mesma
O valor this sempre será global, não irá funcionar o **call, apply, bind e arguments**. 

## Hoisting

O hoisting ocorre quando a uma atribuição sem antes ter uma declaração de variavel, isso só ocorre quando utilizamos **VAR**, no **LET** e no **CONST** nao é possivel fazer **hoisting**

```
number = 1 

var number = 3
```

## Escopos

Veja abaixo a diferança entre o Var, Let e Const

|            | VAR             | CONST | LET   |
| ---------- | --------------- | ----- | ----- |
| Escopo     | Global ou Local | Bloco | Bloco |
| Redeclarar | SIM             | NÃO   | NÃO   |
| Reatribuir | SIM             | NÃO   | SIM   |
| Hoisting   | SIM             | NÃO   | NÃO   |

 