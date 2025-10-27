# Guia Completo: Animações CSS

## O que são Animações CSS?

Animações CSS permitem criar **movimentos e transformações complexas** em elementos HTML sem JavaScript, usando keyframes para definir estados ao longo do tempo.

## 🎬 Diferença: Transition vs Animation

### Transition (Transição)
- ✅ Simples (de A para B)
- ✅ Precisa de gatilho (hover, click, etc)
- ✅ Roda apenas uma vez por gatilho
- ✅ Não tem controle de etapas intermediárias

```css
.elemento {
  transition: all 0.3s ease;
}

.elemento:hover {
  transform: scale(1.2);
}
```

### Animation (Animação)
- ✅ Complexa (múltiplos estados)
- ✅ Pode rodar automaticamente
- ✅ Pode repetir infinitamente
- ✅ Controle total sobre cada etapa

```css
@keyframes pulsar {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}

.elemento {
  animation: pulsar 2s infinite;
}
```

## 🔑 @keyframes - Definindo Animações

Os `@keyframes` definem **o que acontece** durante a animação.

### Sintaxe Básica

```css
@keyframes nome-da-animacao {
  from { /* estado inicial */ }
  to { /* estado final */ }
}

/* OU com porcentagens */

@keyframes nome-da-animacao {
  0% { /* início */ }
  50% { /* meio */ }
  100% { /* fim */ }
}
```

### Exemplos de Keyframes

```css
/* Simples: fade in */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Com múltiplas etapas */
@keyframes deslizar {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

/* Complexo: bounce */
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-30px);
  }
  60% {
    transform: translateY(-15px);
  }
}

/* Rotação contínua */
@keyframes girar {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* Pulsação */
@keyframes pulsar {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.2);
    opacity: 0.8;
  }
}
```

## 🎯 Propriedade `animation`

A propriedade `animation` aplica a animação ao elemento.

### Sintaxe Completa

```css
animation: nome duração timing-function delay iteration-count direction fill-mode play-state;
```

### Propriedades Individuais

#### 1. `animation-name`

Nome do @keyframes a usar.

```css
animation-name: fadeIn;
animation-name: deslizar, girar; /* múltiplas animações */
```

#### 2. `animation-duration`

Duração da animação.

```css
animation-duration: 2s;      /* 2 segundos */
animation-duration: 500ms;   /* 500 milissegundos */
animation-duration: 0.5s;    /* meio segundo */
```

#### 3. `animation-timing-function`

Curva de aceleração da animação.

```css
/* Valores pré-definidos */
animation-timing-function: linear;        /* velocidade constante */
animation-timing-function: ease;          /* padrão: lento-rápido-lento */
animation-timing-function: ease-in;       /* começa devagar */
animation-timing-function: ease-out;      /* termina devagar */
animation-timing-function: ease-in-out;   /* devagar no início e fim */

/* Curvas personalizadas */
animation-timing-function: cubic-bezier(0.68, -0.55, 0.265, 1.55);

/* Steps (animação em passos discretos) */
animation-timing-function: steps(4);           /* 4 passos */
animation-timing-function: steps(10, end);     /* 10 passos, muda no fim */
animation-timing-function: steps(10, start);   /* 10 passos, muda no início */
animation-timing-function: step-start;         /* pula direto para o fim */
animation-timing-function: step-end;           /* pula direto para o início */
```

**Comparação visual:**

```css
/* Linear - velocidade constante */
.linear { animation-timing-function: linear; }

/* Ease - mais natural */
.ease { animation-timing-function: ease; }

/* Ease-in - aceleração gradual */
.ease-in { animation-timing-function: ease-in; }

/* Ease-out - desaceleração gradual */
.ease-out { animation-timing-function: ease-out; }

/* Cubic-bezier - bouncy/elástico */
.bouncy { animation-timing-function: cubic-bezier(0.68, -0.55, 0.265, 1.55); }
```

#### 4. `animation-delay`

Tempo de espera antes de iniciar.

```css
animation-delay: 1s;        /* espera 1 segundo */
animation-delay: 500ms;     /* espera 500ms */
animation-delay: -1s;       /* começa 1s "adiantada" */
```

#### 5. `animation-iteration-count`

Quantas vezes repetir.

```css
animation-iteration-count: 1;         /* uma vez (padrão) */
animation-iteration-count: 3;         /* 3 vezes */
animation-iteration-count: infinite;  /* infinitamente */
```

#### 6. `animation-direction`

Direção da animação.

```css
animation-direction: normal;            /* padrão: 0% → 100% */
animation-direction: reverse;           /* invertido: 100% → 0% */
animation-direction: alternate;         /* vai e volta: 0%→100%→0%→100% */
animation-direction: alternate-reverse; /* vai e volta invertido */
```

