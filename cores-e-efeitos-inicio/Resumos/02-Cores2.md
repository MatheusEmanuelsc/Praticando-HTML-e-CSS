
## 9. **Funções de Cores Modernas**

### **color-mix()**
Mistura duas cores:
```css
background: color-mix(in srgb, red 50%, blue 50%);
background: color-mix(in hsl, yellow 70%, green 30%);
```

### **color-contrast()**
Escolhe a cor com melhor contraste:
```css
color: color-contrast(white vs black, blue, red);
```

### **color()**
Espaços de cor avançados:
```css
color: color(display-p3 1 0.5 0);
```

## 10. **Filtros CSS**

```css
filter: hue-rotate(90deg); /* rotaciona as cores */
filter: saturate(200%); /* aumenta saturação */
filter: brightness(150%); /* aumenta brilho */
filter: contrast(200%); /* aumenta contraste */
filter: grayscale(100%); /* escala de cinza */
filter: sepia(100%); /* efeito sépia */
filter: invert(100%); /* inverte cores */
```

## 11. **Modos de Mesclagem (Blend Modes)**

```css
background-blend-mode: multiply;
background-blend-mode: screen;
background-blend-mode: overlay;
background-blend-mode: darken;
background-blend-mode: lighten;
background-blend-mode: color-dodge;
background-blend-mode: color-burn;

mix-blend-mode: difference; /* para elementos sobrepostos */
```

## 12. **Máscaras e Clipping**

```css
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background: linear-gradient(45deg, red, blue);
/* Cria texto com gradiente */
```

## 13. **Temas Claro/Escuro**

```css
/* Detecta preferência do sistema */
@media (prefers-color-scheme: dark) {
  :root {
    --fundo: #1a1a1a;
    --texto: #ffffff;
  }
}

@media (prefers-color-scheme: light) {
  :root {
    --fundo: #ffffff;
    --texto: #000000;
  }
}
```

## 14. **Cores no SVG**

```html
<svg>
  <rect fill="#ff0000" stroke="blue" stroke-width="2"/>
  <circle fill="rgba(0,255,0,0.5)"/>
</svg>
```

```css
svg path {
  fill: currentColor; /* herda cor do texto */
  stroke: var(--cor-primaria);
}
```

## 15. **Degradês Repetidos**

```css
background: repeating-linear-gradient(
  45deg,
  #606dbc,
  #606dbc 10px,
  #465298 10px,
  #465298 20px
);

background: repeating-radial-gradient(
  circle,
  red,
  red 10px,
  blue 10px,
  blue 20px
);
```

## 16. **Propriedades de Impressão**

```css
@media print {
  body {
    color: black;
    background: white;
  }
  
  /* Ajuste de cores para impressão */
  color-adjust: economy; /* economiza tinta */
  print-color-adjust: exact; /* mantém cores exatas */
}
```

## 17. **Acessibilidade Avançada**

```css
/* Modo de alto contraste */
@media (prefers-contrast: high) {
  :root {
    --cor-texto: #000000;
    --cor-fundo: #ffffff;
  }
}

/* Respeita configuração de cores reduzidas */
@media (prefers-reduced-transparency) {
  .elemento {
    background: rgb(255, 0, 0); /* sem transparência */
  }
}
```

## 18. **Accent Color**

```css
/* Personaliza cores de elementos de formulário */
accent-color: #ff0000;

input[type="checkbox"],
input[type="radio"],
progress {
  accent-color: var(--cor-primaria);
}
```

## 19. **Outline com Offset**

```css
outline: 2px solid blue;
outline-offset: 4px; /* espaçamento do outline */
outline-color: rgba(0, 0, 255, 0.5);
```

## 20. **Cores Dinâmicas com Calc()**

```css
:root {
  --hue: 200;
}

.elemento {
  background: hsl(var(--hue), 70%, 50%);
}

.elemento-variante {
  background: hsl(calc(var(--hue) + 30), 70%, 50%);
}
```

## 21. **Sistema de Cores no Canvas**

```html
<canvas id="meuCanvas"></canvas>
<script>
const ctx = document.getElementById('meuCanvas').getContext('2d');
ctx.fillStyle = '#FF0000';
ctx.fillStyle = 'rgba(255, 0, 0, 0.5)';
ctx.fillStyle = 'hsl(0, 100%, 50%)';
</script>
```

## 22. **Limitações e Suporte**

- **RGBA/HSLA:** Suportado em todos navegadores modernos
- **color-mix():** Suporte limitado (verificar Can I Use)
- **Variáveis CSS:** IE11 não suporta
- **Gradientes:** Prefixos podem ser necessários para navegadores antigos

## 23. **Ferramentas Úteis**

- **Seletor de cores:** DevTools (F12) dos navegadores
- **Contrast Checker:** para acessibilidade
- **Coolors.co:** gerador de paletas
- **Adobe Color:** roda de cores interativa
- **ColorZilla:** extensão para capturar cores

## 24. **Exemplo Completo Avançado**

```css
:root {
  --hue: 220;
  --sat: 70%;
  --light: 50%;
}

.card {
  /* Cor base usando variáveis */
  background: hsl(var(--hue), var(--sat), var(--light));
  
  /* Gradiente complexo */
  background: 
    linear-gradient(135deg, 
      hsla(var(--hue), var(--sat), var(--light), 0.9),
      hsla(calc(var(--hue) + 20), var(--sat), calc(var(--light) - 10%), 0.8)
    );
  
  /* Borda com transparência */
  border: 2px solid hsla(var(--hue), var(--sat), calc(var(--light) - 20%), 0.5);
  
  /* Sombra colorida */
  box-shadow: 
    0 10px 30px hsla(var(--hue), var(--sat), var(--light), 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
  
  /* Filtro ao passar o mouse */
  transition: filter 0.3s;
}

.card:hover {
  filter: brightness(1.1) saturate(1.2);
}

/* Tema escuro automático */
@media (prefers-color-scheme: dark) {
  .card {
    --light: 30%;
    filter: contrast(1.1);
  }
}

