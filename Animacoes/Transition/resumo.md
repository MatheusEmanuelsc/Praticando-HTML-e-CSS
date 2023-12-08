**Índice:**
1. [**`transition-property`**](#transition-property)
2. [**`transition-duration`**](#transition-duration)
3. [**`transition-timing-function`**](#transition-timing-function)
4. [**`transition-delay`**](#transition-delay)

---

## `transition-property`
Define as propriedades CSS que serão aplicadas durante a transição.

**Exemplo:**
```css
.element {
  transition-property: width, height;
}
```
Neste exemplo, a transição será aplicada às propriedades `width` e `height` do elemento.

---

## `transition-duration`
Especifica a duração da transição. Pode ser definida em segundos (s) ou milissegundos (ms).

**Exemplo:**
```css
.element {
  transition-duration: 1s;
}
```
Neste exemplo, a transição terá uma duração de 1 segundo.

---

## `transition-timing-function`
Define a função de temporização da transição, controlando a aceleração e desaceleração.

**Exemplo:**
```css
.element {
  transition-timing-function: ease-in-out;
}
```
Neste exemplo, a função de temporização `ease-in-out` suaviza o início e o término da transição.

---

## `transition-delay`
Indica o tempo de espera antes que a transição comece.

**Exemplo:**
```css
.element {
  transition-delay: 0.5s;
}
```
Neste exemplo, a transição terá um atraso de 0.5 segundos antes de começar.

---

**Explicação Completa:**

A propriedade `transition` no CSS é utilizada para criar transições suaves entre diferentes estados de um elemento. Ela combina quatro propriedades individuais: `transition-property`, `transition-duration`, `transition-timing-function`, e `transition-delay`.

1. **`transition-property`**:
   - Define quais propriedades CSS específicas serão animadas durante a transição. Por exemplo, pode-se animar apenas a mudança de cor ou a largura do elemento.

2. **`transition-duration`**:
   - Especifica a duração da transição. Isso determina o tempo que a transição levará para ser concluída. A unidade pode ser em segundos (`s`) ou milissegundos (`ms`).

3. **`transition-timing-function`**:
   - Controla como a transição progride ao longo do tempo. Define a aceleração e desaceleração da animação. Funções comuns incluem `ease`, `linear`, `ease-in`, `ease-out`, entre outras.

4. **`transition-delay`**:
   - Indica o tempo de espera antes que a transição comece. Isso permite atrasar o início da animação.

**Exemplos:**
```css
/* Exemplo com todas as propriedades */
.element {
  transition-property: width, color;
  transition-duration: 1s;
  transition-timing-function: ease-in-out;
  transition-delay: 0.5s;
}

/* Exemplo simplificado sem todas as propriedades */
.element {
  transition: width 1s ease-in-out 0.5s, color 1s ease-in-out 0.5s;
}
```

Neste exemplo, a transição é aplicada à largura (`width`) e à cor (`color`) do elemento, com uma duração de 1 segundo, uma função de temporização suavizada (`ease-in-out`), e um atraso de 0.5 segundos antes de começar. A forma simplificada é uma abreviação que engloba todas as propriedades em uma única linha.