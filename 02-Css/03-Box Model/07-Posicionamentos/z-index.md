# README: Z-Index no CSS

## Visão Geral

O `z-index` é uma propriedade do CSS que controla a sobreposição de elementos posicionados no eixo Z, determinando qual elemento será exibido sobre os outros. Quanto maior o valor do `z-index`, maior a sobreposição.

### Exemplo Básico:

```css
.element1 {
  position: relative;
  z-index: 1;
}

.element2 {
  position: relative;
  z-index: 2;
}
```

## Como Funciona

1. **Posicionamento:**
   - A propriedade `z-index` só tem efeito em elementos que foram posicionados (`position` diferente de `static`).
   - Elementos posicionados criam um contexto de sobreposição para seus descendentes.

2. **Valores:**
   - Os valores do `z-index` são números inteiros.
   - Quanto maior o número, maior a sobreposição.

### Exemplo de Sobreposição Básica:

```css
.upper-element {
  position: relative;
  z-index: 2;
}

.lower-element {
  position: relative;
  z-index: 1;
}
```

## Considerações Importantes

- **Contexto de Sobreposição:**
  - O `z-index` só afeta elementos dentro do mesmo contexto de sobreposição. Um elemento com `z-index: 2` em um contexto não se sobreporá a um elemento com `z-index: 1` em outro contexto.

- **Stacking Context:**
  - Alguns elementos criam um novo contexto de sobreposição (um "stacking context"), o que pode afetar a ordem de sobreposição. Exemplos incluem elementos com `position: fixed` e `position: absolute` com um valor diferente de `auto` para `z-index`.

## Como Usar

1. **Atribuição de Valor:**
   - Atribua valores de `z-index` para controlar a sobreposição de elementos.
   - Certifique-se de que os elementos estejam posicionados.

2. **Contexto de Sobreposição:**
   - Esteja ciente do contexto de sobreposição para garantir o comportamento desejado.

## Exemplos Avançados

- **Stacking Context:**
  - Alguns elementos podem criar um novo contexto de sobreposição, alterando o comportamento do `z-index`.

```css
.stacking-context {
  position: relative;
  z-index: 1;
}

.child-element {
  position: absolute;
  z-index: 2;
}
```

Este README fornece uma introdução básica à propriedade `z-index` no CSS. Consulte a documentação do CSS para informações mais detalhadas e casos de uso avançados.