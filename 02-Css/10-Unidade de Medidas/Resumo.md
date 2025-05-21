**Índice:**
1. [Unidades de Medida no CSS](#unidades-de-medida-no-css)
2. [Explicação Detalhada e Exemplos](#explicação-detalhada-e-exemplos)

---

# Unidades de Medida no CSS

O CSS (Cascading Style Sheets) utiliza diversas unidades de medida para definir propriedades como comprimento, largura, margens, entre outras. Essas unidades podem ser classificadas em duas categorias principais: unidades absolutas e unidades relativas.

**1. Unidades Absolutas:**
   - 1.1 `cm`: Centímetros
   - 1.2 `mm`: Milímetros
   - 1.3 `in`: Polegadas
   - 1.4 `px`: Pixels

**2. Unidades Relativas:**
   - 2.1 `em`: Relativo ao tamanho da fonte do elemento
   - 2.2 `rem`: Relativo ao tamanho da fonte do elemento raiz (root)
   - 2.3 `%`: Porcentagem do valor do elemento pai
   - 2.4 `vw`: Relativo à largura da viewport
   - 2.5 `vh`: Relativo à altura da viewport

---

# Explicação Detalhada e Exemplos

## 1. Unidades Absolutas

### 1.1 `cm` (Centímetros)
A unidade `cm` representa centímetros. Exemplo:
```css
div {
   width: 5cm;
   height: 3cm;
}
```

### 1.2 `mm` (Milímetros)
A unidade `mm` representa milímetros. Exemplo:
```css
p {
   margin-bottom: 10mm;
}
```

### 1.3 `in` (Polegadas)
A unidade `in` representa polegadas. Exemplo:
```css
img {
   width: 2in;
}

### 1.4 `px` (Pixels)
A unidade `px` representa pixels. Exemplo:
```css
body {
   font-size: 16px;
}
```

## 2. Unidades Relativas

### 2.1 `em`
A unidade `em` é relativa ao tamanho da fonte do elemento. Exemplo:
```css
p {
   margin-left: 2em;
}
```

### 2.2 `rem`
A unidade `rem` é relativa ao tamanho da fonte do elemento raiz. Exemplo:
```css
body {
   font-size: 18px;
}

p {
   margin-top: 1.5rem;
}
```

### 2.3 `%`
A unidade `%` representa uma porcentagem do valor do elemento pai. Exemplo:
```css
div {
   width: 50%;
}

### 2.4 `vw`
A unidade `vw` é relativa à largura da viewport. Exemplo:
```css
section {
   width: 50vw;
}
```

### 2.5 `vh`
A unidade `vh` é relativa à altura da viewport. Exemplo:
```css
header {
   height: 20vh;
}
```

Este guia fornece uma visão geral das unidades de medida no CSS, com exemplos para ilustrar o uso de cada uma. Utilize essas unidades conforme a necessidade e contexto do seu projeto.