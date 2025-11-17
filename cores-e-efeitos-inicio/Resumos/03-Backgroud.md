# Background Blend Mode - Guia Completo

O `background-blend-mode` controla como as camadas de fundo se misturam entre si. É muito poderoso para criar efeitos visuais interessantes!

## 1. **Sintaxe Básica**

```css
background-blend-mode: valor;
```

## 2. **Todos os Valores Disponíveis**

### **normal** (padrão)
Sem mesclagem, camadas normais:
```css
background-blend-mode: normal;
```

### **multiply** (multiplicar)
Multiplica as cores, resultando em tons mais escuros:
```css
background: 
  linear-gradient(rgba(255, 0, 0, 0.5), rgba(255, 0, 0, 0.5)),
  url('imagem.jpg');
background-blend-mode: multiply;
/* Dá um tom avermelhado escuro à imagem */
```

### **screen** (tela)
Inverte, multiplica e inverte novamente. Resulta em tons mais claros:
```css
background-blend-mode: screen;
/* Clareia a imagem */
```

### **overlay** (sobreposição)
Combina multiply e screen. Escurece áreas escuras e clareia áreas claras:
```css
background-blend-mode: overlay;
/* Aumenta contraste */
```

### **darken** (escurecer)
Mantém os pixels mais escuros:
```css
background-blend-mode: darken;
```

### **lighten** (clarear)
Mantém os pixels mais claros:
```css
background-blend-mode: lighten;
```

### **color-dodge** (subexposição de cor)
Clareia cores base para refletir cores de mesclagem:
```css
background-blend-mode: color-dodge;
/* Efeito de luz intensa */
```

### **color-burn** (superexposição de cor)
Escurece cores base para refletir cores de mesclagem:
```css
background-blend-mode: color-burn;
/* Efeito queimado/saturado */
```

### **hard-light** (luz direta)
Similar ao overlay, mas mais intenso:
```css
background-blend-mode: hard-light;
```

### **soft-light** (luz suave)
Similar ao overlay, mas mais suave:
```css
background-blend-mode: soft-light;
/* Efeito de iluminação difusa */
```

### **difference** (diferença)
Subtrai a cor mais clara da mais escura:
```css
background-blend-mode: difference;
/* Cria efeito negativo/invertido */
```

### **exclusion** (exclusão)
Similar ao difference, mas com menor contraste:
```css
background-blend-mode: exclusion;
```

### **hue** (matiz)
Mantém luminosidade e saturação da cor base, mas usa matiz da mesclagem:
```css
background-blend-mode: hue;
```

### **saturation** (saturação)
Mantém luminosidade e matiz da base, usa saturação da mesclagem:
```css
background-blend-mode: saturation;
```

### **color** (cor)
Mantém luminosidade da base, usa matiz e saturação da mesclagem:
```css
background-blend-mode: color;
/* Ótimo para colorizar imagens em preto e branco */
```

### **luminosity** (luminosidade)
Mantém matiz e saturação da base, usa luminosidade da mesclagem:
```css
background-blend-mode: luminosity;
```

## 3. **Exemplos Práticos**

### **Efeito Duotone (Duas Cores)**
```css
.duotone {
  background: 
    linear-gradient(#00ff00, #0000ff),
    url('foto.jpg');
  background-blend-mode: multiply;
  background-size: cover;
}
```

### **Overlay Colorido**
```css
.overlay-color {
  background: 
    linear-gradient(rgba(255, 0, 100, 0.6), rgba(255, 0, 100, 0.6)),
    url('imagem.jpg');
  background-blend-mode: overlay;
  background-size: cover;
}
```

### **Textura sobre Imagem**
```css
.textura {
  background: 
    url('textura-papel.png'),
    url('foto.jpg');
  background-blend-mode: multiply;
  background-size: cover;
}
```

### **Gradiente com Blend**
```css
.gradiente-blend {
  background: 
    linear-gradient(45deg, #ff00ff, #00ffff),
    linear-gradient(135deg, #ffff00, #ff0000);
  background-blend-mode: screen;
}
```

### **Efeito Vintage/Retrô**
```css
.vintage {
  background: 
    linear-gradient(rgba(255, 200, 100, 0.3), rgba(255, 100, 50, 0.3)),
    url('foto.jpg');
  background-blend-mode: soft-light;
  background-size: cover;
  filter: sepia(30%) contrast(1.2);
}
```

