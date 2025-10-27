# Guia Completo: Transformações 2D em CSS

## O que são Transformações 2D?

Transformações 2D permitem **modificar a posição, tamanho, rotação e inclinação** de elementos HTML sem afetar o fluxo do documento. Os elementos transformados mantêm seu espaço original, mas são renderizados visualmente em nova posição/formato.

## Propriedade `transform`

Todas as transformações são aplicadas através da propriedade CSS `transform`:

```css
elemento {
  transform: função(valor);
}
```

## 🔄 Funções de Transformação 2D

### 1. `translate()` - Mover/Deslocar

Move o elemento nas direções X (horizontal) e/ou Y (vertical).

```css
/* Sintaxe */
transform: translate(x, y);
transform: translateX(valor);
transform: translateY(valor);
```

**Exemplos:**

```css
/* Mover 50px para direita e 100px para baixo */
.box1 {
  transform: translate(50px, 100px);
}

/* Mover apenas horizontalmente */
.box2 {
  transform: translateX(50px);
}

/* Mover apenas verticalmente */
.box3 {
  transform: translateY(-30px); /* negativo = para cima */
}

/* Porcentagens (relativo ao tamanho do elemento) */
.box4 {
  transform: translate(50%, 50%);
}

/* Centralizar elemento absolutamente posicionado */
.centralizado {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

**Valores:**
- Pixels: `50px`, `100px`
- Porcentagem: `50%`, `100%` (relativo ao tamanho do próprio elemento)
- Positivo: direita/baixo
- Negativo: esquerda/cima

### 2. `scale()` - Escala/Redimensionar

Aumenta ou diminui o tamanho do elemento.

```css
/* Sintaxe */
transform: scale(x, y);
transform: scaleX(valor);
transform: scaleY(valor);
```

**Exemplos:**

```css
/* Dobrar o tamanho (200%) */
.box1 {
  transform: scale(2);
}

/* Reduzir pela metade (50%) */
.box2 {
  transform: scale(0.5);
}

/* Escala diferente em cada eixo */
.box3 {
  transform: scale(1.5, 0.8); /* 150% largura, 80% altura */
}

/* Apenas largura */
.box4 {
  transform: scaleX(2);
}

/* Apenas altura */
.box5 {
  transform: scaleY(0.5);
}

/* Inverter horizontalmente (espelho) */
.espelho {
  transform: scaleX(-1);
}

/* Efeito hover de crescimento */
.card:hover {
  transform: scale(1.1);
  transition: transform 0.3s;
}
```

**Valores:**
- `1` = tamanho original (100%)
- `2` = dobro do tamanho (200%)
- `0.5` = metade do tamanho (50%)
- `0` = invisível
- Negativo = inverte a direção

### 3. `rotate()` - Rotação

Gira o elemento em torno de seu centro.

```css
/* Sintaxe */
transform: rotate(ângulo);
```

**Exemplos:**

```css
/* Rotacionar 45 graus (sentido horário) */
.box1 {
  transform: rotate(45deg);
}

/* Rotacionar anti-horário */
.box2 {
  transform: rotate(-90deg);
}

/* Meia volta */
.box3 {
  transform: rotate(180deg);
}

/* Volta completa */
.box4 {
  transform: rotate(360deg);
}

/* Usando radianos */
.box5 {
  transform: rotate(3.14159rad); /* ~180deg */
}

/* Usando turns (voltas) */
.box6 {
  transform: rotate(0.5turn); /* meia volta = 180deg */
}

