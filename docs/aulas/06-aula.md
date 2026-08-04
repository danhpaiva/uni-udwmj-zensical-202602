# Aula 06 — Acessibilidade na Web

!!! info "Objetivos da aula"
    - Entender por que a acessibilidade (**a11y**) importa.
    - Aplicar HTML acessível e atributos **ARIA**.
    - Verificar **contraste** e navegação por teclado.

## Por que acessibilidade?

Cerca de **1 em cada 4 pessoas** possui alguma deficiência. Acessibilidade não é "extra": é garantir que todos — incluindo quem usa leitor de tela, só teclado ou tem baixa visão — consigam usar seu site. Além disso, é **lei** (LBI nº 13.146/2015) e melhora o SEO.

!!! quote "Princípios do WCAG (POUR)"
    Conteúdo deve ser **P**erceptível, **O**perável, **U**tilizável (compreensível) e **R**obusto.

## HTML semântico já é acessível

Boa parte da acessibilidade vem de graça quando você usa a marcação correta (Aula 01).

=== "❌ Problema"
    ```html
    <div class="botao" onclick="enviar()">Enviar</div>
    ```
    Uma `<div>` não é focável nem anunciada como botão.

=== "✅ Solução"
    ```html
    <button type="button" onclick="enviar()">Enviar</button>
    ```
    O `<button>` é focável por teclado e anunciado corretamente.

## Recursos essenciais de a11y

| Recurso | Como fazer | Beneficia |
| :------ | :--------- | :-------- |
| Texto alternativo | `<img alt="descrição">` | Leitores de tela |
| Rótulo de campo | `<label for="email">` | Todos |
| Idioma da página | `<html lang="pt-BR">` | Leitura correta |
| Foco visível | `:focus-visible` no CSS | Teclado |
| Ordem lógica | Estrutura de headings `h1→h2→h3` | Navegação |

## ARIA: quando o HTML não basta

**ARIA** (Accessible Rich Internet Applications) adiciona semântica a componentes complexos (abas, modais, menus).

```html
<button aria-expanded="false" aria-controls="menu">☰ Menu</button>
<nav id="menu" aria-label="Menu principal" hidden>...</nav>
```

!!! danger "Primeira regra do ARIA"
    **Não use ARIA se um elemento HTML nativo resolve.** ARIA mal usado piora a acessibilidade. Prefira `<button>` a `<div role="button">`.

## Contraste e cor

Nunca comunique **só pela cor** (ex.: "campos em vermelho estão errados") — adicione ícone ou texto. E garanta contraste suficiente:

| Conteúdo | Contraste mínimo (WCAG AA) |
| :------- | :-------------------------- |
| Texto normal | 4.5:1 |
| Texto grande | 3:1 |

```css
a:focus-visible {
  outline: 3px solid #7c4dff;
  outline-offset: 2px;
}
```

!!! tip "Ferramentas"
    Teste com o **Lighthouse** (DevTools → aba *Lighthouse*) e navegue na sua página **usando só o `Tab`**. Se você não consegue, um usuário de teclado também não.

## Os níveis de conformidade WCAG

O WCAG define três níveis. A maioria das leis e empresas exige o nível **AA**:

| Nível | Significado | Exemplo de critério |
| :---- | :---------- | :------------------ |
| **A** | Mínimo | Todo conteúdo não textual tem alternativa |
| **AA** | **Recomendado** | Contraste de 4.5:1; foco visível |
| **AAA** | Ideal | Contraste de 7:1 (nem sempre viável) |

## Formulários acessíveis (Exercício 2)

O erro mais comum é o campo sem rótulo associado. Há duas formas corretas:

=== "`for` + `id`"
    ```html
    <label for="email">E-mail</label>
    <input id="email" type="email" name="email" />
    ```

=== "`<label>` envolvendo"
    ```html
    <label>
      E-mail
      <input type="email" name="email" />
    </label>
    ```

!!! tip "Descreva erros com texto e ARIA"
    ```html
    <input id="cep" aria-describedby="erro-cep" aria-invalid="true" />
    <span id="erro-cep">CEP inválido: use 8 dígitos.</span>
    ```
    Assim o leitor de tela anuncia o erro junto com o campo — e não dependemos só da cor vermelha.

## Roles, states e properties do ARIA

O ARIA se divide em três tipos de atributos:

| Tipo | Exemplo | Diz o quê |
| :--- | :------ | :-------- |
| **Role** | `role="dialog"` | O **papel** do elemento |
| **State** | `aria-expanded="true"` | Um **estado** que muda |
| **Property** | `aria-label="Fechar"` | Uma **característica** fixa |

```html
<button aria-label="Fechar" aria-controls="modal" aria-expanded="false">✕</button>
```

## Navegação por teclado (Exercício 3)

Elementos interativos nativos (`<a>`, `<button>`, `<input>`) já entram na ordem de `Tab`. Pontos de atenção:

- **`tabindex="0"`** insere um elemento na ordem natural de tabulação.
- **`tabindex="-1"`** o torna focável só por script (útil em modais).
- **Nunca** use `tabindex` com valores positivos (`1`, `2`...): bagunçam a ordem.
- Um foco que "some" quase sempre é `outline: none` sem substituto — use `:focus-visible`.

```css
:focus-visible {
  outline: 3px solid #7c4dff;
  outline-offset: 2px;
}
```

## Exercícios

??? abstract "Exercício 1 — Auditoria com Lighthouse"
    Rode o **Lighthouse** em uma página sua e registre a nota de *Accessibility*. Corrija ao menos 3 problemas apontados e mostre o antes/depois.

??? abstract "Exercício 2 — Formulário acessível"
    Crie um formulário de contato com `<label>` associado a cada campo, `alt` em imagens, foco visível e mensagens de erro que não dependam apenas de cor.

??? abstract "Exercício 3 — Só pelo teclado"
    Pegue um site seu e navegue usando **apenas `Tab`, `Shift+Tab` e `Enter`**. Liste os pontos onde o foco some ou fica preso, e proponha correções.

!!! tip "Próxima Parada"
    Antes de programar telas, é hora de **desenhar e testar ideias** rapidamente. Na próxima aula: prototipagem. Antes, resolva a 👉 [**Lista 06**](../listas/06-lista.md).

## 📚 Referências

- [MDN — Acessibilidade](https://developer.mozilla.org/pt-BR/docs/Learn/Accessibility)
- [W3C WAI — Introdução à Acessibilidade Web](https://www.w3.org/WAI/fundamentals/accessibility-intro/pt-br)
- [WCAG 2.1 (recomendação oficial)](https://www.w3.org/TR/WCAG21/)
- [W3C — ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
- [Chrome — Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/)
