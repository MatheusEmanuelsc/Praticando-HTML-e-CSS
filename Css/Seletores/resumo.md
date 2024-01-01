```markdown
# Resumo de Seletores CSS

Este é um resumo abrangente de todos os seletores CSS, incluindo uma breve descrição e exemplos. Certifique-se de que nenhum seletor seja esquecido. O formato do resumo é em um arquivo `readme.md` com índice e explicações detalhadas.

## Índice

1. [Seletor Universal (`*`)](#1-seletor-universal)
2. [Seletor de Tipo (Seletor de Elemento)](#2-seletor-de-tipo)
3. [Seletor de Classe (`.nome-da-classe`)](#3-seletor-de-classe)
4. [Seletor de ID (`#id`)](#4-seletor-de-id)
5. [Combinador Descendente (` `)](#5-combinador-descendente)
6. [Combinador de Filho (`>`)](#6-combinador-de-filho)
7. [Combinador de Irmão Adjacente (`+`)](#7-combinador-de-irmao-adjacente)
8. [Combinador de Irmão Geral (`~`)](#8-combinador-de-irmao-geral)
9. [Seletor de Atributo (`[attr=valor]`)](#9-seletor-de-atributo)
10. [Seletor de Atributo que Começa (`[attr^=valor]`)](#10-seletor-de-atributo-que-comeca)
11. [Seletor de Atributo que Termina (`[attr$=valor]`)](#11-seletor-de-atributo-que-termina)
12. [Seletor de Atributo que Contém (`[attr*=valor]`)](#12-seletor-de-atributo-que-contem)
13. [Pseudo-classe de Negação (`:not(seletor)`)](#13-pseudo-classe-de-negacao)
14. [Pseudo-classe Primeiro Filho (`:first-child`)](#14-pseudo-classe-primeiro-filho)
15. [Pseudo-classe Último Filho (`:last-child`)](#15-pseudo-classe-ultimo-filho)
16. [Pseudo-classe Único Filho (`:only-child`)](#16-pseudo-classe-unico-filho)
17. [Pseudo-classe Vazio (`:empty`)](#17-pseudo-classe-vazio)
18. [Pseudo-classe Nth Child (`:nth-child()`)](#18-pseudo-classe-nth-child)
19. [Pseudo-classe Nth Last Child (`:nth-last-child()`)](#19-pseudo-classe-nth-last-child)
20. [Pseudo-classe Primeiro do Tipo (`:first-of-type`)](#20-pseudo-classe-primeiro-do-tipo)
21. [Pseudo-classe Último do Tipo (`:last-of-type`)](#21-pseudo-classe-ultimo-do-tipo)
22. [Pseudo-classe Único do Tipo (`:only-of-type`)](#22-pseudo-classe-unico-do-tipo)
23. [Pseudo-classe Nth do Tipo (`:nth-of-type()`)](#23-pseudo-classe-nth-of-type)
24. [Pseudo-classe Nth Last do Tipo (`:nth-last-of-type()`)](#24-pseudo-classe-nth-last-of-type)
25. [Pseudo-classe Raiz (`:root`)](#25-pseudo-classe-raiz)
26. [Pseudo-classe Alvo (`:target`)](#26-pseudo-classe-alvo)
27. [Pseudo-classe Habilitado (`:enabled`)](#27-pseudo-classe-habilitado)
28. [Pseudo-classe Desabilitado (`:disabled`)](#28-pseudo-classe-desabilitado)
29. [Pseudo-classe Marcado (`:checked`)](#29-pseudo-classe-marcado)
30. [Pseudo-classe Padrão (`:default`)](#30-pseudo-classe-padrao)
31. [Pseudo-classe Válido (`:valid`)](#31-pseudo-classe-valido)
32. [Pseudo-classe Inválido (`:invalid`)](#32-pseudo-classe-invalido)
33. [Pseudo-classe Obrigatório (`:required`)](#33-pseudo-classe-obrigatorio)
34. [Pseudo-classe Somente Leitura (`:read-only`)](#34-pseudo-classe-somente-leitura)
35. [Pseudo-classe Leitura-Escrita (`:read-write`)](#35-pseudo-classe-leitura-escrita)
36. [Pseudo-elemento Seleção (`::selection`)](#36-pseudo-elemento-selecao)
37. [Pseudo-elemento Antes (`::before`)](#37-pseudo-elemento-antes)
38. [Pseudo-elemento Depois (`::after`)](#38-pseudo-elemento-depois)
39. [Pseudo-elemento Primeira Linha (`::first-line`)](#39-pseudo-elemento-primeira-linha)
40. [Pseudo-elemento Primeira Letra (`::first-letter`)](#40-pseudo-elemento-primeira-letra)

---

### 1. Seletor Universal (`*`)

O seletor universal `*` seleciona todos os elementos em um documento HTML.

#### Exemplo:

```css
* {
  margin: 0;
  padding: 0;
}
```

---

### 2. Seletor de Tipo (Seletor de Elemento)

O seletor de tipo seleciona todos os elementos de um tipo

 específico.

#### Exemplo:

```css
p {
  color: blue;
}
```

---

### 3. Seletor de Classe (`.nome-da-classe`)

O seletor de classe seleciona elementos com um determinado valor de classe.

#### Exemplo:

```css
.button {
  background-color: #008000;
}
```

---

### 4. Seletor de ID (`#id`)

O seletor de ID seleciona um elemento com um ID específico.

#### Exemplo:

```css
#header {
  font-size: 24px;
}
```

---

Agora, o resumo inclui exemplos para os seletores de 1 a 4 em um formato mais adequado para um arquivo `readme.md`. Se precisar de mais alguma coisa, estou à disposição.

### 5. Combinador Descendente (` `)

O combinador descendente seleciona todos os elementos descendentes de um elemento.

#### Exemplo:

```css
article p {
  font-style: italic;
}
```

---

### 6. Combinador de Filho (`>`)

O combinador de filho seleciona elementos que são filhos diretos de um elemento.

#### Exemplo:

```css
ul > li {
  list-style-type: square;
}
```

---

### 7. Combinador de Irmão Adjacente (`+`)

O combinador de irmão adjacente seleciona o elemento que é imediatamente precedido por um elemento especificado.

#### Exemplo:

```css
h2 + p {
  font-weight: bold;
}
```

---

### 8. Combinador de Irmão Geral (`~`)

O combinador de irmão geral seleciona todos os elementos irmãos que compartilham o mesmo pai.

#### Exemplo:

```css
h2 ~ p {
  color: #888888;
}
```

---

### 9. Seletor de Atributo (`[attr=valor]`)

O seletor de atributo seleciona elementos com um atributo específico e valor.

#### Exemplo:

```css
input[type="text"] {
  border: 1px solid #999999;
}
```

---

### 10. Seletor de Atributo que Começa (`[attr^=valor]`)

O seletor de atributo que começa com seleciona elementos com um atributo cujo valor começa com uma string específica.

#### Exemplo:

```css
a[href^="https://"] {
  color: #3366cc;
}
```

---

### 11. Seletor de Atributo que Termina (`[attr$=valor]`)

O seletor de atributo que termina com seleciona elementos com um atributo cujo valor termina com uma string específica.

#### Exemplo:

```css
a[href$=".pdf"] {
  color: #ff0000;
}
```

---

### 12. Seletor de Atributo que Contém (`[attr*=valor]`)

O seletor de atributo que contém seleciona elementos com um atributo que contém uma substring específica.

#### Exemplo:

```css
input[name*="user"] {
  background-color: #f0f0f0;
}
```

---

### 13. Pseudo-classe de Negação (`:not(seletor)`)

A pseudo-classe de negação seleciona elementos que não correspondem ao seletor especificado.

#### Exemplo:

```css
p:not(.special) {
  font-size: 16px;
}
```

---

### 14. Pseudo-classe Primeiro Filho (`:first-child`)

A pseudo-classe `:first-child` seleciona o elemento que é o primeiro filho de seu pai.

#### Exemplo:

```css
p:first-child {
  font-weight: bold;
}
```

---

### 15. Pseudo-classe Último Filho (`:last-child`)

A pseudo-classe `:last-child` seleciona o elemento que é o último filho de seu pai.

#### Exemplo:

```css
li:last-child {
  margin-bottom: 0;
}
```

---

### 16. Pseudo-classe Único Filho (`:only-child`)

A pseudo-classe `:only-child` seleciona o elemento que é o único filho de seu pai.

#### Exemplo:

```css
div:only-child {
  border: 1px solid #999;
}
```

---

### 17. Pseudo-classe Vazio (`:empty`)

A pseudo-classe `:empty` seleciona elementos que não têm filhos, incluindo espaços em branco e comentários.

#### Exemplo:

```css
p:empty {
  display: none;
}
```

---

### 18. Pseudo-classe Nth Child (`:nth-child()`)

A pseudo-classe `:nth-child()` seleciona elementos com base em sua posição em relação a seus pais.

#### Exemplo:

```css
li:nth-child(odd) {
  background-color: #f2f2f2;
}
```

---

### 19. Pseudo-classe Nth Last Child (`:nth-last-child()`)

A pseudo-classe `:nth-last-child()` seleciona elementos com base em sua posição em relação aos filhos do final.

#### Exemplo:

```css
div:nth-last-child(2) {
  border: 2px solid #ccc;
}
```

---

### 20. Pseudo-classe Primeiro do Tipo (`:first-of-type`)

A pseudo-classe `:first-of-type` seleciona o primeiro elemento de seu tipo.

#### Exemplo:

```css
h2:first-of-type {
  color: #cc0000;
}
```

---

### 21. Pseudo-classe Último do Tipo (`:last-of-type`)

A pseudo-classe `:last-of-type` seleciona o último elemento de seu tipo.

#### Exemplo:

```css
span:last-of-type {
  text-decoration: underline;
}
```

---

### 22. Pseudo-classe Único do Tipo (`:only-of-type`)

A pseudo-classe `:only-of-type` seleciona o elemento que é o único elemento de seu tipo entre os filhos do mesmo pai.

#### Exemplo:

```css
input:only-of-type {
  width: 200px;
}
```

---

### 23. Pseudo-classe Nth do Tipo (`:nth-of-type()`)

A pseudo-classe `:nth-of-type()` seleciona elementos com base em sua posição em relação aos irmãos do mesmo tipo.

#### Exemplo:

```css
p:nth-of-type(even) {
  background-color: #f0f0f0;
}
```

---

### 24. Pseudo-classe Nth Last do Tipo (`:nth-last-of-type()`)

A pseudo-classe `:nth-last-of-type()` seleciona elementos com base em sua posição em relação aos irmãos do mesmo tipo, contando do final.

#### Exemplo:

```css
span:nth-last-of-type(3

) {
  color: #999;
}
```

---

### 25. Pseudo-classe Raiz (`:root`)

A pseudo-classe `:root` seleciona o elemento raiz do documento, geralmente `<html>`.

#### Exemplo:

```css
:root {
  font-size: 16px;
}
```

---

### 26. Pseudo-classe Alvo (`:target`)

A pseudo-classe `:target` seleciona o elemento alvo de um URL.

#### Exemplo:

```css
#section1:target {
  background-color: #ffffcc;
}
```

---

### 27. Pseudo-classe Habilitado (`:enabled`)

A pseudo-classe `:enabled` seleciona elementos de entrada que estão habilitados.

#### Exemplo:

```css
input:enabled {
  border: 1px solid #00cc00;
}
```

---

### 28. Pseudo-classe Desabilitado (`:disabled`)

A pseudo-classe `:disabled` seleciona elementos de entrada que estão desabilitados.

#### Exemplo:

```css
input:disabled {
  background-color: #f2f2f2;
}
```

---

### 29. Pseudo-classe Marcado (`:checked`)

A pseudo-classe `:checked` seleciona elementos de entrada do tipo checkbox ou radio que estão marcados.

#### Exemplo:

```css
input:checked {
  border: 2px solid #3399ff;
}
```

---

### 30. Pseudo-classe Padrão (`:default`)

A pseudo-classe `:default` seleciona o elemento de entrada padrão em um formulário.

#### Exemplo:

```css
input:default {
  border: 2px solid #ff6600;
}
```

---

### 31. Pseudo-classe Válido (`:valid`)

A pseudo-classe `:valid` seleciona elementos de entrada que são considerados válidos.

#### Exemplo:

```css
input:valid {
  border: 1px solid #00cc00;
}
```

---

### 32. Pseudo-classe Inválido (`:invalid`)

A pseudo-classe `:invalid` seleciona elementos de entrada que são considerados inválidos.

#### Exemplo:

```css
input:invalid {
  border: 2px solid #ff0000;
}
```

---

### 33. Pseudo-classe Obrigatório (`:required`)

A pseudo-classe `:required` seleciona elementos de entrada que são obrigatórios.

#### Exemplo:

```css
input:required {
  background-color: #ffff99;
}
```

---

### 34. Pseudo-classe Somente Leitura (`:read-only`)

A pseudo-classe `:read-only` seleciona elementos de entrada que são apenas leitura.

#### Exemplo:

```css
input:read-only {
  background-color: #f0f0f0;
}
```

---

### 35. Pseudo-classe Leitura-Escrita (`:read-write`)

A pseudo-classe `:read-write` seleciona elementos de entrada que são leitura-escrita.

#### Exemplo:

```css
input:read-write {
  border: 1px solid #999999;
}
```

---

### 36. Pseudo-elemento Seleção (`::selection`)

O pseudo-elemento `::selection` seleciona o texto selecionado pelo usuário.

#### Exemplo:

```css
::selection {
  background-color: #66ccff;
}
```

---

### 37. Pseudo-elemento Antes (`::before`)

O pseudo-elemento `::before` insere conteúdo antes do conteúdo do elemento selecionado.

#### Exemplo:

```css
p::before {
  content: ">> ";
}
```

---

### 38. Pseudo-elemento Depois (`::after`)

O pseudo-elemento `::after` insere conteúdo após o conteúdo do elemento selecionado.

#### Exemplo:

```css
p::after {
  content: " <<";
}
```

---

### 39. Pseudo-elemento Primeira Linha (`::first-line`)

O pseudo-elemento `::first-line` seleciona a primeira linha de um elemento.

#### Exemplo:

```css
p::first-line {
  font-weight: bold;
}
```

---

### 40. Pseudo-elemento Primeira Letra (`::first-letter`)

O pseudo-elemento `::first-letter` seleciona a primeira letra de um elemento.

#### Exemplo:

```css
p::first-letter {
  font-size: 150%;
  color: #900;
}
```

