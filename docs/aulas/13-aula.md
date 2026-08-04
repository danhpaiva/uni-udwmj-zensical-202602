# Aula 13 — Desenvolvimento Mobile Híbrido e Multiplataforma

!!! info "Objetivos da aula"
    - Diferenciar apps **nativos, híbridos e PWA**.
    - Entender o modelo **multiplataforma**.
    - Transformar uma web app em **PWA** instalável.

## Três caminhos para um app

=== "Nativo"
    Escrito na linguagem da plataforma (Kotlin/Java no Android, Swift no iOS). **Máximo desempenho** e acesso total ao hardware, mas exige **um código por plataforma**.

=== "Híbrido / Multiplataforma"
    **Um código** roda em Android e iOS. Ferramentas como **Ionic/Capacitor** e **React Native** empacotam tecnologias web (ou próximas) em um app instalável.

=== "PWA"
    Um **site** que se comporta como app: instalável, funciona offline e envia notificações. Sem loja de apps. É o caminho mais próximo do que já sabemos.

| Critério | Nativo | Híbrido | PWA |
| :------- | :----- | :------ | :-- |
| Base de código | Uma por SO | Única | Única |
| Loja de apps | Sim | Sim | Não (opcional) |
| Acesso a hardware | Total | Bom (plugins) | Limitado |
| Custo/velocidade | Alto | Médio | Baixo |

!!! info "Escreva uma vez, rode em todo lugar"
    A promessa do multiplataforma é reduzir custo e tempo mantendo **uma** base de código. O preço costuma ser um pequeno teto de desempenho e dependência de plugins para recursos nativos.

## Do site ao app: Capacitor

O **Capacitor** (do time do Ionic) empacota seu HTML/CSS/JS em um projeto nativo:

```bash
npm install @capacitor/core @capacitor/cli
npx cap init
npx cap add android
npx cap open android   # abre no Android Studio
```

## PWA: o meio mais acessível

Uma PWA precisa de dois ingredientes:

**1. Manifesto** (`manifest.json`) — descreve o app:

```json
{
  "name": "Minha PWA",
  "short_name": "PWA",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#7c4dff",
  "icons": [{ "src": "icon-192.png", "sizes": "192x192", "type": "image/png" }]
}
```

**2. Service Worker** — um script que roda em segundo plano e permite cache/offline:

```js
// sw.js
self.addEventListener("install", (e) => {
  e.waitUntil(
    caches.open("v1").then((cache) => cache.addAll(["/", "/index.html", "/style.css"]))
  );
});

self.addEventListener("fetch", (e) => {
  e.respondWith(caches.match(e.request).then((r) => r || fetch(e.request)));
});
```

Registrando no HTML:

```js
if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("/sw.js");
}
```

!!! warning "HTTPS obrigatório"
    Service Workers só funcionam em **HTTPS** (ou `localhost`). O GitHub Pages já serve por HTTPS — perfeito para testar.

## Como o híbrido funciona por dentro: WebView

Um app híbrido roda seu HTML/CSS/JS dentro de uma **WebView** — um navegador "sem barra de endereço" embutido no app nativo. Ferramentas como o **Capacitor** ainda expõem **plugins** que dão acesso a recursos do aparelho (câmera, GPS, notificações) por meio de uma API JavaScript:

```js
import { Camera } from "@capacitor/camera";
const foto = await Camera.getPhoto({ quality: 90 });
```

## O ciclo de vida do Service Worker

O Service Worker (SW) do Exercício 3 passa por fases bem definidas:

```mermaid
graph LR
    R[register] --> I[install<br/>faz cache inicial]
    I --> A[activate<br/>limpa caches antigos]
    A --> F[fetch<br/>intercepta requisições]
```

!!! warning "O SW controla a página só no próximo carregamento"
    Após registrar pela primeira vez, o Service Worker só assume o controle no **próximo** `reload`. E lembre-se: ele exige **HTTPS** (ou `localhost`).

## Estratégias de cache

O que fazer quando a página pede um arquivo? Há padrões conhecidos:

| Estratégia | Comportamento | Boa para |
| :--------- | :------------ | :------- |
| **Cache First** | Usa o cache; só vai à rede se faltar | Arquivos fixos (CSS, ícones) |
| **Network First** | Tenta a rede; cai no cache se offline | Dados que mudam |
| **Stale-While-Revalidate** | Serve o cache e atualiza em segundo plano | Equilíbrio geral |

O exemplo desta aula usa **Cache First** (`caches.match(...) || fetch(...)`).

## Decidindo a abordagem (Exercício 1)

Use estas perguntas como guia:

- Precisa de **desempenho gráfico** máximo (jogos 3D pesados)? → Nativo.
- Quer **uma base de código** para Android + iOS com bom acesso a hardware? → Híbrido.
- É essencialmente um **site** que ganharia com instalação e offline, sem loja? → PWA.
- Orçamento e prazo **curtos**? → PWA ou híbrido tendem a ser mais baratos.

## Exercícios

??? abstract "Exercício 1 — Comparação fundamentada"
    Escolha um app que você usa e argumente qual abordagem (nativo, híbrido ou PWA) faria mais sentido para ele, considerando custo, hardware e público.

??? abstract "Exercício 2 — Manifesto"
    Crie um `manifest.json` para uma página sua, com nome, ícones e cores. Linke-o no `<head>` e verifique na aba *Application* do DevTools se o app é "instalável".

??? abstract "Exercício 3 — Offline básico"
    Adicione um Service Worker que faça cache dos arquivos principais. Teste desligando a rede no DevTools e recarregando a página.

!!! tip "Próxima Parada"
    Mudamos de assunto: começa nossa jornada por **jogos digitais**, e ela começa com... matemática! Antes, resolva a 👉 [**Lista 13**](../listas/13-lista.md).

## 📚 Referências

- [MDN — Progressive Web Apps](https://developer.mozilla.org/pt-BR/docs/Web/Progressive_web_apps)
- [web.dev — Learn PWA](https://web.dev/learn/pwa/)
- [MDN — Usando Service Workers](https://developer.mozilla.org/pt-BR/docs/Web/API/Service_Worker_API/Using_Service_Workers)
- [Documentação do Capacitor](https://capacitorjs.com/docs)
- [MDN — Manifesto de Web App](https://developer.mozilla.org/pt-BR/docs/Web/Manifest)
