# Guia Completo: Transformações 3D em CSS

## O que são Transformações 3D?

Transformações 3D permitem manipular elementos HTML no **espaço tridimensional** (X, Y e Z), criando efeitos de profundidade, perspectiva e movimento em três dimensões.

## 🎯 Propriedades Essenciais para 3D

### 1. `perspective` - Profundidade Visual

Define a **distância entre o observador e o plano Z=0**. Quanto menor o valor, mais dramático o efeito 3D.

```css
/* Aplicar no elemento pai */
.container {
  perspective: 1000px;
}

/* Ou diretamente no elemento */
.elemento {
  transform: perspective(1000px) rotateY(45deg);
}
```

**Valores:**
- `none` = sem perspectiva (padrão)
- `500px` = perspectiva intensa (objetos muito próximos)
- `1000px` = perspectiva moderada (recomendado)
- `2000px` = perspectiva suave (objetos distantes)

**Exemplos:**

```css
/* Comparação de perspectivas */
.perspectiva-intensa {
  perspective: 300px;
  /* Efeito 3D muito dramático */
}

.perspectiva-moderada {
  perspective: 1000px;
  /* Efeito 3D equilibrado */
}

.perspectiva-suave {
  perspective: 2000px;
  /* Efeito 3D sutil */
}
```

### 2. `perspective-origin` - Ponto de Vista

Define de **onde** você está olhando o elemento 3D.

```css
.container {
  perspective: 1000px;
  perspective-origin: center center; /* padrão */
}
```

**Valores:**

```css
/* Centro (padrão) */
perspective-origin: center center;
perspective-origin: 50% 50%;

/* Olhando de cima */
perspective-origin: center top;

/* Olhando de baixo */
perspective-origin: center bottom;

/* Olhando da esquerda */
perspective-origin: left center;

/* Olhando da direita */
perspective-origin: right center;

/* Valores personalizados */
perspective-origin: 75% 25%;
perspective-origin: 200px 100px;
```

### 3. `transform-style` - Preservar 3D

Define se os elementos filhos devem preservar suas transformações 3D.

```css
.container {
  transform-style: preserve-3d; /* Mantém 3D nos filhos */
  /* ou */
  transform-style: flat; /* Achata para 2D (padrão) */
}
```

**⚠️ CRÍTICO para efeitos 3D complexos!**

```css
/* NECESSÁRIO para flip cards, cubos, etc */
.flip-card-inner {
  transform-style: preserve-3d;
}
```

### 4. `backface-visibility` - Visibilidade da Face de Trás

Define se a parte de trás do elemento é visível quando rotacionado.

```css
.elemento {
  backface-visibility: visible; /* padrão */
  /* ou */
  backface-visibility: hidden; /* oculta a face de trás */
}
```

**Uso comum em flip cards:**

```css
.card-front,
.card-back {
  backface-visibility: hidden;
}

.card-back {
  transform: rotateY(180deg);
}
```

## 🔄 Funções de Transformação 3D

### 1. `translate3d()` - Mover em 3D

Move o elemento nos três eixos (X, Y, Z).

```css
/* Sintaxe */
transform: translate3d(x, y, z);
transform: translateX(valor);
transform: translateY(valor);
transform: translateZ(valor);
```

**Exemplos:**

```css
/* Mover para frente (em direção ao usuário) */
.elemento1 {
  transform: translateZ(100px);
}

/* Mover para trás (afastando do usuário) */
.elemento2 {
  transform: translateZ(-100px);
}

/* Mover em todos os eixos */
.elemento3 {
  transform: translate3d(50px, 50px, 100px);
}

/* Efeito de profundidade em cards */
.card:hover {
  transform: translateZ(50px);
}

/* Parallax simples */
.camada1 { transform: translateZ(0px); }
.camada2 { transform: translateZ(-50px); }
.camada3 { transform: translateZ(-100px); }
```

