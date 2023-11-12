# Resumo da Propriedade `object-fit` em CSS

A propriedade `object-fit` em CSS é usada para controlar como um elemento substituído (como uma imagem ou vídeo) é dimensionado dentro de seu contêiner. Aqui está um resumo dessa propriedade:

## `object-fit`

A propriedade `object-fit` define como o conteúdo substituído (imagem, vídeo, etc.) deve ser redimensionado para se adequar ao elemento.

### Valores Comuns:

#### 1. `fill`:

- O conteúdo é esticado para preencher completamente a caixa, mantendo a proporção.

```css
img {
  object-fit: fill;
}
```

#### 2. `contain`:

- O conteúdo é redimensionado para caber completamente dentro da caixa, mantendo a proporção.

```css
img {
  object-fit: contain;
}
```

#### 3. `cover`:

- O conteúdo é redimensionado para cobrir completamente a caixa, mantendo a proporção.

```css
img {
  object-fit: cover;
}
```

#### 4. `none`:

- O conteúdo mantém sua proporção original, mas pode vazar para fora da caixa.

```css
img {
  object-fit: none;
}
```

#### 5. `scale-down`:

- Similar a `contain`, mas o conteúdo é redimensionado para caber completamente sem ultrapassar seu tamanho original.

```css
img {
  object-fit: scale-down;
}
```

### Aplicações Práticas:

- **Imagens Responsivas:**
  - Use `cover` para garantir que a imagem cubra completamente o contêiner, mantendo a proporção.

```css
img {
  object-fit: cover;
}
```

- **Manter Proporção Original:**
  - Use `contain` para garantir que o conteúdo seja redimensionado para caber completamente sem distorção.

```css
img {
  object-fit: contain;
}
```

### Exemplo Completo:

```css
img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}
```

Neste exemplo, a propriedade `object-fit` é utilizada para garantir que a imagem cubra completamente o contêiner, mantendo a proporção, enquanto as propriedades `width` e `height` garantem que a imagem ocupe 100% da largura e altura do contêiner.

Adapte o valor de `object-fit` conforme necessário para atender aos requisitos específicos do seu layout.