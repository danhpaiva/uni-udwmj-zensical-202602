# Lista 12 — Missão: Pensando em Componentes

!!! abstract "Briefing da Missão"
    Dê o salto para os **frameworks** ([Aula 12](../aulas/12-aula.md)): componentes, props e estado reativo.

## 🎯 Exercícios

??? abstract "Missão 1 — Decompondo em componentes"
    Escolha uma página conhecida (ex.: loja online), faça um diagrama dividindo-a em componentes e indique quais **props** cada card/lista receberia.

??? abstract "Missão 2 — Contador reativo"
    Usando **Vue via CDN** (ou React), crie um contador com botões "+", "−" e "zerar", reagindo ao estado.

??? abstract "Missão 3 — Lista com props"
    Crie um componente "Card de produto" que receba nome, preço e imagem por props e renderize uma lista de 4 produtos reutilizando o componente.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista12/
├── index.html        # app com Vue/React via CDN
├── diagrama.md       # ou imagem da decomposição (Missão 1)
├── css/
│   └── style.css
└── js/
    └── app.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista12`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 12"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista12.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Diagrama identifica componentes e suas props.
    - [ ] Contador reage ao **estado** (sem manipular o DOM na mão).
    - [ ] Card de produto reutilizado para 4 produtos via props.
    - [ ] Repositório público `uni-udwmj-lista12` e link no Classroom.
