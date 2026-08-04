# Lista 09 — Missão: Página Viva com o DOM

!!! abstract "Briefing da Missão"
    Faça a página reagir ([Aula 09](../aulas/09-aula.md)): selecione elementos, altere o DOM e trate **eventos**.

## 🎯 Exercícios

??? abstract "Missão 1 — Alternador de tema"
    Botão que alterna a classe `dark` no `<body>`, trocando as cores (defina o tema escuro no CSS).

??? abstract "Missão 2 — Lista de tarefas"
    Campo de texto + botão "Adicionar" que insere o texto como novo `<li>`. Cada item tem um botão para removê-lo.

??? abstract "Missão 3 — Validação ao vivo"
    Em um campo de senha, use o evento `input` para indicar em tempo real se há ≥ 8 caracteres (verde/vermelho **e** um ícone/texto — não só cor!).

## 📁 Estrutura sugerida

```text
uni-udwmj-lista09/
├── index.html
├── css/
│   └── style.css
└── js/
    └── app.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista09`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 09"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista09.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Uso de `addEventListener` (sem `onclick` no HTML).
    - [ ] Estilos aplicados via `classList`, não `element.style` espalhado.
    - [ ] A todo-list adiciona **e** remove itens.
    - [ ] Feedback de validação não depende só de cor.
    - [ ] Repositório público `uni-udwmj-lista09` e link no Classroom.
