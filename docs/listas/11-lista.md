# Lista 11 — Missão: Ferramentas Profissionais

!!! abstract "Briefing da Missão"
    Adote o fluxo de trabalho de mercado ([Aula 11](../aulas/11-aula.md)): **Git**, **npm** e **Sass**.

## 🎯 Exercícios

??? abstract "Missão 1 — Repositório do zero"
    Crie um projeto, inicie o Git, faça 3 commits no padrão **Conventional Commits** e publique no GitHub. Inclua um `.gitignore` com `node_modules/`.

??? abstract "Missão 2 — Sass na prática"
    Reescreva um CSS seu em **SCSS** usando **variáveis** e **aninhamento**. Compile para CSS e conecte no HTML.

??? abstract "Missão 3 — Scripts no package.json"
    Configure um `package.json` com o script `build:css` que compila seu Sass. Rode com `npm run build:css` e descreva o resultado no README.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista11/
├── index.html
├── package.json
├── .gitignore
├── scss/
│   └── main.scss
└── css/
    └── style.css     # gerado pelo Sass
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista11`**.
2. Suba o código (sem `node_modules/`):
   ```bash
   git add .
   git commit -m "build: configura sass e scripts npm"
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista11.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Ao menos 3 commits com mensagens Conventional Commits.
    - [ ] `.gitignore` ignorando `node_modules/`.
    - [ ] SCSS usa variáveis e aninhamento; CSS é gerado por compilação.
    - [ ] `package.json` com script `build:css` funcional.
    - [ ] Repositório público `uni-udwmj-lista11` e link no Classroom.
