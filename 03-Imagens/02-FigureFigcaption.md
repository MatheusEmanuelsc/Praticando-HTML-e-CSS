````md
# 🖼️ `<figure>` e `<figcaption>` no HTML

## 📌 O que são?

### `<figure>`

Elemento semântico usado para **agrupar conteúdo visual ou ilustrativo**, como imagens, gráficos, vídeos, tabelas, trechos de código etc.

### `<figcaption>`

Elemento utilizado dentro de `<figure>` para **inserir uma legenda descritiva** sobre o conteúdo.

---

## 🧠 Quando usar?

- Quando quiser **associar uma legenda a uma imagem, vídeo ou outro conteúdo**.
- Para destacar visualmente uma figura com contexto.
- Melhora a **acessibilidade e semântica** do HTML.

---

## ✅ Estrutura básica

```html
<figure>
  <img src="imagem.jpg" alt="Descrição da imagem" />
  <figcaption>Legenda explicando o conteúdo da imagem</figcaption>
</figure>
```
````

---

## 📷 Exemplo com imagem

```html
<figure>
  <img src="https://via.placeholder.com/400x200" alt="Gráfico de barras" />
  <figcaption>
    Figura 1: Exemplo de gráfico de barras para visualização de dados.
  </figcaption>
</figure>
```

---

## 🎞️ Exemplo com vídeo

```html
<figure>
  <video controls width="400">
    <source src="video.mp4" type="video/mp4" />
    Seu navegador não suporta vídeos.
  </video>
  <figcaption>Vídeo 1: Demonstração do produto em funcionamento.</figcaption>
</figure>
```

---

## 🧾 Exemplo com código

```html
<figure>
  <pre><code>const soma = (a, b) => a + b;</code></pre>
  <figcaption>
    Exemplo de função em JavaScript que soma dois números.
  </figcaption>
</figure>
```

---

## 💡 Boas práticas

- Sempre use `alt` na imagem para acessibilidade.
- Use `<figcaption>` **logo após ou antes** do conteúdo, dentro do `<figure>`.
- Não limite o uso de `<figure>` apenas a imagens; pode conter qualquer elemento que represente uma "figura com contexto".

---

## ⚠️ O que evitar

- Usar `<figcaption>` fora de `<figure>` — ele **deve estar dentro do `<figure>`**.
- Colocar legendas em parágrafos fora do contexto visual.
- Usar `<figure>` apenas para layout, sem propósito semântico.

---

## 📚 Benefícios

- **Acessibilidade**: Ajuda leitores de tela a identificar e descrever conteúdos visuais.
- **Semântica**: Melhora o significado do conteúdo para navegadores e mecanismos de busca.
- **Organização**: Mantém figuras e legendas agrupadas no código.

---

## 🔁 Ordem de elementos

Ambas as ordens são válidas:

```html
<!-- figcaption após o conteúdo -->
<figure>
  <img src="exemplo.jpg" alt="Exemplo" />
  <figcaption>Legenda da imagem</figcaption>
</figure>

<!-- figcaption antes do conteúdo -->
<figure>
  <figcaption>Legenda da imagem</figcaption>
  <img src="exemplo.jpg" alt="Exemplo" />
</figure>
```

---

Se quiser, posso gerar um layout estilizado com CSS para exibir `<figure>` e `<figcaption` com formatação elegante. Deseja?

```

```
