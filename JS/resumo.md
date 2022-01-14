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

##  Promises

É um dado que no momento que recebido, não sabemos o que pode acontecer, pois nãoo temos o resultado ainda, mas um tempo depois saberemos se o resultado apontou que o dado foi resolvido ou rejeitado. 

​				               	RESOLVED
PENDING		    ------>  .then( ) -------->             PENDING
 Promise ----------|									 |------->  Promise
​						    ------>  .catch( ) ------->
​									 REJECTED

### Estados da promise

1. Pending -  Pendente
2. Fulfilled -   Completada
3. Rejected - Rejeitada

### Estrutura de uma promise

```
Const myPromise = new Promise((resolve, reject) => {
	window.setTimeout(() => {
		resolve(console.log('Resolvida!'));
	}, 2000);
});
```

## Async / await 

Funções assincronas precisam dessas duas palavras, async e await.
Definindo uma função como `async`, podemos utilizar a palavra-chave `await` antes de qualquer expressão que retorne uma promessa. Dessa forma, a execução da função externa (a função `async`) será pausada até que a Promise seja resolvida.

```
async function getUser(userId) { 
	let response = await fetch(`https://api.com/api/user/${userId}`); 
	let userData = await response.json(); 
	return userData.name; // não é necessário o await no return 
}
```

## Fetch

A API fetch provê ao navegador uma interface para a execução de requisições HTTP através de Promises.
Antes do Fetch as requisições HTTP eram feitas através do XMLHttpRequest.	Neste exemplo faremos uma comparação da mesma requisição sendo feita em ambas APIs:

```
// requisição com o XMLHttpRequest
  const request = new XMLHttpRequest()

  request.open('GET', 'http://exemplo.com/usuario')

  request.onload = function () {
    console.log(JSON.parse(this.responseText))
  }

  request.onerror = function () {
    console.log('erro ao executar a requisição')
  }

  request.send()
```

Perceba que na **linha 1** é instanciado o XMLHttpRequest a uma constante, e em seguida (**linha 2**) definimos o método e URL da requisição, para depois declarar dois callbacks: onload e onerror para ação de sucesso e erro, respectivamente. Ao final executamos a requisição com o send().

Todo esse processo torna a requisição complexa de ser feita, sem contar que não foi definido sequer um header no exemplo, por isso foi criado o Fetch, tornando a requisição HTTP mais simples, como podemos ver no exemplo reescrito.

```
// requisição com o Fetch

  fetch('http://exemplo.com/usuario')
    .then(T => T.json())
    .then(console.log)
```