### 2. `scale3d()` - Escala em 3D

Redimensiona nos três eixos.

```css
/* Sintaxe */
transform: scale3d(x, y, z);
transform: scaleZ(valor);
```

**Exemplos:**

```css
/* Escala uniforme em 3D */
.elemento1 {
  transform: scale3d(1.5, 1.5, 1.5);
}

/* Escala apenas no eixo Z */
.elemento2 {
  transform: scaleZ(2);
}

/* Achatando no eixo Z */
.elemento3 {
  transform: scaleZ(0.5);
}
```

### 3. `rotate3d()` - Rotação em 3D

Rotaciona em torno de um vetor 3D personalizado.

```css
/* Sintaxe */
transform: rotate3d(x, y, z, ângulo);
transform: rotateX(ângulo);
transform: rotateY(ângulo);
transform: rotateZ(ângulo);
```

#### `rotateX()` - Rotação no eixo X (horizontal)

Gira como uma **porta horizontal** (cima/baixo).

```css
/* Inclinar para trás */
.elemento1 {
  transform: rotateX(45deg);
}

/* Inclinar para frente */
.elemento2 {
  transform: rotateX(-45deg);
}

/* Virar de ponta-cabeça */
.elemento3 {
  transform: rotateX(180deg);
}

/* Efeito de queda */
@keyframes cair {
  from { transform: rotateX(0deg); }
  to { transform: rotateX(90deg); }
}
```

#### `rotateY()` - Rotação no eixo Y (vertical)

Gira como uma **porta vertical** (esquerda/direita).

```css
/* Girar para direita */
.elemento1 {
  transform: rotateY(45deg);
}

/* Girar para esquerda */
.elemento2 {
  transform: rotateY(-45deg);
}

/* Virar completamente */
.elemento3 {
  transform: rotateY(180deg);
}

/* Flip card horizontal */
.card:hover {
  transform: rotateY(180deg);
}
```

#### `rotateZ()` - Rotação no eixo Z (profundidade)

Igual a `rotate()` em 2D - gira no próprio plano.

```css
.elemento {
  transform: rotateZ(45deg);
  /* Mesmo que rotate(45deg) */
}
```

#### `rotate3d()` - Rotação em vetor customizado

```css
/* Rotacionar em torno de um vetor personalizado */
.elemento {
  transform: rotate3d(1, 1, 0, 45deg);
  /* x=1, y=1, z=0, ângulo=45deg */
}
```

## 🎨 Exemplos Práticos Completos

### 1. Flip Card Básico

```html
<div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      FRENTE
    </div>
    <div class="flip-card-back">
      VERSO
    </div>
  </div>
</div>
```

```css
.flip-card {
  width: 300px;
  height: 400px;
  perspective: 1000px;
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
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2em;
}

.flip-card-front {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

.flip-card-back {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  color: white;
  transform: rotateY(180deg);
}
```

### 2. Flip Card Vertical

```css
.flip-vertical:hover .flip-card-inner {
  transform: rotateX(180deg);
}
```

### 3. Cubo 3D Rotativo

```html
<div class="cubo-container">
  <div class="cubo">
    <div class="face frente">Frente</div>
    <div class="face tras">Trás</div>
    <div class="face direita">Direita</div>
    <div class="face esquerda">Esquerda</div>
    <div class="face topo">Topo</div>
    <div class="face base">Base</div>
  </div>
</div>
```

