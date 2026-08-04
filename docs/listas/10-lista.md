# Lista 10 — Missão: Conectando com o Mundo (APIs)

!!! abstract "Briefing da Missão"
    Busque dados reais ([Aula 10](../aulas/10-aula.md)): use `fetch`, `async/await` e renderize a resposta na tela — com estado de carregamento e tratamento de erro.

## 🎯 Exercícios

??? abstract "Missão 1 — Buscador de CEP"
    Com a API **ViaCEP** (`https://viacep.com.br/ws/CEP/json/`), o usuário digita um CEP e a página mostra rua, bairro e cidade.

??? abstract "Missão 2 — Galeria de posts"
    Consuma `https://jsonplaceholder.typicode.com/posts`, exiba "Carregando...", renderize os 10 primeiros como cards e trate erros de rede.

??? abstract "Missão 3 — API livre"
    Escolha uma API pública gratuita e monte uma página que busca e exibe algo útil, com estado de carregamento e tratamento de erro.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista10/
├── index.html
├── css/
│   └── style.css
└── js/
    ├── cep.js
    ├── posts.js
    └── livre.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista10`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 10"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista10.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Uso de `async/await` com `try/catch`.
    - [ ] Verificação de `resposta.ok` antes de usar os dados.
    - [ ] Estado de "Carregando..." visível durante a busca.
    - [ ] Mensagem amigável quando a requisição falha.
    - [ ] Repositório público `uni-udwmj-lista10` e link no Classroom.
