
```markdown
# Guia do Box Model CSS

Bem-vindo ao guia do Box Model CSS. Este documento fornece uma visão geral das propriedades e conceitos associados ao Box Model, que é fundamental para o layout e design em CSS.

## Índice

1. [Introdução ao Box Model](#introdução-ao-box-model)
2. [Propriedade `width`](#propriedade-width)
3. [Propriedade `height`](#propriedade-height)
4. [Propriedades de Margem](#propriedades-de-margem)
5. [Propriedades de Preenchimento](#propriedades-de-preenchimento)
6. [Propriedades de Borda](#propriedades-de-borda)
7. [Propriedade `box-sizing`](#propriedade-box-sizing)

---

## Introdução ao Box Model

O Box Model é a representação visual de um elemento HTML como uma caixa retangular. Cada caixa consiste em conteúdo, preenchimento, borda e margem.

```css
div {
  width: 200px;
  height: 100px;
  margin: 10px;
  padding: 20px;
  border: 2px solid #333;
}
```

---

## Propriedade `width`

Define a largura do conteúdo da caixa.

Exemplo:

```css
div {
  width: 300px;
}
```

---

## Propriedade `height`

Define a altura do conteúdo da caixa.

Exemplo:

```css
div {
  height: 150px;
}
```

---

## Propriedades de Margem

As propriedades de margem controlam o espaçamento ao redor da caixa.

```css
div {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;
}
```

---

## Propriedades de Preenchimento

As propriedades de preenchimento controlam o espaço dentro da caixa, entre o conteúdo e a borda.

```css
div {
  padding-top: 15px;
  padding-right: 10px;
  padding-bottom: 15px;
  padding-left: 10px;
}
```

---

## Propriedades de Borda

As propriedades de borda definem a aparência da borda da caixa.

```css
div {
  border-width: 2px;
  border-style: dashed;
  border-color: #ff0000;
}
```

---

## Propriedade `box-sizing`

A propriedade `box-sizing` controla como a largura e a altura de um elemento são calculadas.

Exemplo:

```css
div {
  box-sizing: border-box;
}```