```css
.cubo-container {
  width: 200px;
  height: 200px;
  perspective: 1000px;
  margin: 100px auto;
}

.cubo {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  animation: girar-cubo 10s infinite linear;
}

@keyframes girar-cubo {
  from { transform: rotateX(0deg) rotateY(0deg); }
  to { transform: rotateX(360deg) rotateY(360deg); }
}

.face {
  position: absolute;
  width: 200px;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2em;
  font-weight: bold;
  color: white;
  border: 2px solid #333;
}

.frente {
  background: rgba(255, 0, 0, 0.7);
  transform: translateZ(100px);
}

.tras {
  background: rgba(0, 255, 0, 0.7);
  transform: rotateY(180deg) translateZ(100px);
}

.direita {
  background: rgba(0, 0, 255, 0.7);
  transform: rotateY(90deg) translateZ(100px);
}

.esquerda {
  background: rgba(255, 255, 0, 0.7);
  transform: rotateY(-90deg) translateZ(100px);
}

.topo {
  background: rgba(255, 0, 255, 0.7);
  transform: rotateX(90deg) translateZ(100px);
}

.base {
  background: rgba(0, 255, 255, 0.7);
  transform: rotateX(-90deg) translateZ(100px);
}
```

### 4. Card com Profundidade ao Hover

```css
.card-3d {
  width: 300px;
  height: 400px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
  transition: all 0.3s ease;
  transform-style: preserve-3d;
}

.card-3d:hover {
  transform: translateZ(50px) rotateX(5deg) rotateY(5deg);
  box-shadow: 0 30px 60px rgba(0,0,0,0.3);
}

.card-3d img {
  transition: transform 0.3s ease;
}

.card-3d:hover img {
  transform: translateZ(30px);
}

.card-3d h2 {
  transition: transform 0.3s ease;
}

.card-3d:hover h2 {
  transform: translateZ(40px);
}
```

### 5. Efeito de Página Virando

```css
.livro {
  perspective: 1500px;
}

.pagina {
  width: 400px;
  height: 600px;
  background: white;
  transform-origin: left center;
  transition: transform 1s;
  transform-style: preserve-3d;
}

.livro:hover .pagina {
  transform: rotateY(-180deg);
}

.pagina::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, rgba(0,0,0,0.2), transparent);
  transform: rotateY(180deg);
  backface-visibility: hidden;
}
```

### 6. Carrossel 3D

```html
<div class="carrossel-3d">
  <div class="carrossel-inner">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
  </div>
</div>
```

```css
.carrossel-3d {
  width: 300px;
  height: 400px;
  perspective: 1000px;
  margin: 100px auto;
}

.carrossel-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  animation: girar-carrossel 20s infinite linear;
}

@keyframes girar-carrossel {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
}

.item {
  position: absolute;
  width: 200px;
  height: 300px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3em;
  color: white;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

.item:nth-child(1) { transform: rotateY(0deg) translateZ(400px); }
.item:nth-child(2) { transform: rotateY(60deg) translateZ(400px); }
.item:nth-child(3) { transform: rotateY(120deg) translateZ(400px); }
.item:nth-child(4) { transform: rotateY(180deg) translateZ(400px); }
.item:nth-child(5) { transform: rotateY(240deg) translateZ(400px); }
.item:nth-child(6) { transform: rotateY(300deg) translateZ(400px); }
```

### 7. Botão com Profundidade 3D

```css
.btn-3d {
  padding: 20px 40px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1.2em;
  cursor: pointer;
  transition: all 0.2s;
  transform-style: preserve-3d;
  box-shadow: 0 8px 0 #3d2861;
}

.btn-3d:hover {
  transform: translateY(-3px);
  box-shadow: 0 11px 0 #3d2861;
}

.btn-3d:active {
  transform: translateY(4px);
  box-shadow: 0 4px 0 #3d2861;
}
```

### 8. Card com Efeito Parallax no Mouse

```javascript
// JavaScript necessário
const card = document.querySelector('.parallax-card');

card.addEventListener('mousemove', (e) => {
  const rect = card.getBoundingClientRect();
  const x = e.clientX - rect.left;
  const y = e.clientY - rect.top;
  
  const centerX = rect.width / 2;
  const centerY = rect.height / 2;
  
  const rotateX = (y - centerY) / 10;
  const rotateY = (centerX - x) / 10;
  
  card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
});

card.addEventListener('mouseleave', () => {
  card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0)';
});
```