/* Rotação infinita (animação) */
@keyframes girar {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.loading {
  animation: girar 2s linear infinite;
}
```

**Unidades:**
- `deg` (graus): 0deg a 360deg
- `rad` (radianos): 0rad a 6.28rad (2π)
- `turn` (voltas): 0turn a 1turn
- Positivo: sentido horário
- Negativo: sentido anti-horário

### 4. `skew()` - Inclinação/Distorção

Inclina o elemento nos eixos X e/ou Y.

```css
/* Sintaxe */
transform: skew(x-angle, y-angle);
transform: skewX(ângulo);
transform: skewY(ângulo);
```

**Exemplos:**

```css
/* Inclinar horizontalmente */
.box1 {
  transform: skewX(20deg);
}

/* Inclinar verticalmente */
.box2 {
  transform: skewY(10deg);
}

/* Inclinar em ambos os eixos */
.box3 {
  transform: skew(20deg, 10deg);
}

/* Efeito de perspectiva/paralaxe */
.paralax {
  transform: skewY(-5deg);
}

/* Texto itálico customizado */
.texto-inclinado {
  transform: skewX(-10deg);
}
```

**Valores:**
- Ângulos em `deg`, `rad` ou `turn`
- Positivo/negativo mudam a direção da inclinação

### 5. `matrix()` - Matriz de Transformação

Combina todas as transformações em uma única função matemática.

```css
transform: matrix(a, b, c, d, tx, ty);
```

**Raramente usado manualmente**, mas útil para entender:
- `a, d` = escala
- `b, c` = inclinação
- `tx, ty` = translação

```css
/* Equivalente a translate(50px, 100px) */
.box {
  transform: matrix(1, 0, 0, 1, 50, 100);
}
```

## 🔗 Combinando Transformações

Você pode aplicar **múltiplas transformações** separando-as por espaço:

```css
/* A ordem importa! */
.box {
  transform: translate(50px, 50px) rotate(45deg) scale(1.5);
}
```

**⚠️ IMPORTANTE: A ordem das transformações altera o resultado!**

```css
/* Resultado diferente */
.exemplo1 {
  transform: rotate(45deg) translate(100px, 0);
  /* Rotaciona primeiro, depois move na diagonal */
}

.exemplo2 {
  transform: translate(100px, 0) rotate(45deg);
  /* Move para direita, depois rotaciona no lugar */
}
```

**Exemplos práticos:**

```css
/* Card com efeito hover completo */
.card:hover {
  transform: translateY(-10px) scale(1.05) rotate(2deg);
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  transition: all 0.3s ease;
}

/* Botão com efeito de clique */
.button:active {
  transform: scale(0.95) translateY(2px);
}

/* Ícone animado */
.icon:hover {
  transform: rotate(360deg) scale(1.2);
  transition: transform 0.5s ease;
}
```

## 🎯 `transform-origin` - Ponto de Origem

Define o **ponto central** da transformação. Por padrão é o centro do elemento (`50% 50%`).

```css
transform-origin: x y;
```

**Valores:**

```css
/* Centro (padrão) */
transform-origin: center center;
transform-origin: 50% 50%;

/* Cantos */
transform-origin: top left;      /* canto superior esquerdo */
transform-origin: top right;     /* canto superior direito */
transform-origin: bottom left;   /* canto inferior esquerdo */
transform-origin: bottom right;  /* canto inferior direito */

/* Lados */
transform-origin: top center;
transform-origin: bottom center;
transform-origin: left center;
transform-origin: right center;

/* Valores personalizados */
transform-origin: 20px 40px;
transform-origin: 75% 25%;
```

**Exemplos práticos:**

```css
/* Porta abrindo (girar do lado esquerdo) */
.porta {
  transform-origin: left center;
  transform: rotateY(90deg);
}

/* Pêndulo (girar do topo) */
.pendulo {
  transform-origin: top center;
  animation: balanco 2s ease-in-out infinite;
}

@keyframes balanco {
  0%, 100% { transform: rotate(-20deg); }
  50% { transform: rotate(20deg); }
}

/* Menu dropdown (expandir do topo) */
.dropdown {
  transform-origin: top center;
  transform: scaleY(0);
  transition: transform 0.3s;
}

.dropdown.ativo {
  transform: scaleY(1);
}

/* Rotação de canto */
.canto {
  transform-origin: top right;
  transform: rotate(45deg);
}
```

## ⏱️ Transições com Transform

Transformações funcionam perfeitamente com `transition` para criar animações suaves:

```css
.elemento {
  transition: transform 0.3s ease;
}

.elemento:hover {
  transform: scale(1.2);
}
```

**Exemplos avançados:**

```css
/* Botão com múltiplos efeitos */
.btn {
  transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

.btn:hover {
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}

.btn:active {
  transform: translateY(-2px) scale(0.98);
}

/* Card flip */
.card {
  transition: transform 0.6s;
  transform-style: preserve-3d;
}

.card:hover {
  transform: rotateY(180deg);
}

/* Loading spinner */
@keyframes spin {
  to { transform: rotate(360deg); }
}

.spinner {
  animation: spin 1s linear infinite;
}
```

## 🎨 Exemplos Práticos Completos

### 1. Card Hover Elegante

```css
.card {
  width: 300px;
  height: 400px;
  background: white;
  border-radius: 10px;
  transition: all 0.4s ease;
}

.card:hover {
  transform: translateY(-20px) scale(1.03);
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}

.card img {
  transition: transform 0.4s ease;
}

.card:hover img {
  transform: scale(1.1);
}
```

### 2. Botão com Efeito de Pressão

```css
.button {
  padding: 15px 30px;
  background: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.button:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(0,123,255,0.4);
}

.button:active {
  transform: translateY(0);
  box-shadow: 0 2px 5px rgba(0,123,255,0.4);
}
```

### 3. Menu Hamburguer Animado

```css
.hamburger {
  width: 30px;
  height: 3px;
  background: black;
  position: relative;
  transition: transform 0.3s;
}

.hamburger::before,
.hamburger::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 3px;
  background: black;
  transition: all 0.3s;
}

.hamburger::before { top: -10px; }
.hamburger::after { top: 10px; }

.hamburger.ativo {
  transform: rotate(45deg);
}

.hamburger.ativo::before {
  transform: rotate(90deg);
  top: 0;
}

.hamburger.ativo::after {
  opacity: 0;
}
```

### 4. Galeria com Zoom

```css
.galeria-item {
  overflow: hidden;
  border-radius: 10px;
}

.galeria-item img {
  width: 100%;
  transition: transform 0.5s ease;
}

.galeria-item:hover img {
  transform: scale(1.2) rotate(5deg);
}
```

### 5. Loading Spinner

```css
.spinner {
  width: 50px;
  height: 50px;
  border: 5px solid #f3f3f3;
  border-top: 5px solid #3498db;
  border-radius: 50%;
  animation: girar 1s linear infinite;
}

@keyframes girar {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
```

### 6. Texto com Efeito Wave

```css
.wave span {
  display: inline-block;
  animation: wave 1.5s ease-in-out infinite;
}

.wave span:nth-child(1) { animation-delay: 0s; }
.wave span:nth-child(2) { animation-delay: 0.1s; }
.wave span:nth-child(3) { animation-delay: 0.2s; }
/* ... */

@keyframes wave {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}
```

### 7. Tooltip com Animação

```css
.tooltip {
  position: relative;
}

.tooltip::after {
  content: attr(data-tooltip);
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%) translateY(-10px) scale(0);
  background: black;
  color: white;
  padding: 5px 10px;
  border-radius: 5px;
  white-space: nowrap;
  opacity: 0;
  transition: all 0.3s ease;
}

.tooltip:hover::after {
  transform: translateX(-50%) translateY(-5px) scale(1);
  opacity: 1;
}
```

### 8. Shake Animation (Erro)

```css
@keyframes shake {
  0%, 100% { transform: translateX(0); }
  10%, 30%, 50%, 70%, 90% { transform: translateX(-10px); }
  20%, 40%, 60%, 80% { transform: translateX(10px); }
}

.erro {
  animation: shake 0.5s;
}
```

### 9. Pulse Animation (Atenção)

```css
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.1); }
}

