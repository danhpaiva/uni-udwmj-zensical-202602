# Usabilidade, Dev Web, Mobile e Jogos

Site de apoio da disciplina **Usabilidade, Dev Web, Mobile e Jogos**, construído com [Zensical](https://zensical.org) e publicado automaticamente no GitHub Pages via GitHub Actions.

O site fica em: https://danhpaiva.github.io/uni-udwmj-zensical-202602/

## Estrutura de pastas

```
.
├── docs/                  # Conteúdo do site (única pasta publicada)
│   ├── index.md           # Página inicial (cronograma, objetivos)
│   ├── setup.md           # Guia de início rápido para o professor
│   ├── ferramentas.md     # Guia de instalação de ferramentas para o aluno
│   ├── aulas/              # Uma página por aula (01-aula.md a 16-aula.md)
│   ├── listas/             # Uma página por lista de exercícios
│   ├── assets/             # Imagens (logo, favicon)
│   └── javascripts/        # JS extra carregado pelo tema (ex.: mathjax.js)
├── mkdocs.yml             # Configuração do site (nome, tema, navegação, extensões)
├── requirements.txt       # Dependências Python (zensical)
├── .github/workflows/     # Workflow de build e publicação (GitHub Actions)
├── LICENSE
└── README.md
```

`site/` é a saída do build (gerada localmente ou no CI) e não é versionada — veja `.gitignore`.

## Como rodar localmente

1. Clone o repositório:

   ```bash
   git clone https://github.com/danhpaiva/uni-udwmj-zensical-202602.git
   cd uni-udwmj-zensical-202602
   ```

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   # Windows:
   .\venv\Scripts\activate
   # Linux/Mac:
   source venv/bin/activate
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Inicie o servidor de visualização com recarregamento automático:

   ```bash
   zensical serve
   ```

   Acesse `http://127.0.0.1:8000` no navegador. Edite qualquer arquivo em `docs/` e a página recarrega automaticamente.

5. Para gerar o site estático em `site/` sem servir (o mesmo comando usado no CI):

   ```bash
   zensical build --strict
   ```

## Como publicar (GitHub Pages)

A publicação é automática via GitHub Actions a cada push na branch `main`. Para funcionar em um fork ou repositório novo, configure uma vez:

1. **Settings → Pages → Build and deployment → Source**: selecione **"GitHub Actions"** (não deixe em "Deploy from a branch").
2. **Settings → Actions → General → Workflow permissions**: selecione **"Read and write permissions"** e salve.

Se a publicação falhar com `Deployment failed, try again later`, quase sempre a causa é o passo 1 ainda não ter sido feito — corrija e reexecute o workflow em **Actions → (workflow) → Re-run jobs**.

## Fluxo de branches do CI

O workflow em [.github/workflows/ci.yml](.github/workflows/ci.yml) roda em push para `main` e `develop`:

- **`develop`**: builda o site com `zensical build --strict` apenas para validar que não há erros — nada é publicado.
- **`main`**: builda, e além disso publica o resultado no GitHub Pages (jobs `build` + `deploy`).

Use `develop` (ou uma branch de feature) para validar mudanças antes de mesclar em `main`.

## Como personalizar

Tudo é configurado em [mkdocs.yml](mkdocs.yml) (o Zensical lê esse arquivo diretamente, sem conversão):

- `site_name`: nome da disciplina exibido no site.
- `theme.palette` / `theme.font`: cores e fontes.
- `theme.features`: recursos de navegação e conteúdo habilitados (abas, busca, botão de editar página, etc.).
- `nav`: estrutura do menu lateral — organize aulas, listas e páginas aqui.
- `markdown_extensions`: extensões de Markdown habilitadas (admonitions, abas, mermaid, MathJax, etc.).

A busca é nativa do Zensical e não precisa ser declarada como plugin — ela herda automaticamente o idioma configurado em `theme.language`.

## Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE).