```css
.parallax-card {
  width: 300px;
  height: 400px;
  background: white;
  border-radius: 10px;
  transition: transform 0.1s;
  transform-style: preserve-3d;
}
```

### 9. Efeito de Dobra (Fold)

```css
.dobra {
  width: 400px;
  height: 300px;
  perspective: 1000px;
}

.dobra-inner {
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: transform 0.6s;
}

.dobra:hover .dobra-inner {
  transform: rotateX(-90deg);
}

.dobra-top,
.dobra-bottom {
  position: absolute;
  width: 100%;
  height: 50%;
  background: #667eea;
}

.dobra-top {
  top: 0;
  transform-origin: bottom;
  background: linear-gradient(to bottom, #667eea 0%, #764ba2 100%);
}

.dobra-bottom {
  bottom: 0;
  transform: rotateX(-90deg);
  transform-origin: top;
  background: linear-gradient(to top, #667eea 0%, #764ba2 100%);
}
```

### 10. Ribbon 3D (Fita)

```css
.ribbon-3d {
  width: 200px;
  height: 50px;
  background: #e74c3c;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  transform-style: preserve-3d;
}

.ribbon-3d::before,
.ribbon-3d::after {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-style: solid;
}

.ribbon-3d::before {
  left: -20px;
  border-width: 25px 20px 25px 0;
  border-color: transparent #c0392b transparent transparent;
  transform: rotateY(30deg);
}

.ribbon-3d::after {
  right: -20px;
  border-width: 25px 0 25px 20px;
  border-color: transparent transparent transparent #c0392b;
  transform: rotateY(-30deg);
}
```

## 📊 Tabela de Referência Rápida

| Propriedade | Descrição | Valores Comuns |
|------------|-----------|----------------|
| `perspective` | Define profundidade 3D | `500px`, `1000px`, `2000px` |
| `perspective-origin` | Ponto de vista | `center`, `top left`, `50% 50%` |
| `transform-style` | Preserva 3D nos filhos | `preserve-3d`, `flat` |
| `backface-visibility` | Mostra/oculta face de trás | `visible`, `hidden` |
| `translate3d()` | Move em 3D | `translate3d(x, y, z)` |
| `translateZ()` | Move no eixo Z | `translateZ(100px)` |
| `scale3d()` | Escala em 3D | `scale3d(x, y, z)` |
| `scaleZ()` | Escala no eixo Z | `scaleZ(2)` |
| `rotate3d()` | Rotação customizada | `rotate3d(x, y, z, angle)` |
| `rotateX()` | Rotação horizontal | `rotateX(45deg)` |
| `rotateY()` | Rotação vertical | `rotateY(45deg)` |
| `rotateZ()` | Rotação no plano | `rotateZ(45deg)` |

## 🎯 Eixos 3D Explicados

```
        Y (vertical)
        |
        |
        |__________ X (horizontal)
       /
      /
     Z (profundidade)

- X: esquerda (-) / direita (+)
- Y: cima (-) / baixo (+)
- Z: longe (-) / perto (+)
```

## ⚡ Valores de Perspective Comparados

```css
/* Perspectiva muito próxima - efeito dramático */
.container1 {
  perspective: 300px;
}

/* Perspectiva moderada - equilibrado (recomendado) */
.container2 {
  perspective: 1000px;
}

/* Perspectiva distante - efeito sutil */
.container3 {
  perspective: 2000px;
}

/* Sem perspectiva - achatado */
.container4 {
  perspective: none;
}
```

## 🔗 Combinando Transformações 3D

```css
/* A ordem IMPORTA ainda mais em 3D! */
.elemento {
  transform: 
    perspective(1000px)
    translateZ(50px)
    rotateY(45deg)
    rotateX(30deg)
    scale(1.2);
}
```

## 🎨 Efeitos Avançados

### 1. Isométrico (Estilo Jogo)

