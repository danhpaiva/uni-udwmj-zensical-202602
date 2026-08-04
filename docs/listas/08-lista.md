# Lista 08 — Missão: Lógica com JavaScript

!!! abstract "Briefing da Missão"
    Programe a lógica ([Aula 08](../aulas/08-aula.md)): variáveis, condições, laços, funções, arrays e objetos. Tudo testado no **console**.

## 🎯 Exercícios

??? abstract "Missão 1 — Calculadora de média"
    Função que recebe um array de notas, retorna a média e imprime "Aprovado" (≥ 6) ou "Reprovado".

??? abstract "Missão 2 — FizzBuzz"
    De 1 a 30: imprima o número; múltiplo de 3 → "Fizz"; de 5 → "Buzz"; de ambos → "FizzBuzz".

??? abstract "Missão 3 — Catálogo"
    Array de objetos `produto` (nome, preço). Use `filter` para listar os que custam < R$ 50 e `map` para gerar um array só com os nomes.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista08/
├── index.html        # carrega os scripts e mostra saídas no console
└── js/
    ├── media.js
    ├── fizzbuzz.js
    └── catalogo.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista08`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 08"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista08.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Uso de `const`/`let` (nunca `var`) e comparação com `===`.
    - [ ] Funções com nomes claros e um único propósito.
    - [ ] Uso de `filter`/`map` na Missão 3 (sem laço manual).
    - [ ] Código roda sem erros no console.
    - [ ] Repositório público `uni-udwmj-lista08` e link no Classroom.
