# Lista 01 — Missão: Sua Primeira Página Web

!!! abstract "Briefing da Missão"
    Coloque em prática a [Aula 01](../aulas/01-aula.md) construindo páginas com **HTML semântico**. Sem CSS ainda — o foco é estrutura e significado.

## 🎯 Exercícios

??? abstract "Missão 1 — Página de perfil"
    Crie `perfil.html` com estrutura semântica: `<header>` com seu nome, `<main>` com um `<article>` de apresentação e `<footer>` com seus links. Nenhum texto solto fora de tags de conteúdo.

??? abstract "Missão 2 — Corrigindo a marcação"
    Reescreva usando tags semânticas:
    ```html
    <div id="cabecalho"><div id="titulo">Meu Blog</div></div>
    <div id="post"><div id="txt">Primeiro post...</div></div>
    <div id="rodape">© 2026</div>
    ```

??? abstract "Missão 3 — Listas e tabela"
    Página com: lista **ordenada** de 3 objetivos, lista **não ordenada** de 3 ferramentas e uma **tabela** de 3 linguagens com seu ano de criação.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista01/
├── index.html
├── perfil.html
├── marcacao.html
└── listas-e-tabela.html
```

## 🚀 Passo a passo da entrega

1. Crie um repositório **público** no GitHub chamado **`uni-udwmj-lista01`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 01"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista01.git
   git push -u origin main
   ```
3. Confira se os arquivos aparecem no GitHub.
4. **Entregue o link do repositório** na atividade correspondente do **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Todas as páginas têm `<!DOCTYPE html>`, `lang="pt-BR"` e `<meta viewport>`.
    - [ ] Uso de tags semânticas (nada de `<div>` desnecessária).
    - [ ] Nenhum texto solto fora de tags de conteúdo.
    - [ ] Repositório **público** e nomeado `uni-udwmj-lista01`.
    - [ ] Link entregue no Google Classroom.
