# Lista 04 — Missão: Responsivo em Qualquer Tela

!!! abstract "Briefing da Missão"
    Aplique **Mobile First** e **media queries** ([Aula 04](../aulas/04-aula.md)). Sua interface precisa brilhar do celular ao desktop.

## 🎯 Exercícios

??? abstract "Missão 1 — Grid que responde"
    Galeria de cards: 1 coluna no celular, 2 no tablet e 4 no desktop, controlando **apenas** com media queries `min-width`.

??? abstract "Missão 2 — Menu hambúrguer (visual)"
    Menu horizontal no desktop; no celular, esconda os links e mostre o ícone ☰. Ainda sem JS — apenas com media query.

??? abstract "Missão 3 — Teste no DevTools"
    Teste a galeria da Missão 1 no **modo dispositivo** (`Ctrl+Shift+M`). Inclua no README prints em 3 larguras e descreva o que muda.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista04/
├── index.html
├── css/
│   └── style.css
├── img/
└── README.md         # com os prints da Missão 3
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista04`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 04"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista04.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] `<meta viewport>` presente em todas as páginas.
    - [ ] Estilo base é o do **celular**; media queries usam `min-width`.
    - [ ] Imagens fluidas (`max-width: 100%`).
    - [ ] Prints das 3 larguras no README.
    - [ ] Repositório público `uni-udwmj-lista04` e link no Classroom.
