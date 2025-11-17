# Guia Completo sobre Cores em HTML e CSS



## 1. **Formatos de Cores**

### **Cores Nomeadas**
HTML/CSS possui 140 cores pré-definidas com nomes em inglês:

```css
color: red;
color: blue;
color: green;
color: white;
color: black;
color: coral;
color: tomato;
```

### **Hexadecimal (HEX)**
Formato mais comum: `#RRGGBB` (Red, Green, Blue)

```css
color: #FF0000; /* vermelho */
color: #00FF00; /* verde */
color: #0000FF; /* azul */
color: #FFFFFF; /* branco */
color: #000000; /* preto */
color: #FFA500; /* laranja */
```

**Formato curto:** Quando os pares são iguais
```css
color: #F00; /* equivale a #FF0000 */
color: #0F0; /* equivale a #00FF00 */
```

### **RGB (Red, Green, Blue)**
Valores de 0 a 255 para cada canal:

```css
color: rgb(255, 0, 0); /* vermelho */
color: rgb(0, 255, 0); /* verde */
color: rgb(0, 0, 255); /* azul */
color: rgb(255, 165, 0); /* laranja */
```

### **RGBA (RGB + Alpha)**
Adiciona transparência (0 = transparente, 1 = opaco):

```css
color: rgba(255, 0, 0, 0.5); /* vermelho 50% transparente */
color: rgba(0, 0, 0, 0.8); /* preto 80% opaco */
background: rgba(255, 255, 255, 0.2); /* branco quase transparente */
```

### **HSL (Hue, Saturation, Lightness)**
- **Hue (Matiz):** 0-360 graus (roda de cores)
- **Saturation (Saturação):** 0-100% (intensidade da cor)
- **Lightness (Luminosidade):** 0-100% (claro/escuro)

```css
color: hsl(0, 100%, 50%); /* vermelho */
color: hsl(120, 100%, 50%); /* verde */
color: hsl(240, 100%, 50%); /* azul */
color: hsl(39, 100%, 50%); /* laranja */
```

### **HSLA (HSL + Alpha)**
```css
color: hsla(0, 100%, 50%, 0.5); /* vermelho semi-transparente */
background: hsla(200, 100%, 50%, 0.3);
```

## 2. **Propriedades CSS que Usam Cores**

### **Texto**
```css
color: #333; /* cor do texto */
```

### **Fundo**
```css
background-color: #f0f0f0;
background: linear-gradient(to right, red, blue); /* gradiente */
```

### **Bordas**
```css
border-color: red;
border: 2px solid #000;
border-top-color: blue;
```

### **Sombras**
```css
text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
```

### **Outros**
```css
outline-color: red;
text-decoration-color: blue;
caret-color: green; /* cor do cursor de texto */
```

## 3. **Gradientes**

### **Linear Gradient**
```css
background: linear-gradient(direction, cor1, cor2, ...);

/* Exemplos */
background: linear-gradient(to right, red, blue);
background: linear-gradient(45deg, #ff0000, #00ff00);
background: linear-gradient(to bottom, red 0%, yellow 50%, green 100%);
```

### **Radial Gradient**
```css
background: radial-gradient(shape, cor1, cor2);

/* Exemplos */
background: radial-gradient(circle, red, blue);
background: radial-gradient(ellipse at center, #fff, #000);
```

### **Conic Gradient**
```css
background: conic-gradient(red, yellow, green, blue, red);
```

## 4. **Valores Especiais**

```css
color: transparent; /* totalmente transparente */
color: currentColor; /* herda a cor atual do texto */
color: inherit; /* herda do elemento pai */
color: initial; /* valor inicial da propriedade */
```

## 5. **Variáveis CSS com Cores**

```css
:root {
  --cor-primaria: #3498db;
  --cor-secundaria: #2ecc71;
  --cor-texto: #333;
}

.elemento {
  color: var(--cor-texto);
  background-color: var(--cor-primaria);
}
```

## 6. **Dicas Práticas**

### **Contraste e Acessibilidade**
- Use contraste adequado entre texto e fundo (mínimo 4.5:1)
- Ferramentas: WebAIM Contrast Checker

### **Paletas de Cores**
- Use ferramentas como Coolors, Adobe Color
- Regra 60-30-10: 60% cor dominante, 30% secundária, 10% destaque

### **Transparência vs Opacidade**
```css
/* Transparência (apenas a cor) */
background: rgba(255, 0, 0, 0.5);

/* Opacidade (elemento inteiro, incluindo filhos) */
opacity: 0.5;
```

## 7. **Exemplo Completo**

```html
<!DOCTYPE html>
<html>
<head>
<style>
  :root {
    --azul: #3498db;
  }
  
  .caixa {
    /* Texto */
    color: #fff;
    
    /* Fundo com gradiente */
    background: linear-gradient(135deg, var(--azul), #2980b9);
    
    /* Borda */
    border: 3px solid rgba(0, 0, 0, 0.2);
    
    /* Sombra */
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
    
    padding: 20px;
    border-radius: 10px;
  }
  
  .caixa:hover {
    background: hsl(204, 70%, 53%);
  }
</style>
</head>
<body>
  <div class="caixa">
    Exemplo de cores em CSS
  </div>
</body>
</html>
```

## 8. **Conversão entre Formatos**

- **HEX para RGB:** Divida em pares e converta de hexadecimal para decimal
  - `#FF5733` → R: FF (255), G: 57 (87), B: 33 (51)
  
- Use ferramentas online ou DevTools do navegador para converter

**Dica final:** Prefira RGBA/HSLA quando precisar de transparência, HEX para cores sólidas simples, e HSL quando quiser controlar saturação e luminosidade facilmente.