# Lista 06 — Missão: Web para Todos

!!! abstract "Briefing da Missão"
    Torne suas páginas **acessíveis** ([Aula 06](../aulas/06-aula.md)). A missão é garantir que qualquer pessoa consiga usá-las.

## 🎯 Exercícios

??? abstract "Missão 1 — Auditoria com Lighthouse"
    Rode o **Lighthouse** em uma página sua, registre a nota de *Accessibility*, corrija ao menos 3 problemas e mostre o antes/depois (prints no README).

??? abstract "Missão 2 — Formulário acessível"
    Formulário de contato com `<label>` associado a cada campo, `alt` nas imagens, foco visível (`:focus-visible`) e mensagens de erro que não dependam só de cor.

??? abstract "Missão 3 — Só pelo teclado"
    Navegue por um site seu usando **apenas** `Tab`, `Shift+Tab` e `Enter`. Liste onde o foco some/prende e proponha correções.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista06/
├── index.html
├── contato.html
├── css/
│   └── style.css
└── README.md         # notas do Lighthouse e relato do teste por teclado
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista06`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 06"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista06.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Todo `<img>` tem `alt` significativo; todo campo tem `<label>`.
    - [ ] `<html lang="pt-BR">` e hierarquia correta de headings.
    - [ ] Foco visível ao navegar por teclado.
    - [ ] Nenhuma informação transmitida **só** por cor.
    - [ ] Repositório público `uni-udwmj-lista06` e link no Classroom.
