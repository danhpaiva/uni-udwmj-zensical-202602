# Lista 14 — Missão: Matemática que Move

!!! abstract "Briefing da Missão"
    Prepare o terreno para os jogos ([Aula 14](../aulas/14-aula.md)): vetores, distância, colisão e trigonometria em JavaScript.

## 🎯 Exercícios

??? abstract "Missão 1 — Distância e colisão"
    Escreva `distancia(a, b)` e `colidem(a, b)` (círculos). Teste com pares de pontos, imprimindo se colidem ou não.

??? abstract "Missão 2 — Mira no alvo"
    Dado um objeto e um ponto-alvo, calcule `vx` e `vy` (usando `atan2`) para mover o objeto em linha reta até o alvo a uma velocidade fixa.

??? abstract "Missão 3 — Movimento suave (lerp)"
    Implemente `lerp(a, b, t)` que aproxima um valor de um alvo. Simule 10 quadros imprimindo a posição a cada passo e observe a suavização.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista14/
├── index.html        # roda os scripts e mostra saídas no console
└── js/
    ├── colisao.js
    ├── mira.js
    └── lerp.js
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista14`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 14"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista14.git
   git push -u origin main
   ```
3. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Distância usando `Math.hypot` (ou a fórmula completa).
    - [ ] Ângulos em **radianos**; conversão explícita quando necessário.
    - [ ] `lerp` produz aproximação suave (testado com prints).
    - [ ] Repositório público `uni-udwmj-lista14` e link no Classroom.