```css
.isometrico {
  transform: rotateX(45deg) rotateZ(45deg);
}
```

### 2. Efeito Matrix/Perspectiva

```css
.matrix {
  transform: 
    perspective(800px) 
    rotateX(20deg) 
    translateZ(-100px);
}
```

### 3. Efeito de Profundidade em Camadas

```css
.camada1 { transform: translateZ(0px); }
.camada2 { transform: translateZ(-100px); }
.camada3 { transform: translateZ(-200px); }
.camada4 { transform: translateZ(-300px); }
```

## ⚠️ Considerações Importantes

### Performance

```css
/* ✅ BOM - Usa aceleração de GPU */
.elemento {
  transform: translate3d(0, 0, 0); /* força GPU mesmo sem movimento */
}

/* ⚠️ Cuidado com muitos elementos 3D */
/* Pode sobrecarregar GPU em dispositivos fracos */
```

### Compatibilidade

```css
/* Prefixos para navegadores antigos */
.elemento {
  -webkit-perspective: 1000px;
  perspective: 1000px;
  
  -webkit-transform-style: preserve-3d;
  transform-style: preserve-3d;
}
```

### Acessibilidade

```css
/* Respeitar preferências do usuário */
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
    transform: none !important;
  }
}
```

### Debugging 3D

```css
/* Visualizar todas as faces */
.debug * {
  backface-visibility: visible !important;
  border: 1px solid red;
}
```

## 🚀 Dicas Avançadas

### 1. Hardware Acceleration

```css
/* Forçar aceleração de hardware */
.acelerar {
  transform: translate3d(0, 0, 0);
  will-change: transform;
}
```

### 2. Variáveis CSS para Controle Dinâmico

```css
:root {
  --rotate-x: 0deg;
  --rotate-y: 0deg;
  --translate-z: 0px;
}

.elemento {
  transform: 
    rotateX(var(--rotate-x)) 
    rotateY(var(--rotate-y)) 
    translateZ(var(--translate-z));
}
```

### 3. Perspective em Diferentes Breakpoints

```css
.container {
  perspective: 1000px;
}

@media (max-width: 768px) {
  .container {
    perspective: 500px; /* Mais dramático em mobile */
  }
}
```

## ✅ Checklist para Efeitos 3D

- ✅ Definir `perspective` no elemento pai
- ✅ Usar `transform-style: preserve-3d` quando necessário
- ✅ Definir `backface-visibility: hidden` em flip cards
- ✅ Testar em diferentes dispositivos e navegadores
- ✅ Considerar performance (não exagerar)
- ✅ Implementar fallbacks para navegadores antigos
- ✅ Respeitar `prefers-reduced-motion`
- ✅ Usar transições suaves

## 📱 Responsividade e 3D

```css
/* Desktop - efeito completo */
@media (min-width: 1024px) {
  .card-3d {
    perspective: 1000px;
  }
  
  .card-3d:hover {
    transform: rotateY(180deg);
  }
}

/* Mobile - efeito simplificado ou removido */
@media (max-width: 768px) {
  .card-3d {
    perspective: none;
  }
  
  .card-3d:hover {
    transform: scale(1.05); /* Apenas escala em mobile */
  }
}
```

## 🎯 Resumo Final

**Transformações 3D permitem:**
- 🎭 Criar efeitos de profundidade realistas
- 🎴 Flip cards (frente e verso)
- 🎲 Objetos 3D (cubos, carrosséis)
- 📐 Perspectivas dinâmicas
- 🎨 Interfaces imersivas

**Propriedades essenciais:**
- `perspective` - profundidade
- `transform-style: preserve-3d` - mantém 3D
- `backface-visibility` - controla face de trás
- `rotateX()`, `rotateY()`, `rotateZ()` - rotações
- `translateZ()` - movimento em profundidade

**Transformações 3D elevam suas interfaces a um novo nível de interatividade e modernidade!** 🚀✨