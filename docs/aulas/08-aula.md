# Aula 08 — JavaScript: Fundamentos da Linguagem

!!! info "Objetivos da aula"
    - Declarar **variáveis** e usar **tipos** de dados.
    - Escrever **condições**, **laços** e **funções**.
    - Trabalhar com **arrays** e **objetos**.

## Onde o JavaScript roda

```html
<!-- No fim do <body>, para o HTML já existir -->
<script src="app.js"></script>
```

!!! tip "Console é seu amigo"
    Abra o **DevTools** (`F12`), aba *Console*. Tudo que você imprimir com `console.log()` aparece ali. É onde você vai depurar o tempo todo.

## Variáveis e tipos

```js
let idade = 20;          // pode mudar
const nome = "Ana";      // constante
let ativo = true;        // boolean

console.log(typeof idade); // "number"
```

| Tipo | Exemplo |
| :--- | :------ |
| `number` | `42`, `3.14` |
| `string` | `"texto"`, `'aspas'` |
| `boolean` | `true`, `false` |
| `array` | `[1, 2, 3]` |
| `object` | `{ nome: "Ana" }` |
| `undefined` / `null` | ausência de valor |

!!! danger "Use const por padrão"
    Prefira `const`; troque para `let` só quando precisar reatribuir. **Evite `var`** — ela tem regras de escopo confusas e legadas.

## Condições

```js
const nota = 7;

if (nota >= 9) {
  console.log("Excelente");
} else if (nota >= 6) {
  console.log("Aprovado");
} else {
  console.log("Recuperação");
}
```

!!! warning "== x ==="
    Sempre use `===` (compara valor **e** tipo). `==` faz conversões traiçoeiras: `0 == ""` é `true`, mas `0 === ""` é `false`.

## Laços

=== "for"
    ```js
    for (let i = 0; i < 5; i++) {
      console.log(i);
    }
    ```

=== "for...of"
    ```js
    const cores = ["azul", "verde"];
    for (const cor of cores) {
      console.log(cor);
    }
    ```

=== "while"
    ```js
    let n = 3;
    while (n > 0) {
      console.log(n);
      n--;
    }
    ```

## Funções

```js
// declaração
function soma(a, b) {
  return a + b;
}

// arrow function
const dobro = (x) => x * 2;

console.log(soma(2, 3)); // 5
console.log(dobro(10));  // 20
```

## Arrays e objetos

```js
const alunos = ["Ana", "Bruno", "Carla"];
alunos.push("Diego");          // adiciona
console.log(alunos.length);    // 4

const carro = { marca: "Fiat", ano: 2022 };
console.log(carro.marca);      // "Fiat"
carro.cor = "prata";           // adiciona propriedade
```

Métodos de array que você usará muito:

```js
const numeros = [1, 2, 3, 4];
const pares = numeros.filter((n) => n % 2 === 0); // [2, 4]
const emDobro = numeros.map((n) => n * 2);        // [2, 4, 6, 8]
```

## Template literals e strings

Use crases (`` ` ``) para interpolar variáveis sem concatenar com `+` — muito útil para montar as saídas dos exercícios:

```js
const nome = "Ana";
const nota = 8.5;
console.log(`${nome} tirou ${nota} e foi ${nota >= 6 ? "aprovada" : "reprovada"}`);
```

Métodos de string frequentes:

```js
"JavaScript".length;            // 10
"olá".toUpperCase();            // "OLÁ"
"  texto  ".trim();             // "texto"
"a,b,c".split(",");             // ["a", "b", "c"]
"FizzBuzz".includes("Buzz");    // true
```

## Verdadeiro, falso e o operador ternário

Em condições, alguns valores contam como "falso" (**falsy**): `false`, `0`, `""`, `null`, `undefined`, `NaN`. Todo o resto é **truthy**.

```js
const lista = [];
if (lista.length) { /* não entra: 0 é falsy */ }

// ternário: condição ? seValor : senão
const status = nota >= 6 ? "Aprovado" : "Reprovado";
```

## Escopo: onde a variável "existe"

`let` e `const` têm **escopo de bloco**: só existem dentro das `{ }` onde foram declaradas.

```js
if (true) {
  const x = 10;
}
// console.log(x); // ❌ erro: x não existe aqui
```

!!! warning "Cuidado dentro de laços"
    Declarar `const` dentro de um `for` cria uma variável **nova a cada volta** — isso é o comportamento desejado. Já variáveis declaradas fora do laço são compartilhadas entre as iterações.

## Métodos de array que resolvem os exercícios

Além de `filter` e `map` (Exercício 3), conheça:

```js
const numeros = [1, 2, 3, 4, 5];

numeros.forEach((n) => console.log(n)); // executa algo para cada item
numeros.reduce((soma, n) => soma + n, 0); // 15 — "reduz" a um único valor
numeros.includes(3);                      // true
numeros.find((n) => n > 3);               // 4 — o primeiro que satisfaz
```

!!! tip "A média com `reduce`"
    A calculadora do Exercício 1 fica elegante assim:
    ```js
    const media = notas.reduce((s, n) => s + n, 0) / notas.length;
    ```

## Percorrendo objetos

```js
const carro = { marca: "Fiat", ano: 2022 };
Object.keys(carro);    // ["marca", "ano"]
Object.values(carro);  // ["Fiat", 2022]

for (const [chave, valor] of Object.entries(carro)) {
  console.log(`${chave}: ${valor}`);
}
```

## Exercícios

??? abstract "Exercício 1 — Calculadora de média"
    Escreva uma função que receba um array de notas e retorne a média, imprimindo "Aprovado" (≥ 6) ou "Reprovado".

??? abstract "Exercício 2 — FizzBuzz"
    De 1 a 30, imprima o número; se múltiplo de 3, "Fizz"; de 5, "Buzz"; de ambos, "FizzBuzz".

??? abstract "Exercício 3 — Catálogo"
    Crie um array de objetos `produto` (nome, preço). Use `filter` para listar os que custam menos de R$ 50 e `map` para gerar um array só com os nomes.

!!! tip "Próxima Parada"
    Você sabe a lógica — agora vamos **mexer na página de verdade** manipulando o DOM. Antes, resolva a 👉 [**Lista 08**](../listas/08-lista.md).

## 📚 Referências

- [MDN — Primeiros passos com JavaScript](https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/First_steps)
- [javascript.info — O Tutorial JavaScript Moderno](https://javascript.info/)
- [MDN — Métodos de Array](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [MDN — Guia de JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide)
- [web.dev — Learn JavaScript](https://web.dev/learn/javascript/)
