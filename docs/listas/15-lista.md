# Lista 15 — Missão: Pixels em Movimento

!!! abstract "Briefing da Missão"
    Desenhe e anime ([Aula 15](../aulas/15-aula.md)): API **Canvas 2D**, **game loop** e captura de teclado.

## 🎯 Exercícios

??? abstract "Missão 1 — Cena estática"
    Desenhe uma cena simples (ex.: sol, chão e casa) com retângulos, círculos e texto. Comente as cores no código.

??? abstract "Missão 2 — Bola quicando"
    Reproduza a bola que quica nas bordas com `requestAnimationFrame`. Depois adicione uma segunda bola com velocidade e cor diferentes.

??? abstract "Missão 3 — Jogador controlável"
    Quadrado que se move com as setas do teclado, **sem** sair da tela (limitado às bordas do canvas).

## 📁 Estrutura sugerida

```text
uni-udwmj-lista15/
├── index.html        # contém o <canvas>
├── css/
│   └── style.css
└── js/
    ├── cena.js
    ├── bola.js
    └── jogador.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista15`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 15"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista15.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Loop com `requestAnimationFrame` e `clearRect` no início.
    - [ ] Bola quica corretamente nas 4 bordas.
    - [ ] Jogador respeita os limites da tela.
    - [ ] Repositório público `uni-udwmj-lista15` e link no Classroom.
