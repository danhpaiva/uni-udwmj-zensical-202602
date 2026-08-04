# Lista 03 — Missão: Layouts que Encaixam

!!! abstract "Briefing da Missão"
    Domine o posicionamento com **Flexbox e Grid** ([Aula 03](../aulas/03-aula.md)). Sua missão é montar layouts reais.

## 🎯 Exercícios

??? abstract "Missão 1 — Barra de navegação (Flexbox)"
    `<nav>` com logo à esquerda e 3 links à direita, alinhados verticalmente ao centro, usando **apenas Flexbox**.

??? abstract "Missão 2 — Layout Holy Grail (Grid)"
    Reproduza com **Grid** um layout com `header`, `footer`, menu lateral e conteúdo, usando `grid-template-areas`.

??? abstract "Missão 3 — Galeria adaptável"
    Galeria de 6 cards que exibe 3 colunas no desktop e se reduz automaticamente em telas menores, usando `auto-fit` + `minmax`.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista03/
├── index.html        # links para os 3 exercícios
├── navbar.html
├── holy-grail.html
├── galeria.html
└── css/
    └── style.css
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista03`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 03"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista03.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Flexbox usado onde o layout é de 1 dimensão; Grid onde é de 2.
    - [ ] Uso de `gap` em vez de margens manuais entre itens.
    - [ ] Galeria realmente se reorganiza ao mudar a largura da janela.
    - [ ] Repositório público `uni-udwmj-lista03` e link no Classroom.
