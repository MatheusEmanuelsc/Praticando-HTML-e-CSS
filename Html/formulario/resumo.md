# HTML Formulários - Resumo

## Índice

1. [Introdução](#introdução)
2. [Parte 1: Tags e Atributos](#parte-1-tags-e-atributos)
   1. [\<form\>](#form)
   2. [\<input\>](#input)
   3. [\<label\>](#label)
   4. [\<select\>](#select)
   5. [\<textarea\>](#textarea)
   6. [\<button\>](#button)
   7. [Outras Tags Relacionadas](#outras-tags-relacionadas)
3. [Parte 2: Exemplos Práticos](#parte-2-exemplos-práticos)
   1. [Formulário Simples](#formulário-simples)
   2. [Caixas de Seleção](#caixas-de-seleção)
   3. [Campo de Texto Multilinha](#campo-de-texto-multilinha)
   4. [Botões de Opção](#botões-de-opção)

---

## Introdução

Formulários HTML são elementos essenciais para interação do usuário com páginas web. Eles permitem coletar dados que podem ser processados pelo servidor. Este resumo aborda as principais tags e atributos relacionados a formulários HTML.

## Parte 1: Tags e Atributos

### \<form\>

A tag \<form\> define um formulário HTML e é usada para encapsular os elementos de entrada.

Atributos principais:
- **action**: Especifica o URL para onde os dados do formulário serão enviados.
- **method**: Define o método HTTP usado ao enviar os dados (GET ou POST).

### \<input\>

A tag \<input\> cria uma caixa de entrada que permite ao usuário inserir dados.

Atributos comuns:
- **type**: Especifica o tipo de entrada (text, password, checkbox, radio, etc.).
- **name**: Define um nome para a entrada, usado ao enviar dados para o servidor.

### \<label\>

A tag \<label\> associa um rótulo descritivo a um elemento de formulário.

Atributos:
- **for**: Especifica qual elemento de formulário o rótulo está associado, usando o valor do atributo "id" desse elemento.

### \<select\>

A tag \<select\> cria uma lista suspensa (dropdown) de opções.

Atributos principais:
- **name**: Define um nome para a lista suspensa.

### \<textarea\>

A tag \<textarea\> cria uma área de texto multilinha.

Atributos principais:
- **name**: Define um nome para a área de texto.
- **rows** e **cols**: Especificam o número de linhas e colunas da área de texto.

### \<button\>

A tag \<button\> cria um botão dentro do formulário.

Atributos principais:
- **type**: Especifica o tipo de botão (submit, reset, button).

### Outras Tags Relacionadas

Existem tags como \<fieldset\> e \<legend\> para agrupar e descrever elementos do formulário, respectivamente.

## Parte 2: Exemplos Práticos

### Formulário Simples

```html
<!-- Este é um formulário simples com campos de texto e um botão de envio -->
<form action="/processar-dados" method="post">
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome">

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <button type="submit">Enviar</button>
</form>
```

Comentário: Neste exemplo, criamos um formulário básico com campos de texto para nome e email, e um botão de envio.

### Caixas de Seleção

```html
<!-- Exemplo de uso da tag <select> com opções -->
<form action="/processar-escolha" method="post">
  <label for="escolha">Escolha uma opção:</label>
  <select id="escolha" name="escolha">
    <option value="opcao1">Opção 1</option>
    <option value="opcao2">Opção 2</option>
    <option value="opcao3">Opção 3</option>
  </select>

  <button type="submit">Enviar</button>
</form>
```

Comentário: Aqui, utilizamos a tag \<select\> para criar uma lista suspensa com três opções.

### Campo de Texto Multilinha

```html
<!-- Exemplo de uso da tag <textarea> para entrada de texto multilinha -->
<form action="/processar-comentario" method="post">
  <label for="comentario">Deixe seu comentário:</label>
  <textarea id="comentario" name="comentario" rows="4" cols="50"></textarea>

  <button type="submit">Enviar</button>
</form>
```

Comentário: Utilizamos a tag \<textarea\> para permitir que os usuários insiram comentários mais extensos.

### Botões de Opção

```html
<!-- Exemplo de botões de opção usando <input> com type="radio" -->
<form action="/processar-opcao" method="post">
  <label>Escolha uma opção:</label>
  <input type="radio" id="opcao1" name="opcao" value="opcao1">
  <label for="opcao1">Opção 1</label>

  <input type="radio" id="opcao2" name="opcao" value="opcao2">
  <label for="opcao2">Opção 2</label>

  <input type="radio" id="opcao3" name="opcao" value="opcao3">
  <label for="opcao3">Opção 3</label>

  <button type="submit">Enviar</button>
</form>
```

Comentário: Demonstramos o uso de botões de opção usando \<input\> com type="radio" e rótulos associados com a tag \<label\>.

Este resumo fornece uma visão abrangente dos elementos básicos de formulários HTML, desde as tags até os atributos, com exemplos práticos ilustrativos.