# 📘 CSS `transition` – Resumo Completo

## 🧠 O que é `transition`?

A propriedade `transition` do CSS permite que mudanças nos valores de outras propriedades CSS ocorram de forma suave (animada) ao longo do tempo, em vez de instantaneamente.

Ela é muito usada para animar mudanças de cor, tamanho, posição, opacidade, entre outras propriedades visuais.

---

## 🔧 Como Utilizar

Você pode aplicar `transition` diretamente em um seletor. Exemplo básico:

```css
button {
  background-color: blue;
  transition: background-color 0.3s ease-in-out;
}

button:hover {
  background-color: red;
}
```

````

Nesse exemplo, ao passar o mouse sobre o botão, ele mudará suavemente de azul para vermelho em 0.3 segundos.

---

## 🧩 Sintaxe Completa

```css
transition: [propriedade] [duração] [função de tempo] [atraso];
```

Todos os valores podem ser combinados:

- `transition-property`
- `transition-duration`
- `transition-timing-function`
- `transition-delay`

---

## 📜 Lista das Propriedades Relacionadas

| Propriedade                  | Descrição                                                                                       |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `transition`                 | Shorthand (atalho) para definir as quatro propriedades abaixo.                                  |
| `transition-property`        | Define qual(is) propriedade(s) será(ão) animada(s). Ex: `background-color`, `all`, `transform`. |
| `transition-duration`        | Define o tempo de duração da transição. Ex: `0.3s`, `500ms`.                                    |
| `transition-timing-function` | Define o ritmo da transição (aceleração/desaceleração).                                         |
| `transition-delay`           | Define o tempo de espera antes da transição começar. Ex: `1s`.                                  |

---

## 🎛️ Valores comuns para `transition-timing-function`

| Valor                      | Descrição                                                             |
| -------------------------- | --------------------------------------------------------------------- |
| `ease`                     | Começa devagar, acelera no meio e desacelera no fim (padrão).         |
| `linear`                   | Velocidade constante do início ao fim.                                |
| `ease-in`                  | Começa devagar e acelera.                                             |
| `ease-out`                 | Começa rápido e desacelera.                                           |
| `ease-in-out`              | Combina `ease-in` e `ease-out`.                                       |
| `cubic-bezier(x, y, z, w)` | Define uma função personalizada de aceleração com pontos de controle. |

---

## 📦 Exemplos Completos

### 1. Transição de Opacidade

```css
div {
  opacity: 1;
  transition: opacity 0.5s ease-in;
}

div:hover {
  opacity: 0.5;
}
```

### 2. Transição de Transformação (Escala)

```css
img {
  transform: scale(1);
  transition: transform 0.3s ease;
}

img:hover {
  transform: scale(1.1);
}
```

### 3. Várias Propriedades ao Mesmo Tempo

```css
.box {
  width: 100px;
  height: 100px;
  background: green;
  transition: width 0.5s ease, background 0.5s ease-in;
}

.box:hover {
  width: 200px;
  background: blue;
}
```

---

## 💡 Dicas

- Use `all` com cautela em `transition-property`, pois pode afetar muitas propriedades inesperadas.
- Para animações mais complexas ou infinitas, considere usar `@keyframes` e `animation`.

---

## ✅ Conclusão

A propriedade `transition` é uma maneira poderosa e simples de melhorar a experiência do usuário com animações suaves. Saber combiná-la com pseudo-classes como `:hover`, `:focus` ou mudanças de classes via JavaScript pode criar interações ricas sem depender de bibliotecas externas.

---
````
