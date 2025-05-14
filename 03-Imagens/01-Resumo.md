### Adicionando e Estilizando Imagens em HTML e CSS

Este documento fornece exemplos práticos de como adicionar e estilizar imagens em uma página web usando HTML e CSS. Abaixo estão duas abordagens: a tradicional `<img>` e uma abordagem avançada usando a tag `<picture>` e a propriedade `srcset`.

#### **1. Adicionando Imagem com `<img>`:**

##### Estrutura HTML (`index.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Adicionar Imagem com &lt;img&gt;</title>
</head>
<body>

  <h1>Exemplo de Adição de Imagem com &lt;img&gt;</h1>

  <img src="caminho/da/imagem.jpg" alt="Descrição da Imagem">

</body>
</html>
```

##### Resumo:

- **`<img>`:**
  - A tag `<img>` é usada para incorporar imagens em uma página HTML.
  
- **`src`:**
  - O atributo `src` especifica o caminho da imagem.

- **`alt`:**
  - O atributo `alt` fornece texto alternativo para a imagem, importante para acessibilidade e SEO.

#### **2. Estilizando Imagem com CSS:**

##### Estrutura HTML (`index.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Estilizando Imagem com CSS</title>
</head>
<body>

  <h1>Exemplo de Estilização de Imagem com CSS</h1>

  <img src="caminho/da/imagem.jpg" alt="Descrição da Imagem" class="styled-image">

</body>
</html>
```

##### Estilos CSS (`styles.css`):

```css
/* styles.css */

/* Estilo personalizado para a classe styled-image */
.styled-image {
  width: 100%; /* Define a largura da imagem como 100% do contêiner pai */
  border-radius: 10px; /* Adiciona cantos arredondados à imagem */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3); /* Adiciona uma sombra à imagem */
}
```

##### Resumo:

- **Estilizando Imagens:**
  - Adicione uma classe à tag `<img>` para aplicar estilos específicos.
  
- **Propriedades CSS:**
  - **`width`:** Define a largura da imagem.
  - **`border-radius`:** Adiciona cantos arredondados à imagem.
  - **`box-shadow`:** Adiciona uma sombra à imagem.

#### **3. Tag `<picture>` e `srcset` para Responsividade:**

##### Estrutura HTML (`index.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Tag &lt;picture&gt; e srcset</title>
</head>
<body>

  <h1>Exemplo de Utilização da Tag &lt;picture&gt; e srcset</h1>

  <picture>
    <source media="(min-width: 768px)" srcset="caminho/da/imagem-large.jpg">
    <img src="caminho/da/imagem-small.jpg" alt="Descrição da Imagem">
  </picture>

</body>
</html>
```

##### Resumo:

- **`<picture>`:**
  - A tag `<picture>` permite especificar várias fontes de imagem para diferentes condições de visualização.

- **`<source>`:**
  - A tag `<source>` fornece diferentes fontes de imagem com base em condições específicas, como largura de tela (`media="(min-width: 768px)"`).

- **`srcset`:**
  - A propriedade `srcset` na tag `<img>` permite fornecer várias versões da imagem para diferentes densidades de pixels e tamanhos de tela.

Estes são exemplos de como adicionar e estilizar imagens em HTML e CSS, incluindo uma abordagem avançada para tornar as imagens responsivas usando a tag `<picture>` e a propriedade `srcset`. Ajuste conforme necessário para atender aos requisitos específicos do seu projeto.