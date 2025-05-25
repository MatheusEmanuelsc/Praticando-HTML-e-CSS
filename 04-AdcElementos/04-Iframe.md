````md
# 🧱 Elemento `<iframe>` no HTML

## 📌 O que é?

O elemento `<iframe>` (inline frame) permite **incorporar outro documento HTML dentro do documento atual**, como se fosse uma "janela" que mostra outra página.

---

## ✅ Estrutura básica

```html
<iframe src="https://exemplo.com" width="600" height="400"></iframe>
```
````

---

## 🧾 Atributos mais comuns

| Atributo          | Descrição                                                                   |
| ----------------- | --------------------------------------------------------------------------- |
| `src`             | URL da página a ser incorporada.                                            |
| `width`           | Largura do iframe (em pixels ou `%`).                                       |
| `height`          | Altura do iframe.                                                           |
| `title`           | Descrição do conteúdo incorporado (usado para acessibilidade).              |
| `name`            | Identificador do iframe (pode ser usado como alvo de links ou formulários). |
| `allowfullscreen` | Permite que o conteúdo do iframe use **tela cheia**.                        |
| `loading`         | Pode ser `"lazy"` para carregamento lento (melhora o desempenho).           |
| `referrerpolicy`  | Controla se o navegador envia o `Referer`.                                  |
| `sandbox`         | Restringe ações do conteúdo embutido (segurança).                           |
| `allow`           | Especifica permissões (ex: câmera, microfone, geolocalização, etc).         |

---

## 🛡️ Segurança com `sandbox`

O atributo `sandbox` impõe **restrições ao conteúdo do iframe**, como:

```html
<iframe src="..." sandbox></iframe>
```

Você também pode permitir recursos específicos:

```html
<iframe src="..." sandbox="allow-scripts allow-forms"></iframe>
```

### Permissões possíveis com `sandbox`:

- `allow-forms` – Permite envio de formulários.
- `allow-modals` – Permite abertura de modais.
- `allow-orientation-lock` – Permite bloquear orientação.
- `allow-popups` – Permite popups.
- `allow-same-origin` – Permite acesso ao mesmo domínio.
- `allow-scripts` – Permite scripts.
- `allow-top-navigation` – Permite redirecionar a página pai.

> ⚠️ Sem `allow-same-origin`, o conteúdo é tratado como de outro domínio, mesmo que seja o mesmo site.

---

## 🌐 Exemplo prático

```html
<iframe
  src="https://www.wikipedia.org"
  width="800"
  height="500"
  title="Wikipedia"
  loading="lazy"
  sandbox="allow-scripts allow-same-origin"
></iframe>
```

---

## ❌ Limitações

- Nem todos os sites permitem ser carregados via iframe (usam cabeçalhos como `X-Frame-Options: DENY` ou `Content-Security-Policy`).
- Iframes podem causar **problemas de desempenho** e **segurança**, se mal utilizados.
- Evite usar iframe para conteúdo dinâmico ou que precisa de SEO.

---

## 📦 Uso comum de iframe

- Vídeos (YouTube, Vimeo):

  ```html
  <iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/VIDEO_ID"
    allowfullscreen
  ></iframe>
  ```

- Google Maps:

  ```html
  <iframe
    src="https://www.google.com/maps/embed?pb=..."
    width="600"
    height="450"
    allowfullscreen
  ></iframe>
  ```

- Ferramentas externas (ex: visualizadores, formulários, gráficos).

---

## ✔️ Boas práticas

- Sempre use `title` para acessibilidade.
- Use `loading="lazy"` quando possível.
- Prefira `sandbox` para segurança.
- Evite conteúdo crítico dentro de iframes.
- Verifique se o site externo permite ser embutido.

---
