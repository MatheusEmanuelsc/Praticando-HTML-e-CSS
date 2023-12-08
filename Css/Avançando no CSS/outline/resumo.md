**Resumo do Uso do Outline em CSS para README.md**

O `outline` em CSS é usado para adicionar uma linha de contorno em torno de um elemento HTML. Ele é frequentemente utilizado para destacar elementos focados, como links e botões, sem alterar o layout da página. Abaixo está um resumo das propriedades do `outline` com exemplos e explicações, formatado para um arquivo README.md:

```markdown
# Uso do Outline em CSS

O `outline` é uma propriedade CSS utilizada para adicionar uma linha de contorno ao redor de um elemento HTML sem afetar o layout da página.

## Propriedades do Outline

### `outline-style`

Define o estilo da linha de contorno.

Exemplo:
```css
/* Dotted outline */
element {
  outline-style: dotted;
}
```

### `outline-width`

Define a largura da linha de contorno.

Exemplo:
```css
/* Outline with 2px width */
element {
  outline-width: 2px;
}
```

### `outline-color`

Define a cor da linha de contorno.

Exemplo:
```css
/* Red outline */
element {
  outline-color: red;
}
```

### `outline-offset`

Define o espaçamento entre a borda do elemento e a linha de contorno.

Exemplo:
```css
/* Offset the outline by 5px */
element {
  outline-offset: 5px;
}
```

### `outline`

Combina todas as propriedades de `outline` em uma única declaração.

Exemplo:
```css
/* Shorthand for dotted red outline with 2px width */
element {
  outline: 2px dotted red;
}
```

## Uso Comum

O `outline` é frequentemente utilizado para destacar elementos focados, como links e botões, sem afetar o layout da página.

Exemplo:
```css
/* Highlight focused links with a blue outline */
a:focus {
  outline: 2px solid blue;
}
```

Lembre-se de ajustar os valores de acordo com os requisitos de design e estilo do seu projeto.


