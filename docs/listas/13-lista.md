# Lista 13 — Missão: Da Web para o Bolso (PWA)

!!! abstract "Briefing da Missão"
    Leve a web para o celular ([Aula 13](../aulas/13-aula.md)): transforme um site em **PWA** instalável e offline.

## 🎯 Exercícios

??? abstract "Missão 1 — Comparação fundamentada"
    Escolha um app que você usa e argumente qual abordagem (**nativo**, **híbrido** ou **PWA**) faz mais sentido, considerando custo, hardware e público.

??? abstract "Missão 2 — Manifesto"
    Crie um `manifest.json` (nome, ícones, cores), linke-o no `<head>` e verifique na aba *Application* do DevTools se o app é "instalável" (print no README).

??? abstract "Missão 3 — Offline básico"
    Adicione um **Service Worker** que faça cache dos arquivos principais. Teste desligando a rede no DevTools e recarregando.

## 📁 Estrutura sugerida

```text
uni-udwmj-lista13/
├── index.html
├── manifest.json
├── sw.js
├── icons/
│   └── icon-192.png
└── README.md         # comparação + prints do "instalável"
```

## 🚀 Passo a passo da entrega

1. Crie o repositório **público** **`uni-udwmj-lista13`**.
2. Suba o código:
   ```bash
   git init
   git add .
   git commit -m "feat: resolve lista 13"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/uni-udwmj-lista13.git
   git push -u origin main
   ```
3. (Opcional) Ative o **GitHub Pages** para testar a PWA em HTTPS.
4. **Entregue o link do repositório** no **Google Classroom**.

!!! check "Checklist de qualidade"
    - [ ] `manifest.json` válido e linkado no `<head>`.
    - [ ] Service Worker registrado e fazendo cache dos arquivos base.
    - [ ] App carrega mesmo com a rede desligada (teste no DevTools).
    - [ ] Comparação com argumentos de custo/hardware/público.
    - [ ] Repositório público `uni-udwmj-lista13` e link no Classroom.