**Exemplo com alternate:**

```css
@keyframes mover {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}

.elemento {
  animation: mover 2s infinite alternate;
  /* Vai para direita, depois volta, depois vai... */
}
```

#### 7. `animation-fill-mode`

Como aplicar estilos antes/depois da animação.

```css
animation-fill-mode: none;       /* padrão: não aplica estilos */
animation-fill-mode: forwards;   /* mantém estilo final */
animation-fill-mode: backwards;  /* aplica estilo inicial imediatamente */
animation-fill-mode: both;       /* forwards + backwards */
```

**Exemplo prático:**

```css
@keyframes aparecer {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Sem fill-mode: volta ao estado original */
.sem-fill {
  animation: aparecer 1s;
  /* Após animar, volta a ser invisível */
}

/* Com forwards: mantém estado final */
.com-fill {
  animation: aparecer 1s forwards;
  /* Após animar, fica visível */
}

/* Com delay + backwards: aplica estilo inicial imediatamente */
.com-backwards {
  animation: aparecer 1s 2s backwards;
  /* Fica invisível durante os 2s de delay */
}
```

#### 8. `animation-play-state`

Pausar/retomar animação.

```css
animation-play-state: running;  /* rodando (padrão) */
animation-play-state: paused;   /* pausada */
```

**Uso prático:**

```css
.elemento {
  animation: girar 2s linear infinite;
}

.elemento:hover {
  animation-play-state: paused;
}
```

### Sintaxe Shorthand

```css
/* Ordem: name duration timing-function delay iteration-count direction fill-mode */
.elemento {
  animation: fadeIn 2s ease-in-out 0.5s infinite alternate forwards;
}

/* Múltiplas animações */
.elemento {
  animation: 
    fadeIn 1s ease-out,
    deslizar 2s ease-in-out 0.5s,
    girar 3s linear infinite;
}
```

## 🎨 Exemplos Práticos de Animações

