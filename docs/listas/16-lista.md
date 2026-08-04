# Lista 16 — Missão: Seu Primeiro Jogo Completo

!!! abstract "Briefing da Missão"
    A missão final ([Aula 16](../aulas/16-aula.md)): integre loop, física, entrada, colisão, placar e **estados** em um jogo jogável.

## 🎯 Exercícios

??? abstract "Missão 1 — Complete o Pong"
    Monte o Pong da aula com tela de **menu** ("Pressione Enter"), **jogo** e **fim** (mostra o placar e permite reiniciar).

??? abstract "Missão 2 — Seu jogo autoral"
    Crie um jogo simples original (coletar itens que caem, desviar de obstáculos, "flappy" minimalista) com loop, entrada, colisão e placar.

??? abstract "Missão 3 — Polimento"
    Adicione ao seu jogo **dois** destes: som ao pontuar, dificuldade crescente, recorde com `localStorage` ou tela de instruções.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista16/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── game.js
├── assets/           # sons e imagens (se usar)
└── README.md         # como jogar + controles
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista16`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 16"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista16.git
   git push -u origin main
   ```
3. (Recomendado) Ative o **GitHub Pages** e jogue direto pelo navegador.
4. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] Jogo tem estados de menu, jogo e fim, com reinício.
    - [ ] Colisão e placar funcionando.
    - [ ] README explica como jogar e os controles.
    - [ ] Pelo menos dois itens de polimento aplicados (Missão 3).
    - [ ] Repositório público `uni-udwmj-lista16` e link no Classroom.
