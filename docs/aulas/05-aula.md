# Aula 05 — UI/UX: Usabilidade e Design Centrado no Usuário

!!! info "Objetivos da aula"
    - Diferenciar **UI** de **UX**.
    - Conhecer as **10 heurísticas de Nielsen**.
    - Aplicar o **Design Centrado no Usuário (DCU)**.

## UI x UX: não são a mesma coisa

=== "UI — User Interface"
    O **que você vê e toca**: cores, botões, tipografia, ícones, espaçamento. É a camada visual.

=== "UX — User Experience"
    O **que você sente ao usar**: é fácil? é rápido? me frustrei? A experiência completa, do primeiro clique ao objetivo cumprido.

!!! quote "Analogia"
    Se o produto fosse um restaurante, a **UI** é a decoração e a louça; a **UX** é toda a experiência: reserva, atendimento, sabor e a conta no fim.

## As 10 heurísticas de Nielsen

| # | Heurística | Em uma frase |
| :- | :--------- | :----------- |
| 1 | Visibilidade do status | Mostre o que está acontecendo (loading, sucesso). |
| 2 | Correspondência com o mundo real | Fale a língua do usuário. |
| 3 | Controle e liberdade | Ofereça "desfazer" e "voltar". |
| 4 | Consistência e padrões | Não reinvente convenções. |
| 5 | Prevenção de erros | Evite que o erro aconteça. |
| 6 | Reconhecer > lembrar | Deixe opções visíveis. |
| 7 | Flexibilidade e eficiência | Atalhos para experientes. |
| 8 | Design minimalista | Menos é mais. |
| 9 | Ajudar a reconhecer/recuperar de erros | Mensagens claras e com solução. |
| 10 | Ajuda e documentação | Disponível quando necessária. |

!!! example "Heurística 1 na prática"
    Um botão "Enviar" que, ao ser clicado, mostra um *spinner* e depois "✅ Enviado!" respeita a **visibilidade do status**. Um botão que parece não fazer nada quebra essa heurística.

## Design Centrado no Usuário (DCU)

```mermaid
graph LR
    A[Pesquisar<br/>quem é o usuário] --> B[Definir<br/>necessidades]
    B --> C[Prototipar<br/>soluções]
    C --> D[Avaliar<br/>com usuários]
    D --> A
```

O DCU é **iterativo**: você projeta, testa com pessoas reais, aprende e repete. Decisões são baseadas em **evidências**, não em achismos.

Ferramentas do DCU:

- **Personas** — arquétipos dos usuários.
- **Jornada do usuário** — os passos até o objetivo.
- **Testes de usabilidade** — observar pessoas usando o produto.

## Boas práticas de UI

!!! tip "Checklist rápido"
    - **Hierarquia visual**: o mais importante deve saltar aos olhos.
    - **Contraste**: texto legível sobre o fundo.
    - **Feedback**: todo clique gera uma resposta visível.
    - **Alvos de toque** ≥ 44×44px no mobile.
    - **Consistência**: mesmos padrões em todo o produto.

## Heurísticas com exemplos concretos

Para a "caça às heurísticas" (Exercício 1), saber reconhecê-las na prática é essencial:

=== "Boas práticas ✅"
    - **#2 (mundo real):** um app de banco fala "extrato" e "saldo", não "log de transações".
    - **#3 (controle):** o Gmail mostra "Desfazer" logo após enviar um e-mail.
    - **#5 (prevenção):** o campo de cartão só aceita números e formata sozinho.
    - **#9 (recuperar de erro):** "Senha incorreta. Esqueceu? Clique aqui" — diz o problema **e** a saída.

=== "Violações ❌"
    - **#1 (status):** clicar em "Pagar" e a tela não dar sinal de vida por 5 segundos.
    - **#4 (consistência):** o botão de salvar fica à direita em uma tela e à esquerda em outra.
    - **#6 (reconhecer):** obrigar o usuário a decorar um código de outra tela.
    - **#8 (minimalista):** uma tela lotada de banners competindo pela atenção.

## Princípios visuais: por que uma tela "funciona"

A **UI** apoia a **UX** organizando o que o olho vê. Alguns princípios de Gestalt e design que você usará no redesenho (Exercício 3):

| Princípio | Ideia | Aplicação |
| :-------- | :---- | :-------- |
| **Proximidade** | Itens próximos parecem relacionados | Agrupe rótulo e campo do formulário |
| **Semelhança** | Itens parecidos parecem do mesmo tipo | Todos os botões primários iguais |
| **Hierarquia** | Tamanho/cor guiam a atenção | Título grande, ação principal em destaque |
| **Espaço em branco** | "Respiro" reduz a sobrecarga | Menos é mais |

!!! tip "A regra dos 3 cliques (com cautela)"
    Quanto menos passos para concluir uma tarefa, melhor — mas **clareza** vence quantidade de cliques. Um caminho de 4 passos óbvios é melhor que 2 passos confusos.

## Persona e jornada na prática

Uma **persona** (Exercício 2) resume um usuário-alvo real em um personagem:

```text
Nome: Marina, 34 anos, autônoma
Objetivo: emitir uma nota fiscal em menos de 2 minutos
Frustração: sistemas cheios de jargão contábil
Contexto: usa o celular, entre um cliente e outro
```

A **jornada do usuário** lista os passos (e emoções) até o objetivo — ela revela onde o usuário trava e ajuda a priorizar melhorias.

## Como fazer uma avaliação heurística

1. Escolha as tarefas principais do produto.
2. Percorra cada tela **com a lista das 10 heurísticas na mão**.
3. Anote cada problema, cite a **heurística violada** e classifique a **gravidade** (de 0 = cosmético a 4 = catastrófico).
4. Proponha uma correção para cada item.

## Exercícios

??? abstract "Exercício 1 — Caça às heurísticas"
    Escolha um app ou site que você usa. Liste **3 boas** práticas (heurísticas respeitadas) e **3 problemas** (heurísticas violadas), citando o número da heurística em cada caso.

??? abstract "Exercício 2 — Persona"
    Crie uma persona para um app de sua escolha: nome, idade, objetivos, frustrações e contexto de uso. Explique como ela influenciaria uma decisão de design.

??? abstract "Exercício 3 — Redesenho"
    Encontre um formulário confuso (real ou inventado) e proponha uma versão melhorada, justificando cada mudança com a heurística correspondente.

!!! tip "Próxima Parada"
    Usável para a maioria é ótimo — mas e para **todos**? Na próxima aula garantimos acessibilidade. Antes, resolva a 👉 [**Lista 05**](../listas/05-lista.md).

## 📚 Referências

- [Nielsen Norman Group — 10 Heurísticas de Usabilidade](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [Interaction Design Foundation — UX Design](https://www.interaction-design.org/literature/topics/ux-design)
- [Nielsen Norman Group — Personas](https://www.nngroup.com/articles/persona/)
- [Laws of UX — princípios de design](https://lawsofux.com/)
- [web.dev — Learn Accessibility (base de UX inclusiva)](https://web.dev/learn/accessibility/)
