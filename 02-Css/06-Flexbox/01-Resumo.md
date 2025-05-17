**Flexbox CSS - Resumo em Formato README**

## Índice

1. [Introdução](#introdução)
2. [Propriedades do Flexbox](#propriedades-do-flexbox)
   - [display](#display)
   - [flex-direction](#flex-direction)
   - [justify-content](#justify-content)
   - [align-items](#align-items)
   - [flex](#flex)
   - [align-self](#align-self)
   - [order](#order)
3. [Exemplos](#exemplos)
   - [Exemplo 1: Layout Simples](#exemplo-1-layout-simples)
   - [Exemplo 2: Alinhamento e Justificação](#exemplo-2-alinhamento-e-justificação)
4. [Conclusão](#conclusão)

## Introdução

O Flexbox (Flexible Box Layout) é um modelo de layout em CSS que facilita o design responsivo e a criação de interfaces flexíveis. Ele permite organizar elementos de maneira eficiente em relação ao espaço disponível no contêiner.

## Propriedades do Flexbox

### display

Define o contexto de layout como um contêiner flexível ou um contêiner de grade.

### flex-direction

Determina a direção principal dos itens no contêiner flexível.

### justify-content

Alinha os itens ao longo do eixo principal do contêiner flexível.

### align-items

Alinha os itens ao longo do eixo transversal do contêiner flexível.

### flex

Combina as propriedades flex-grow, flex-shrink e flex-basis em uma única propriedade.

### align-self

Substitui a propriedade align-items para itens individuais.

### order

Especifica a ordem de um item flexível em relação aos outros itens no contêiner.

## Exemplos

### Exemplo 1: Layout Simples

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### Exemplo 2: Alinhamento e Justificação

```css
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
}

.item {
  order: 2;
}
```

## Conclusão

O Flexbox oferece um poderoso conjunto de ferramentas para criar layouts flexíveis e responsivos. Essas propriedades permitem adaptar o design de maneira eficaz, proporcionando uma experiência consistente em diferentes dispositivos e tamanhos de tela.

---

