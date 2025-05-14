# Resumo da Propriedade `background-size` em CSS

A propriedade `background-size` em CSS permite controlar as dimensões da imagem de fundo em um elemento HTML. Aqui está um resumo dessa propriedade:

## `background-size`

A propriedade `background-size` define a dimensão da imagem de fundo em relação à caixa de conteúdo do elemento.

### Valores Comuns:

#### 1. `auto`:

- A imagem de fundo é exibida no tamanho original.

```css
div {
  background-size: auto;
}
```

#### 2. `cover`:

- A imagem é dimensionada para cobrir completamente a caixa de conteúdo, mantendo a proporção.

```css
div {
  background-size: cover;
}
```

#### 3. `contain`:

- A imagem é dimensionada para caber inteiramente dentro da caixa de conteúdo, mantendo a proporção.

```css
div {
  background-size: contain;
}
```

#### 4. Valores Numéricos:

- Especifica largura e altura como valores numéricos ou percentuais.

```css
div {
  background-size: 50% 100%;
}
```

### Aplicações Práticas:

- **Imagens Responsivas:**
  - Use `cover` para garantir que a imagem cubra completamente o contêiner, mantendo a proporção.

```css
div {
  background-size: cover;
}
```

- **Imagens de Fundo para Texto:**
  - Use `contain` para garantir que a imagem fique completamente visível dentro do contêiner.

```css
div {
  background-size: contain;
}
```

### Exemplo Completo:

```css
div {
  background-image: url('imagem.jpg');
  background-size: cover;
  background-repeat: no-repeat;
}
```

Neste exemplo, a imagem de fundo é definida para cobrir a caixa de conteúdo do elemento, sem repetição.

Lembre-se de adaptar o valor de `background-size` conforme necessário para atender aos requisitos específicos do seu layout.