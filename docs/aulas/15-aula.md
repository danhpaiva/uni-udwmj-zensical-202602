# Aula 15 — Computação Gráfica: Canvas e Game Loop

!!! info "Objetivos da aula"
    - Desenhar formas com a API **Canvas 2D**.
    - Estruturar um **game loop** com `requestAnimationFrame`.
    - Animar objetos e capturar **entrada** do teclado.

## O elemento Canvas

O `<canvas>` é uma "tela em branco" onde desenhamos via JavaScript, pixel a pixel.

```html
<canvas id="tela" width="480" height="320"></canvas>
```

```js
const canvas = document.querySelector("#tela");
const ctx = canvas.getContext("2d"); // o "pincel"
```

## Desenhando formas

```js
// retângulo preenchido
ctx.fillStyle = "#7c4dff";
ctx.fillRect(20, 20, 100, 60);

// círculo
ctx.beginPath();
ctx.arc(200, 100, 30, 0, Math.PI * 2);
ctx.fillStyle = "orange";
ctx.fill();

// texto
ctx.fillStyle = "black";
ctx.font = "20px Inter";
ctx.fillText("Placar: 0", 10, 300);
```

| Método | Desenha |
| :----- | :------ |
| `fillRect(x, y, w, h)` | Retângulo preenchido |
| `strokeRect(...)` | Só a borda |
| `arc(x, y, r, 0, 2π)` | Arco/círculo |
| `clearRect(...)` | Apaga uma área |

## O Game Loop

Todo jogo repete o mesmo ciclo, dezenas de vezes por segundo:

```mermaid
graph LR
    E[Entrada<br/>teclado/mouse] --> U[Atualizar<br/>posições e lógica]
    U --> R[Renderizar<br/>desenhar tudo]
    R --> E
```

Usamos `requestAnimationFrame`, que sincroniza com a taxa de atualização do monitor (~60 fps):

```js
const bola = { x: 50, y: 50, vx: 3, vy: 2, r: 15 };

function loop() {
  // 1. limpar a tela
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  // 2. atualizar (física da Aula 14)
  bola.x += bola.vx;
  bola.y += bola.vy;

  // 3. colidir com as bordas
  if (bola.x + bola.r > canvas.width || bola.x - bola.r < 0) bola.vx *= -1;
  if (bola.y + bola.r > canvas.height || bola.y - bola.r < 0) bola.vy *= -1;

  // 4. renderizar
  ctx.beginPath();
  ctx.arc(bola.x, bola.y, bola.r, 0, Math.PI * 2);
  ctx.fillStyle = "#7c4dff";
  ctx.fill();

  requestAnimationFrame(loop); // agenda o próximo quadro
}

loop();
```

!!! danger "Sempre limpe a tela"
    Sem `clearRect` no início do loop, cada quadro se acumula e a bola vira um "rastro". Limpar → atualizar → desenhar é a ordem sagrada.

## Capturando o teclado

```js
const teclas = {};
addEventListener("keydown", (e) => (teclas[e.key] = true));
addEventListener("keyup", (e) => (teclas[e.key] = false));

// dentro do loop:
if (teclas["ArrowRight"]) jogador.x += 4;
if (teclas["ArrowLeft"]) jogador.x -= 4;
```

!!! tip "Delta time (bônus)"
    Para o jogo rodar na mesma velocidade em qualquer máquina, multiplique o movimento pelo tempo entre quadros (*delta time*), em vez de somar valores fixos. `requestAnimationFrame` passa um timestamp para você calcular isso.

## Caminhos: desenhando formas livres

Para a cena do Exercício 1 (telhado, montanhas), você precisa de linhas e polígonos:

```js
ctx.beginPath();
ctx.moveTo(50, 200);   // ponto inicial
ctx.lineTo(150, 100);  // linha até aqui (topo do telhado)
ctx.lineTo(250, 200);
ctx.closePath();       // fecha de volta ao início
ctx.fillStyle = "#c0392b";
ctx.fill();
```

| Método | Faz |
| :----- | :-- |
| `beginPath()` | Inicia um novo traçado |
| `moveTo(x, y)` | "Levanta a caneta" até o ponto |
| `lineTo(x, y)` | Traça linha até o ponto |
| `closePath()` | Liga o fim ao início |
| `stroke()` / `fill()` | Contorna / preenche |

!!! warning "Estado do contexto"
    Propriedades como `fillStyle` e `font` **permanecem** até você trocá-las. Defina a cor **antes** de cada `fill()`, ou use `ctx.save()` / `ctx.restore()` para isolar mudanças.

## Desenhando imagens e sprites

Além de formas, dá para desenhar imagens (base para personagens):

```js
const img = new Image();
img.src = "nave.png";
img.onload = () => ctx.drawImage(img, x, y, largura, altura);
```

Um **spritesheet** guarda vários quadros de animação em uma só imagem; você recorta o quadro atual com a versão completa de `drawImage(img, sx, sy, sw, sh, dx, dy, dw, dh)`.

## Por que `requestAnimationFrame` e não `setInterval`?

| | `requestAnimationFrame` | `setInterval` |
| :-- | :---------------------- | :------------ |
| Sincroniza com a tela | ✅ (~60 fps) | ❌ (tempo fixo) |
| Pausa em abas ocultas | ✅ (economiza bateria) | ❌ |
| Suavidade | Alta | Pode "tremer" |

## Delta time: velocidade igual em qualquer PC

Se você soma valores fixos por quadro, um monitor de 144 Hz roda o jogo mais rápido que um de 60 Hz. A solução é multiplicar pelo **tempo entre quadros**:

```js
let anterior = 0;
function loop(agora) {
  const dt = (agora - anterior) / 1000; // segundos desde o último quadro
  anterior = agora;

  bola.x += velocidade * dt; // movimento independente do fps

  requestAnimationFrame(loop);
}
requestAnimationFrame(loop);
```

## Mantendo o jogador na tela (Exercício 3)

Depois de mover, "prenda" a posição dentro dos limites com `Math.min`/`Math.max`:

```js
jogador.x = Math.max(0, Math.min(jogador.x, canvas.width - jogador.w));
```

## Exercícios

??? abstract "Exercício 1 — Cena estática"
    Desenhe no Canvas uma cena simples (ex.: sol, chão e uma casa) usando retângulos, círculos e texto. Nomeie as cores com comentários.

??? abstract "Exercício 2 — Bola quicando"
    Reproduza o exemplo da bola que quica nas bordas. Depois, adicione uma segunda bola com velocidade e cor diferentes.

??? abstract "Exercício 3 — Jogador controlável"
    Crie um quadrado que se move com as setas do teclado, **sem** sair da tela (limite-o às bordas do canvas).

!!! tip "Próxima Parada"
    Você tem loop, física e controle — está tudo pronto para montar um **jogo completo**! Antes, resolva a 👉 [**Lista 15**](../listas/15-lista.md).

## 📚 Referências

- [MDN — Tutorial de Canvas](https://developer.mozilla.org/pt-BR/docs/Web/API/Canvas_API/Tutorial)
- [MDN — Referência da API Canvas](https://developer.mozilla.org/pt-BR/docs/Web/API/CanvasRenderingContext2D)
- [MDN — Anatomia de um videogame (game loop)](https://developer.mozilla.org/pt-BR/docs/Games/Anatomy)
- [MDN — `requestAnimationFrame`](https://developer.mozilla.org/pt-BR/docs/Web/API/window/requestAnimationFrame)
- [MDN — Desenvolvimento de jogos](https://developer.mozilla.org/pt-BR/docs/Games)