### **Múltiplas Camadas com Diferentes Blends**
```css
.multiplas-camadas {
  background: 
    linear-gradient(rgba(255, 0, 0, 0.3), transparent),
    linear-gradient(45deg, rgba(0, 0, 255, 0.3), transparent),
    url('imagem.jpg');
  background-blend-mode: overlay, screen, normal;
  background-size: cover;
}
```

## 4. **Mix Blend Mode (para elementos)**

Diferente do `background-blend-mode`, o `mix-blend-mode` afeta como um **elemento inteiro** se mistura com o que está atrás dele:

```css
.elemento-sobreposto {
  mix-blend-mode: multiply;
}

/* Exemplo: texto com blend */
h1 {
  color: white;
  mix-blend-mode: difference;
  /* Texto muda de cor conforme o fundo */
}
```

## 5. **Isolation (Isolamento)**

Controla se um elemento cria um novo contexto de mesclagem:

```css
.container {
  isolation: isolate; /* isola blends dentro do container */
}

.container {
  isolation: auto; /* padrão, não isola */
}
```

## 6. **Exemplos Completos**

### **Card com Overlay Colorido**
```html
<style>
.card {
  width: 300px;
  height: 400px;
  background: 
    linear-gradient(135deg, 
      rgba(156, 39, 176, 0.7), 
      rgba(63, 81, 181, 0.7)
    ),
    url('https://picsum.photos/300/400');
  background-blend-mode: multiply;
  background-size: cover;
  background-position: center;
  border-radius: 10px;
  display: flex;
  align-items: end;
  padding: 20px;
  color: white;
}
</style>

<div class="card">
  <h2>Título do Card</h2>
</div>
```

### **Efeito de Luz Neon**
```css
.neon-effect {
  background: 
    radial-gradient(circle at 30% 30%, 
      rgba(0, 255, 255, 0.8), 
      transparent 50%
    ),
    radial-gradient(circle at 70% 70%, 
      rgba(255, 0, 255, 0.8), 
      transparent 50%
    ),
    #000;
  background-blend-mode: screen;
  min-height: 100vh;
}
```

### **Imagem em Preto e Branco Colorizada**
```css
.colorize {
  background: 
    linear-gradient(to right, #ff6b6b, #4ecdc4),
    url('foto-pb.jpg');
  background-blend-mode: color;
  background-size: cover;
  filter: contrast(1.2);
}
```

## 7. **Dicas Importantes**

✅ **Ordem importa:** A ordem das camadas de background afeta o resultado final

✅ **Performance:** Blend modes podem ser pesados, use com moderação em animações

✅ **Combine com filtros:** `filter` + `blend-mode` = efeitos poderosos

✅ **Teste em diferentes navegadores:** Suporte é bom, mas pode ter variações sutis

✅ **Use para:** overlays, efeitos duotone, texturas, ajustes de cor dinâmicos

## 8. **Suporte nos Navegadores**

- ✅ Chrome/Edge: Suporte completo
- ✅ Firefox: Suporte completo
- ✅ Safari: Suporte completo
- ⚠️ IE: Não suportado

## 9. **Exemplo Interativo Completo**

```html
<!DOCTYPE html>
<html>
<head>
<style>
  .demo {
    width: 400px;
    height: 300px;
    background: 
      linear-gradient(45deg, rgba(255, 0, 150, 0.6), rgba(0, 150, 255, 0.6)),
      url('https://picsum.photos/400/300');
    background-size: cover;
    background-position: center;
    transition: background-blend-mode 0.5s;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 24px;
    font-weight: bold;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  }
  
  .demo.multiply { background-blend-mode: multiply; }
  .demo.screen { background-blend-mode: screen; }
  .demo.overlay { background-blend-mode: overlay; }
  .demo.color { background-blend-mode: color; }
  .demo.luminosity { background-blend-mode: luminosity; }
</style>
</head>
<body>
  <div class="demo multiply">Multiply</div>
  <br>
  <button onclick="changeMode('multiply')">Multiply</button>
  <button onclick="changeMode('screen')">Screen</button>
  <button onclick="changeMode('overlay')">Overlay</button>
  <button onclick="changeMode('color')">Color</button>
  <button onclick="changeMode('luminosity')">Luminosity</button>
  
  <script>
    function changeMode(mode) {
      const demo = document.querySelector('.demo');
      demo.className = 'demo ' + mode;
      demo.textContent = mode.charAt(0).toUpperCase() + mode.slice(1);
    }
  </script>
</body>
</html>
```