### 1. Fade In (Aparecer)

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn 1s ease-in;
}
```

### 2. Slide In (Deslizar para dentro)

```css
@keyframes slideInLeft {
  from {
    transform: translateX(-100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes slideInRight {
  from {
    transform: translateX(100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes slideInTop {
  from {
    transform: translateY(-100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes slideInBottom {
  from {
    transform: translateY(100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.slide-in-left { animation: slideInLeft 0.5s ease-out; }
.slide-in-right { animation: slideInRight 0.5s ease-out; }
.slide-in-top { animation: slideInTop 0.5s ease-out; }
.slide-in-bottom { animation: slideInBottom 0.5s ease-out; }
```

### 3. Bounce (Quicar)

```css
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-30px);
  }
  60% {
    transform: translateY(-15px);
  }
}

.bounce {
  animation: bounce 2s infinite;
}
```

### 4. Shake (Tremer)

```css
@keyframes shake {
  0%, 100% { transform: translateX(0); }
  10%, 30%, 50%, 70%, 90% { transform: translateX(-10px); }
  20%, 40%, 60%, 80% { transform: translateX(10px); }
}

.shake {
  animation: shake 0.5s;
}

/* Aplicar ao clicar */
.button.erro {
  animation: shake 0.5s;
}
```

### 5. Pulse (Pulsar)

```css
@keyframes pulse {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.8;
  }
}

.pulse {
  animation: pulse 2s ease-in-out infinite;
}
```

### 6. Rotate (Girar)

```css
@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.rotate {
  animation: rotate 2s linear infinite;
}

/* Loading spinner */
.spinner {
  width: 50px;
  height: 50px;
  border: 5px solid #f3f3f3;
  border-top: 5px solid #3498db;
  border-radius: 50%;
  animation: rotate 1s linear infinite;
}
```

### 7. Flip (Virar)

```css
@keyframes flip {
  from {
    transform: rotateY(0);
  }
  to {
    transform: rotateY(360deg);
  }
}

.flip {
  animation: flip 1s ease-in-out;
}
```

### 8. Zoom In (Aumentar)

```css
@keyframes zoomIn {
  from {
    transform: scale(0);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

.zoom-in {
  animation: zoomIn 0.5s ease-out;
}
```

### 9. Swing (Balançar)

```css
@keyframes swing {
  20% {
    transform: rotate(15deg);
  }
  40% {
    transform: rotate(-10deg);
  }
  60% {
    transform: rotate(5deg);
  }
  80% {
    transform: rotate(-5deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

.swing {
  transform-origin: top center;
  animation: swing 1s ease-in-out;
}
```

### 10. Typing Effect (Efeito de Digitação)

```css
@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

@keyframes blink {
  50% {
    border-color: transparent;
  }
}

.typing {
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid;
  animation: 
    typing 3.5s steps(40, end),
    blink 0.75s step-end infinite;
}
```

## 🌟 Animações Avançadas

### 1. Loading Dots (Pontinhos carregando)

```css
@keyframes loading {
  0%, 80%, 100% {
    opacity: 0;
    transform: scale(0);
  }
  40% {
    opacity: 1;
    transform: scale(1);
  }
}

.loading-dots span {
  display: inline-block;
  width: 12px;
  height: 12px;
  background: #3498db;
  border-radius: 50%;
  animation: loading 1.4s infinite ease-in-out both;
}

.loading-dots span:nth-child(1) {
  animation-delay: -0.32s;
}

.loading-dots span:nth-child(2) {
  animation-delay: -0.16s;
}
```

### 2. Wave Text (Texto ondulando)

```css
@keyframes wave {
  0%, 40%, 100% {
    transform: translateY(0);
  }
  20% {
    transform: translateY(-20px);
  }
}

.wave-text span {
  display: inline-block;
  animation: wave 1.5s ease-in-out infinite;
}

.wave-text span:nth-child(1) { animation-delay: 0s; }
.wave-text span:nth-child(2) { animation-delay: 0.1s; }
.wave-text span:nth-child(3) { animation-delay: 0.2s; }
.wave-text span:nth-child(4) { animation-delay: 0.3s; }
.wave-text span:nth-child(5) { animation-delay: 0.4s; }
```

### 3. Progress Bar Animada

```css
@keyframes progress {
  from {
    width: 0%;
  }
  to {
    width: 100%;
  }
}

.progress-bar {
  height: 20px;
  background: #e0e0e0;
  border-radius: 10px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  animation: progress 3s ease-out forwards;
}
```

### 4. Skeleton Loading

```css
@keyframes skeleton {
  0% {
    background-position: -200px 0;
  }
  100% {
    background-position: calc(200px + 100%) 0;
  }
}

.skeleton {
  background: linear-gradient(
    90deg,
    #f0f0f0 0px,
    #e0e0e0 40px,
    #f0f0f0 80px
  );
  background-size: 200px;
  animation: skeleton 1.5s infinite ease-in-out;
}
```

### 5. Floating (Flutuando)

```css
@keyframes floating {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.floating {
  animation: floating 3s ease-in-out infinite;
}
```

### 6. Glowing (Brilhando)

```css
@keyframes glow {
  0%, 100% {
    box-shadow: 0 0 5px #3498db;
  }
  50% {
    box-shadow: 0 0 20px #3498db, 0 0 30px #3498db;
  }
}

.glowing {
  animation: glow 2s ease-in-out infinite;
}
```

### 7. Gradient Animation (Gradiente animado)

```css
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.gradient-animated {
  background: linear-gradient(
    -45deg,
    #ee7752,
    #e73c7e,
    #23a6d5,
    #23d5ab
  );
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
}
```

### 8. Heartbeat (Batimento cardíaco)

```css
@keyframes heartbeat {
  0%, 100% {
    transform: scale(1);
  }
  10%, 30% {
    transform: scale(0.9);
  }
  20%, 40% {
    transform: scale(1.1);
  }
}

.heartbeat {
  animation: heartbeat 1.3s ease-in-out infinite;
}
```

### 9. Notification Badge

```css
@keyframes notify {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
}

.badge {
  width: 20px;
  height: 20px;
  background: #e74c3c;
  border-radius: 50%;
  animation: notify 2s ease-in-out infinite;
}
```

### 10. Matrix Rain (Chuva de código)

```css
@keyframes matrix-rain {
  0% {
    transform: translateY(-100%);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    transform: translateY(100vh);
    opacity: 0;
  }
}

.matrix-char {
  position: absolute;
  color: #0f0;
  font-family: monospace;
  animation: matrix-rain 3s linear infinite;
}

.matrix-char:nth-child(1) { left: 10%; animation-delay: 0s; }
.matrix-char:nth-child(2) { left: 30%; animation-delay: 0.5s; }
.matrix-char:nth-child(3) { left: 50%; animation-delay: 1s; }
.matrix-char:nth-child(4) { left: 70%; animation-delay: 1.5s; }
.matrix-char:nth-child(5) { left: 90%; animation-delay: 2s; }
```

## 🎭 Animações com JavaScript

### Adicionar/Remover Classes

```javascript
// Adicionar animação
elemento.classList.add('fade-in');

// Remover após completar
elemento.addEventListener('animationend', () => {
  elemento.classList.remove('fade-in');
});

// Detectar tipo de animação que terminou
elemento.addEventListener('animationend', (e) => {
  if (e.animationName === 'fadeIn') {
    console.log('Fade in completado!');
  }
});
```

### Controlar Play State

```javascript
const elemento = document.querySelector('.animado');

// Pausar
elemento.style.animationPlayState = 'paused';

// Retomar
elemento.style.animationPlayState = 'running';
```

### Animação ao Scroll (Intersection Observer)

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('animate');
    }
  });
});

document.querySelectorAll('.animate-on-scroll').forEach(el => {
  observer.observe(el);
});
```

```css
.animate-on-scroll {
  opacity: 0;
  transform: translateY(50px);
}

.animate-on-scroll.animate {
  animation: slideInBottom 0.6s ease-out forwards;
}
```

## 📊 Tabela de Referência Rápida

| Propriedade | Valores Comuns | Descrição |
|------------|----------------|-----------|
| `animation-name` | nome do keyframe | Define qual animação usar |
| `animation-duration` | `1s`, `500ms` | Duração da animação |
| `animation-timing-function` | `ease`, `linear`, `ease-in-out` | Curva de velocidade |
| `animation-delay` | `0.5s`, `1s` | Atraso antes de iniciar |
| `animation-iteration-count` | `1`, `3`, `infinite` | Quantas vezes repetir |
| `animation-direction` | `normal`, `reverse`, `alternate` | Direção da animação |
| `animation-fill-mode` | `none`, `forwards`, `backwards`, `both` | Estilos antes/depois |
| `animation-play-state` | `running`, `paused` | Estado de execução |

## 🎯 Timing Functions Visualizadas

```css
/* Linear - velocidade constante */
animation-timing-function: linear;
/* ━━━━━━━━━━━━━━━━━━━━━━ */

/* Ease - padrão (lento-rápido-lento) */
animation-timing-function: ease;
/* ━╱━━━━━━━━━╲━ */

/* Ease-in - acelera */
animation-timing-function: ease-in;
/* ╱━━━━━━━━━━━━ */

/* Ease-out - desacelera */
animation-timing-function: ease-out;
/* ━━━━━━━━━━━━╲ */

/* Ease-in-out - acelera e desacelera */
animation-timing-function: ease-in-out;
/* ╱━━━━━━━━━╲ */

/* Cubic-bezier customizado */
animation-timing-function: cubic-bezier(0.68, -0.55, 0.265, 1.55);
/* Efeito elástico/bouncy */
```

## ⚠️ Boas Práticas

### Performance

```css
/* ✅ BOM - Propriedades otimizadas */
@keyframes bom {
  from {
    transform: translateX(0);
    opacity: 1;
  }
  to {
    transform: translateX(100px);
    opacity: 0;
  }
}

/* ❌ RUIM - Causa reflow/repaint */
@keyframes ruim {
  from {
    left: 0;
    width: 100px;
  }
  to {
    left: 100px;
    width: 200px;
  }
}

/* ✅ Use transform e opacity */
/* ❌ Evite: top, left, width, height, margin, padding */
```

### Will-change

```css
/* Avisar o navegador sobre animações */
.elemento {
  will-change: transform, opacity;
}

/* Remover após animação */
.elemento.animado {
  will-change: auto;
}
```

### Prefixos (raramente necessário hoje)

```css
@-webkit-keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.elemento {
  -webkit-animation: fadeIn 1s;
  animation: fadeIn 1s;
}
```

### Acessibilidade

```css
/* Respeitar preferência do usuário */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

## 🚀 Dicas Avançadas

### 1. Stagger (Efeito em cascata)

```css
.item {
  animation: fadeIn 0.5s ease-out backwards;
}

.item:nth-child(1) { animation-delay: 0.1s; }
.item:nth-child(2) { animation-delay: 0.2s; }
.item:nth-child(3) { animation-delay: 0.3s; }
.item:nth-child(4) { animation-delay: 0.4s; }
.item:nth-child(5) { animation-delay: 0.5s; }
```

### 2. Variáveis CSS para Controle Dinâmico

```css
:root {
  --animation-duration: 2s;
  --animation-delay: 0s;
}

.elemento {
  animation: fadeIn var(--animation-duration) ease-out var(--animation-delay);
}
```

```javascript
// Alterar via JavaScript
element.style.setProperty('--animation-duration', '5s');
```

### 3. Animações Responsivas

```css
/* Desktop - animação completa */
@media (min-width: 1024px) {
  .elemento {
    animation: complexAnimation 2s ease-out;
  }
}

/* Mobile - animação simplificada */
@media (max-width: 768px) {
  .elemento {
    animation: simpleAnimation 1s ease-out;
  }
}
```

## ✅ Checklist de Animações

- ✅ Use `transform` e `opacity` para performance
- ✅ Defina `animation-fill-mode: forwards` se quiser manter estado final
- ✅ Use `will-change` com moderação
- ✅ Teste em diferentes dispositivos
- ✅ Implemente `prefers-reduced-motion`
- ✅ Considere delays para efeitos em cascata
- ✅ Não exagere - menos é mais
- ✅ Teste a fluidez (60fps)

## 🎯 Resumo Final

**Animações CSS permitem:**
- ✨ Criar movimentos complexos sem JavaScript
- 🎬 Definir múltiplos estados com keyframes
- 🔄 Repetir infinitamente ou número específico de vezes
- 🎨 Controlar timing, direção e preenchimento
- 🚀 Performance superior com aceleração GPU

**Componentes essenciais:**
- `@keyframes` - define o que acontece
- `animation` - aplica ao elemento
- `animation-timing-function` - controla velocidade
- `animation-fill-mode` - mantém estados
- `animation-iteration-count` - controla repetições

**Animações elevam a experiência do usuário e tornam interfaces mais vivas e engajantes!** 🎭✨

---

## 🎪 Bibliotecas de Animações CSS Prontas

### Animate.css

Biblioteca popular com animações pré-definidas.

```html
<!-- Incluir via CDN -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>

<!-- Usar classes -->
<div class="animate__animated animate__fadeIn">
  Conteúdo
</div>

<div class="animate__animated animate__bounce animate__delay-2s">
  Bounce com delay
</div>
```

**Classes úteis:**
- `animate__fadeIn`, `animate__fadeOut`
- `animate__slideInLeft`, `animate__slideInRight`
- `animate__bounceIn`, `animate__bounceOut`
- `animate__zoomIn`, `animate__zoomOut`
- `animate__rotateIn`, `animate__rotateOut`
- `animate__flip`, `animate__flipInX`
- `animate__heartBeat`, `animate__pulse`
- `animate__wobble`, `animate__jello`
- `animate__delay-2s`, `animate__slow`, `animate__fast`
- `animate__infinite`, `animate__repeat-2`

### Criando Biblioteca Própria

```css
/* animations.css - sua própria biblioteca */

/* Utilitários */
.animated {
  animation-duration: 1s;
  animation-fill-mode: both;
}

.animated.infinite { animation-iteration-count: infinite; }
.animated.delay-1s { animation-delay: 1s; }
.animated.delay-2s { animation-delay: 2s; }
.animated.fast { animation-duration: 0.5s; }
.animated.slow { animation-duration: 2s; }

/* Fade animations */
.fade-in { animation-name: fadeIn; }
.fade-out { animation-name: fadeOut; }
.fade-in-up { animation-name: fadeInUp; }
.fade-in-down { animation-name: fadeInDown; }

/* Slide animations */
.slide-in-left { animation-name: slideInLeft; }
.slide-in-right { animation-name: slideInRight; }

/* Scale animations */
.zoom-in { animation-name: zoomIn; }
.zoom-out { animation-name: zoomOut; }

/* Rotate animations */
.rotate-in { animation-name: rotateIn; }
.rotate-out { animation-name: rotateOut; }

/* Attention seekers */
.bounce { animation-name: bounce; }
.pulse { animation-name: pulse; }
.shake { animation-name: shake; }
.swing { animation-name: swing; }
```

## 🎮 Animações Interativas com Scroll

### Scroll-triggered Animations

```css
/* Estado inicial (invisível) */
.reveal {
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.6s ease-out;
}

/* Estado revelado */
.reveal.active {
  opacity: 1;
  transform: translateY(0);
}

/* Variações de direção */
.reveal-left {
  opacity: 0;
  transform: translateX(-50px);
}

.reveal-right {
  opacity: 0;
  transform: translateX(50px);
}

.reveal-scale {
  opacity: 0;
  transform: scale(0.8);
}

.reveal.active,
.reveal-left.active,
.reveal-right.active,
.reveal-scale.active {
  opacity: 1;
  transform: translate(0) scale(1);
}
```

```javascript
// Intersection Observer para ativar no scroll
const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -100px 0px'
};

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('active');
      // Opcional: parar de observar após animar
      observer.unobserve(entry.target);
    }
  });
}, observerOptions);

// Observar todos os elementos com classe .reveal
document.querySelectorAll('.reveal, .reveal-left, .reveal-right, .reveal-scale')
  .forEach(el => observer.observe(el));
```

### Parallax com Scroll

```css
.parallax-layer {
  transition: transform 0.1s ease-out;
}

.layer-1 { transform: translateY(calc(var(--scroll) * 0.2px)); }
.layer-2 { transform: translateY(calc(var(--scroll) * 0.5px)); }
.layer-3 { transform: translateY(calc(var(--scroll) * 0.8px)); }
```

```javascript
// Atualizar variável CSS com scroll
window.addEventListener('scroll', () => {
  const scroll = window.pageYOffset;
  document.documentElement.style.setProperty('--scroll', scroll);
});
```

## 🎨 Efeitos de Texto Avançados

### 1. Glitch Effect

```css
@keyframes glitch-1 {
  0%, 100% {
    clip-path: inset(40% 0 61% 0);
  }
  20% {
    clip-path: inset(92% 0 1% 0);
  }
  40% {
    clip-path: inset(43% 0 1% 0);
  }
  60% {
    clip-path: inset(25% 0 58% 0);
  }
  80% {
    clip-path: inset(54% 0 7% 0);
  }
}

@keyframes glitch-2 {
  0%, 100% {
    transform: translate(0);
  }
  33% {
    transform: translate(-5px, 2px);
  }
  66% {
    transform: translate(5px, -2px);
  }
}

.glitch {
  position: relative;
  font-size: 3em;
  font-weight: bold;
}

.glitch::before,
.glitch::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.glitch::before {
  color: #ff00ff;
  animation: glitch-1 2s infinite linear alternate-reverse;
}

.glitch::after {
  color: #00ffff;
  animation: glitch-2 3s infinite linear alternate-reverse;
}
```

```html
<div class="glitch" data-text="GLITCH">GLITCH</div>
```

### 2. Neon Text

```css
@keyframes neon {
  0%, 100% {
    text-shadow:
      0 0 10px #fff,
      0 0 20px #fff,
      0 0 30px #fff,
      0 0 40px #0ff,
      0 0 70px #0ff,
      0 0 80px #0ff,
      0 0 100px #0ff,
      0 0 150px #0ff;
  }
  50% {
    text-shadow:
      0 0 5px #fff,
      0 0 10px #fff,
      0 0 15px #fff,
      0 0 20px #0ff,
      0 0 35px #0ff,
      0 0 40px #0ff,
      0 0 50px #0ff,
      0 0 75px #0ff;
  }
}

.neon-text {
  font-size: 3em;
  color: #fff;
  animation: neon 1.5s ease-in-out infinite;
}
```

### 3. Text Reveal Effect

```css
@keyframes text-reveal {
  from {
    clip-path: inset(0 100% 0 0);
  }
  to {
    clip-path: inset(0 0 0 0);
  }
}

.text-reveal {
  display: inline-block;
  animation: text-reveal 1s cubic-bezier(0.77, 0, 0.175, 1) forwards;
}
```

### 4. Scramble Text Effect

```javascript
class TextScramble {
  constructor(el) {
    this.el = el;
    this.chars = '!<>-_\\/[]{}—=+*^?#________';
    this.update = this.update.bind(this);
  }
  
  setText(newText) {
    const oldText = this.el.innerText;
    const length = Math.max(oldText.length, newText.length);
    const promise = new Promise((resolve) => this.resolve = resolve);
    this.queue = [];
    
    for (let i = 0; i < length; i++) {
      const from = oldText[i] || '';
      const to = newText[i] || '';
      const start = Math.floor(Math.random() * 40);
      const end = start + Math.floor(Math.random() * 40);
      this.queue.push({ from, to, start, end });
    }
    
    cancelAnimationFrame(this.frameRequest);
    this.frame = 0;
    this.update();
    return promise;
  }
  
  update() {
    let output = '';
    let complete = 0;
    
    for (let i = 0, n = this.queue.length; i < n; i++) {
      let { from, to, start, end, char } = this.queue[i];
      
      if (this.frame >= end) {
        complete++;
        output += to;
      } else if (this.frame >= start) {
        if (!char || Math.random() < 0.28) {
          char = this.randomChar();
          this.queue[i].char = char;
        }
        output += char;
      } else {
        output += from;
      }
    }
    
    this.el.innerHTML = output;
    
    if (complete === this.queue.length) {
      this.resolve();
    } else {
      this.frameRequest = requestAnimationFrame(this.update);
      this.frame++;
    }
  }
  
  randomChar() {
    return this.chars[Math.floor(Math.random() * this.chars.length)];
  }
}

// Uso
const el = document.querySelector('.scramble-text');
const fx = new TextScramble(el);
fx.setText('NOVO TEXTO');
```

## 🎯 Animações de Loading

### 1. Spinner Dots

```css
@keyframes dot-pulse {
  0%, 80%, 100% {
    transform: scale(0);
  }
  40% {
    transform: scale(1);
  }
}

.spinner-dots {
  display: flex;
  gap: 10px;
}

.spinner-dots span {
  width: 15px;
  height: 15px;
  background: #3498db;
  border-radius: 50%;
  animation: dot-pulse 1.4s infinite ease-in-out both;
}

.spinner-dots span:nth-child(1) { animation-delay: -0.32s; }
.spinner-dots span:nth-child(2) { animation-delay: -0.16s; }
.spinner-dots span:nth-child(3) { animation-delay: 0s; }
```

### 2. Spinner Bar

```css
@keyframes bar-stretch {
  0%, 40%, 100% {
    transform: scaleY(0.4);
  }
  20% {
    transform: scaleY(1);
  }
}

.spinner-bar {
  display: flex;
  gap: 5px;
  align-items: center;
  height: 40px;
}

.spinner-bar span {
  width: 6px;
  height: 100%;
  background: #3498db;
  animation: bar-stretch 1.2s infinite ease-in-out;
}

.spinner-bar span:nth-child(1) { animation-delay: -1.2s; }
.spinner-bar span:nth-child(2) { animation-delay: -1.1s; }
.spinner-bar span:nth-child(3) { animation-delay: -1.0s; }
.spinner-bar span:nth-child(4) { animation-delay: -0.9s; }
.spinner-bar span:nth-child(5) { animation-delay: -0.8s; }
```

### 3. Circle Progress

```css
@keyframes circle-progress {
  0% {
    stroke-dashoffset: 283;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

.circle-progress {
  width: 100px;
  height: 100px;
}

.circle-progress circle {
  fill: none;
  stroke: #3498db;
  stroke-width: 10;
  stroke-dasharray: 283;
  stroke-dashoffset: 283;
  animation: circle-progress 2s ease-out forwards;
  transform: rotate(-90deg);
  transform-origin: center;
}
```

```html
<svg class="circle-progress">
  <circle cx="50" cy="50" r="45"/>
</svg>
```

### 4. Skeleton Screen

```css
@keyframes skeleton-loading {
  0% {
    background-position: -200px 0;
  }
  100% {
    background-position: calc(200px + 100%) 0;
  }
}

.skeleton {
  background: #f6f7f8;
  background-image: linear-gradient(
    90deg,
    #f6f7f8 0px,
    #edeef1 40px,
    #f6f7f8 80px
  );
  background-size: 200px 100%;
  animation: skeleton-loading 1.5s infinite;
}

.skeleton-text {
  height: 16px;
  margin-bottom: 10px;
  border-radius: 4px;
}

.skeleton-avatar {
  width: 60px;
  height: 60px;
  border-radius: 50%;
}

.skeleton-button {
  height: 40px;
  border-radius: 8px;
}
```

## 🎪 Animações de Botões

### 1. Ripple Effect

```css
.btn-ripple {
  position: relative;
  overflow: hidden;
}

@keyframes ripple {
  to {
    transform: scale(4);
    opacity: 0;
  }
}

.btn-ripple::after {
  content: '';
  position: absolute;
  width: 100px;
  height: 100px;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  transform: scale(0);
  pointer-events: none;
}

.btn-ripple:active::after {
  animation: ripple 0.6s ease-out;
}
```

### 2. Slide Background

```css
@keyframes slide-bg {
  from {
    left: -100%;
  }
  to {
    left: 100%;
  }
}

.btn-slide {
  position: relative;
  overflow: hidden;
  background: #3498db;
  color: white;
  padding: 15px 30px;
  border: none;
  cursor: pointer;
}

.btn-slide::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.3);
}

.btn-slide:hover::before {
  animation: slide-bg 0.6s ease-out;
}
```

### 3. Morphing Button

```css
.btn-morph {
  padding: 15px 30px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

.btn-morph:hover {
  border-radius: 10px;
  transform: scale(1.1);
  box-shadow: 0 10px 25px rgba(52, 152, 219, 0.4);
}

.btn-morph:active {
  transform: scale(0.95);
}
```

### 4. Success Button Animation

```css
@keyframes success {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}

@keyframes checkmark {
  0% {
    stroke-dashoffset: 50;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

.btn-success {
  position: relative;
  padding: 15px 30px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.btn-success.success {
  background: #2ecc71;
  animation: success 0.6s ease-out;
}

.btn-success svg {
  display: none;
  width: 20px;
  height: 20px;
  stroke: white;
  stroke-width: 3;
  stroke-dasharray: 50;
  stroke-dashoffset: 50;
}

.btn-success.success svg {
  display: inline-block;
  animation: checkmark 0.5s ease-out forwards;
}
```

## 🎨 Micro-interações

### 1. Like Button

```css
@keyframes like {
  0%, 100% {
    transform: scale(1);
  }
  25% {
    transform: scale(1.2);
  }
  50% {
    transform: scale(0.95);
  }
  75% {
    transform: scale(1.1);
  }
}

.btn-like {
  font-size: 2em;
  background: none;
  border: none;
  cursor: pointer;
  transition: color 0.3s;
}

.btn-like.liked {
  color: #e74c3c;
  animation: like 0.6s ease-out;
}
```

### 2. Toggle Switch

```css
.toggle {
  width: 60px;
  height: 30px;
  background: #ccc;
  border-radius: 15px;
  position: relative;
  cursor: pointer;
  transition: background 0.3s;
}

.toggle::after {
  content: '';
  width: 26px;
  height: 26px;
  background: white;
  border-radius: 50%;
  position: absolute;
  top: 2px;
  left: 2px;
  transition: transform 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.toggle.active {
  background: #2ecc71;
}

.toggle.active::after {
  transform: translateX(30px);
}
```

### 3. Counter Animation

```javascript
function animateCounter(element, target, duration = 2000) {
  const start = 0;
  const increment = target / (duration / 16);
  let current = start;
  
  const timer = setInterval(() => {
    current += increment;
    if (current >= target) {
      element.textContent = target;
      clearInterval(timer);
    } else {
      element.textContent = Math.floor(current);
    }
  }, 16);
}

// Uso
const counter = document.querySelector('.counter');
animateCounter(counter, 1000);
```

```css
.counter {
  font-size: 4em;
  font-weight: bold;
  color: #3498db;
}
```

## 🎭 Animações de Modais e Popups

### 1. Modal Fade & Scale

```css
@keyframes modal-fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes modal-scale-in {
  from {
    transform: scale(0.7);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  animation: modal-fade-in 0.3s ease-out;
}

.modal-content {
  background: white;
  padding: 30px;
  border-radius: 10px;
  max-width: 500px;
  animation: modal-scale-in 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

### 2. Slide Modal

```css
@keyframes slide-up {
  from {
    transform: translateY(100%);
  }
  to {
    transform: translateY(0);
  }
}

.modal-slide {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: white;
  border-radius: 20px 20px 0 0;
  padding: 30px;
  animation: slide-up 0.3s ease-out;
}
```

### 3. Tooltip Animado

```css
@keyframes tooltip-fade {
  from {
    opacity: 0;
    transform: translateY(5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.tooltip {
  position: relative;
}

.tooltip::after {
  content: attr(data-tooltip);
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  background: #333;
  color: white;
  padding: 8px 12px;
  border-radius: 5px;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  margin-bottom: 5px;
}

.tooltip:hover::after {
  animation: tooltip-fade 0.3s ease-out forwards;
}
```

## 📱 Animações Responsivas

### Mobile-First Animations

```css
/* Mobile - animações simplificadas */
.card {
  transition: transform 0.3s;
}

.card:active {
  transform: scale(0.95);
}

/* Tablet+ - adicionar mais efeitos */
@media (min-width: 768px) {
  .card:hover {
    transform: translateY(-10px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.2);
  }
}

/* Desktop - animações completas */
@media (min-width: 1024px) {
  .card {
    animation: none; /* remover auto-play em desktop */
  }
  
  .card:hover {
    transform: translateY(-10px) scale(1.02) rotate(2deg);
    box-shadow: 0 30px 60px rgba(0,0,0,0.3);
  }
}
```

## ✅ Resumo de Melhores Práticas

### Performance
```css
/* ✅ Animar apenas transform e opacity */
.good {
  animation: slide 1s;
}

@keyframes slide {
  from { transform: translateX(-100%); }
  to { transform: translateX(0); }
}

/* ❌ Evitar propriedades que causam reflow */
.bad {
  animation: slide-bad 1s;
}

@keyframes slide-bad {
  from { left: -100px; } /* RUIM */
  to { left: 0; }
}
```

### Acessibilidade
```css
/* Sempre incluir */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Organização
```css
/* Agrupe animações relacionadas */
/* animations/fade.css */
@keyframes fadeIn { }
@keyframes fadeOut { }
@keyframes fadeInUp { }

/* animations/slide.css */
@keyframes slideInLeft { }
@keyframes slideInRight { }

/* animations/scale.css */
@keyframes zoomIn { }
@keyframes zoomOut { }
```

**Animações CSS são a alma das interfaces modernas - use com sabedoria!** 🎨✨🚀