# 🧰 Instalação das Ferramentas

Antes das atividades práticas, prepare seu ambiente. Siga a ordem sugerida e, ao final de cada item, use o comando de verificação para confirmar que deu certo.

!!! tip "Dica"
    Após instalar cada ferramenta, **feche e reabra o terminal** (ou o VS Code) para que os comandos passem a ser reconhecidos.

---

## 1. Navegador moderno + DevTools

Usaremos **Google Chrome** ou **Mozilla Firefox** como laboratório. As **Ferramentas de Desenvolvedor** (`F12`) serão abertas o tempo todo.

- 🔗 **Chrome:** [google.com/chrome](https://www.google.com/chrome/)
- 🔗 **Firefox:** [mozilla.org/firefox](https://www.mozilla.org/firefox/)

!!! info "Conheça o DevTools"
    Abra qualquer site e pressione `F12`. As abas *Elements*, *Console*, *Network*, *Application* e *Lighthouse* serão suas melhores amigas ao longo da disciplina.

---

## 2. Visual Studio Code

Editor de código que usaremos nas aulas.

- 🔗 **Download:** [code.visualstudio.com/download](https://code.visualstudio.com/download)

1. Baixe a versão para o seu sistema e instale.
2. No Windows, marque **"Adicionar ao PATH"** durante a instalação.
3. Extensões recomendadas (aba *Extensions*, `Ctrl+Shift+X`):
    - **Live Server** — recarrega a página automaticamente ao salvar.
    - **Prettier** — formata HTML/CSS/JS.
    - **Live Preview** (opcional) — pré-visualização embutida.

!!! tip "Live Server"
    Com a extensão instalada, clique com o botão direito em um `index.html` e escolha **"Open with Live Server"** para ver o site com recarregamento automático.

---

## 3. Node.js e npm

Ambiente para rodar ferramentas de desenvolvimento (Sass, Vite) e gerenciar pacotes. O **npm** já vem junto com o Node.

- 🔗 **Download:** [nodejs.org](https://nodejs.org/) (baixe a versão **LTS**)

1. Instale com as opções padrão.
2. Verifique no terminal:

```bash
node --version
npm --version
```

---

## 4. Git

Controle de versão, usado para versionar o código e entregar as listas.

- 🔗 **Download:** [git-scm.com/downloads](https://git-scm.com/downloads)

1. Baixe e instale (no Windows, aceite as opções padrão).
2. Verifique no terminal:

```bash
git --version
```

3. Configure seu nome e e-mail (uma única vez):

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

---

## 5. Conta no GitHub

Onde você publicará os repositórios das listas (`uni-udwmj-listaNN`).

- 🔗 **Criar conta:** [github.com/signup](https://github.com/signup)

!!! tip "Estudante?"
    Ative o **GitHub Student Developer Pack** ([education.github.com](https://education.github.com/)) para benefícios gratuitos.

---

## 6. Figma (para as aulas de UI/UX)

Ferramenta de prototipagem que usaremos a partir da [Aula 07](aulas/07-aula.md).

- 🔗 **Acesso:** [figma.com](https://www.figma.com/) (funciona no navegador; conta gratuita)

---

!!! success "Tudo pronto?"
    Se `node --version`, `npm --version` e `git --version` responderam com um número de versão, e o **Live Server** abre seu HTML no navegador, seu ambiente está configurado. Em caso de erro, confira se reabriu o terminal após a instalação.