.notificacao {
  animation: pulse 2s ease-in-out infinite;
}
```

### 10. Flip Card (Frente e Verso)

```css
.flip-card {
  perspective: 1000px;
  width: 300px;
  height: 400px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

.flip-card-back {
  transform: rotateY(180deg);
}
```

## 📊 Tabela de Referência Rápida

| Função | Sintaxe | Exemplo | Efeito |
|--------|---------|---------|--------|
| `translate()` | `translate(x, y)` | `translate(50px, 100px)` | Move elemento |
| `translateX()` | `translateX(valor)` | `translateX(50px)` | Move horizontal |
| `translateY()` | `translateY(valor)` | `translateY(100px)` | Move vertical |
| `scale()` | `scale(x, y)` | `scale(1.5)` | Redimensiona |
| `scaleX()` | `scaleX(valor)` | `scaleX(2)` | Escala horizontal |
| `scaleY()` | `scaleY(valor)` | `scaleY(0.5)` | Escala vertical |
| `rotate()` | `rotate(ângulo)` | `rotate(45deg)` | Rotaciona |
| `skew()` | `skew(x, y)` | `skew(20deg, 10deg)` | Inclina |
| `skewX()` | `skewX(ângulo)` | `skewX(20deg)` | Inclina horizontal |
| `skewY()` | `skewY(ângulo)` | `skewY(10deg)` | Inclina vertical |

## 🎯 Propriedades Relacionadas

```css
/* Ponto de origem da transformação */
transform-origin: center center;

/* Preservar 3D (para flip cards) */
transform-style: preserve-3d;

/* Ocultar face de trás */
backface-visibility: hidden;

/* Perspectiva para efeitos 3D */
perspective: 1000px;
```

## ⚠️ Considerações Importantes

### Performance
✅ **Transform é otimizado pelo GPU** - use para animações suaves
```css
/* BOM - usa GPU */
.elemento {
  transform: translateX(100px);
}

/* RUIM - não usa GPU */
.elemento {
  left: 100px; /* reflow/repaint */
}
```

### Acessibilidade
```css
/* Respeitar preferência de redução de movimento */
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```

### Compatibilidade
```css
/* Prefixos para navegadores antigos (raramente necessário hoje) */
.elemento {
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}
```

### Ordem de Transformações
```css
/* A ordem IMPORTA */
transform: translate(100px, 0) rotate(45deg);
/* ≠ */
transform: rotate(45deg) translate(100px, 0);
```

### Espaço Original
```css
/* Transform não afeta o layout */
.box {
  transform: translate(100px, 100px);
  /* O espaço original ainda é ocupado */
}
```

## 🚀 Dicas Avançadas

### 1. Combinação com Variáveis CSS

```css
:root {
  --escala: 1;
  --rotacao: 0deg;
}

.elemento {
  transform: scale(var(--escala)) rotate(var(--rotacao));
  transition: transform 0.3s;
}

.elemento:hover {
  --escala: 1.2;
  --rotacao: 10deg;
}
```

### 2. Efeitos Sequenciais

```css
.lista-item {
  opacity: 0;
  transform: translateY(20px);
  animation: aparecer 0.5s forwards;
}

.lista-item:nth-child(1) { animation-delay: 0.1s; }
.lista-item:nth-child(2) { animation-delay: 0.2s; }
.lista-item:nth-child(3) { animation-delay: 0.3s; }

@keyframes aparecer {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

### 3. Transform com Calc()

```css
.elemento {
  transform: translateX(calc(100% - 50px));
}
```

## ✅ Resumo Final

**Transformações 2D permitem:**
- ✨ Mover elementos (`translate`)
- 📏 Redimensionar (`scale`)
- 🔄 Rotacionar (`rotate`)
- 📐 Inclinar (`skew`)

**Boas práticas:**
- ✅ Use `transform` para animações (melhor performance)
- ✅ Combine com `transition` para suavidade
- ✅ Defina `transform-origin` quando necessário
- ✅ Teste em diferentes dispositivos
- ✅ Respeite preferências de acessibilidade
- ⚠️ Lembre que a ordem das transformações importa

**Transform é essencial para criar interfaces modernas, interativas e com animações fluidas!** 🚀