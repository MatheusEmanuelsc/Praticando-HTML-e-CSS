# Guia Completo de Formulários HTML

## 1. Estrutura Básica

```html
<form action="/processar" method="POST">
  <!-- action: URL de destino | method: GET ou POST -->
</form>
```

## 2. Principais Campos de Entrada

```html
<!-- Texto -->
<input type="text" name="nome" placeholder="Digite aqui" required>

<!-- Email -->
<input type="email" name="email" required>

<!-- Senha -->
<input type="password" name="senha" minlength="8">

<!-- Número -->
<input type="number" name="idade" min="18" max="100">

<!-- Data -->
<input type="date" name="data">

<!-- Telefone -->
<input type="tel" name="telefone">

<!-- Arquivo -->
<input type="file" name="arquivo">

<!-- Cor -->
<input type="color" name="cor">

<!-- Área de texto -->
<textarea name="mensagem" rows="4" maxlength="200"></textarea>

<!-- Dropdown -->
<select name="pais">
  <option value="">Selecione...</option>
  <option value="br">Brasil</option>
  <option value="pt">Portugal</option>
</select>

<!-- Radio buttons -->
<input type="radio" id="op1" name="opcao" value="1">
<label for="op1">Opção 1</label>

<!-- Checkbox -->
<input type="checkbox" id="aceito" name="aceito" value="sim">
<label for="aceito">Aceito os termos</label>

<!-- Botões -->
<button type="submit">Enviar</button>
<button type="reset">Limpar</button>
<button type="button">Customizado</button>
```

## 3. Fieldset e Legend (Agrupamento)

```html
<fieldset>
  <legend>Dados Pessoais</legend>
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome">
  
  <label for="email">Email:</label>
  <input type="email" id="email" name="email">
</fieldset>

<fieldset disabled>
  <legend>Seção Desabilitada</legend>
  <input type="text" name="campo">
</fieldset>
```

**Atributo `disabled`**: desabilita todos os campos dentro do fieldset.

## 4. Atributos de Validação

```html
<input type="text" required>              <!-- Obrigatório -->
<input type="text" minlength="3">         <!-- Mínimo de caracteres -->
<input type="text" maxlength="50">        <!-- Máximo de caracteres -->
<input type="number" min="0" max="100">   <!-- Valor mínimo/máximo -->
<input type="text" pattern="[0-9]{3}">    <!-- Expressão regular -->
<input type="text" readonly>              <!-- Somente leitura -->
<input type="text" disabled>              <!-- Desabilitado -->
<input type="text" autocomplete="off">    <!-- Desabilita autocomplete -->
```

## 5. Pseudo-classes de Estado

### Interação
```css
/* Foco */
input:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}

/* Hover */
input:hover {
  border-color: #999;
}

button:hover {
  background-color: #0056b3;
  transform: scale(1.05);
}

/* Clique ativo */
button:active {
  transform: scale(0.98);
}
```

### Validação
```css
/* Campo válido */
input:valid {
  border-color: green;
}

/* Campo inválido */
input:invalid {
  border-color: red;
}

/* Evitar mostrar erro antes da interação */
input:invalid:not(:focus):not(:placeholder-shown) {
  border-color: red;
  background-color: #fff5f5;
}

/* Campo válido preenchido */
input:valid:not(:placeholder-shown) {
  border-color: green;
  background-color: #f0fff4;
}

/* Valor dentro do range */
input[type="number"]:in-range {
  border-color: green;
}

/* Valor fora do range */
input[type="number"]:out-of-range {
  border-color: red;
  background-color: #ffe6e6;
}
```

### Obrigatoriedade
```css
/* Campo obrigatório */
input:required {
  border-left: 3px solid #ff6b6b;
}

/* Campo opcional */
input:optional {
  border-left: 3px solid #95e1d3;
}

/* Adicionar asterisco nos obrigatórios */
label:has(+ input:required)::after {
  content: " *";
  color: red;
}
```

### Habilitação
```css
/* Campo habilitado */
input:enabled {
  cursor: text;
}

/* Campo desabilitado */
input:disabled {
  background-color: #f5f5f5;
  cursor: not-allowed;
  opacity: 0.6;
}

/* Somente leitura */
input:read-only {
  background-color: #f9f9f9;
  border-style: dashed;
}

/* Editável */
input:read-write {
  background-color: white;
}
```

### Seleção
```css
/* Checkbox/Radio marcado */
input[type="checkbox"]:checked {
  accent-color: #007bff;
}

input[type="checkbox"]:checked + label {
  font-weight: bold;
  color: #007bff;
}

/* Estado indeterminado */
input[type="checkbox"]:indeterminate {
  accent-color: orange;
}
```

### Placeholder
```css
/* Quando placeholder está visível */
input:placeholder-shown {
  font-style: italic;
  border-color: #ddd;
}

/* Quando placeholder não está visível */
input:not(:placeholder-shown) {
  border-color: #007bff;
}

/* Estilizar o placeholder (pseudo-elemento) */
input::placeholder {
  color: #999;
  opacity: 0.7;
  font-size: 0.9em;
}

input:focus::placeholder {
  opacity: 0.4;
}
```

## 6. Seletores de Atributo

```css
/* Campos obrigatórios */
input[required] {
  border-left: 3px solid #ff6b6b;
}

/* Tipo específico */
input[type="email"] {
  font-family: monospace;
}

/* Com pattern */
input[pattern] {
  font-family: 'Courier New', monospace;
}

/* Autocomplete desabilitado */
input[autocomplete="off"] {
  background-color: #fffef0;
}
```

## 7. Pseudo-classes Combinadas

```css
/* Validação inteligente - erro após sair do campo */
input:invalid:not(:focus):not(:placeholder-shown) {
  border-color: #dc3545;
  background-color: #fff5f5;
}

/* Obrigatório vazio que já foi focado */
input:required:invalid:not(:focus):placeholder-shown {
  border-left: 3px solid orange;
}

/* Botão habilitado apenas com form válido */
form:valid button[type="submit"] {
  background-color: #28a745;
  cursor: pointer;
}

form:invalid button[type="submit"] {
  background-color: #ccc;
  cursor: not-allowed;
  opacity: 0.6;
}
```

## 8. Exemplo Completo

```html
<form action="/cadastro" method="POST">
  <fieldset>
    <legend>Cadastro de Usuário</legend>
    
    <div class="form-group">
      <label for="nome">Nome Completo</label>
      <input 
        type="text" 
        id="nome" 
        name="nome" 
        placeholder="Digite seu nome"
        required
        minlength="3">
    </div>

    <div class="form-group">
      <label for="email">Email</label>
      <input 
        type="email" 
        id="email" 
        name="email" 
        placeholder="seu@email.com"
        required>
    </div>

    <div class="form-group">
      <label for="idade">Idade</label>
      <input 
        type="number" 
        id="idade" 
        name="idade" 
        min="18" 
        max="100"
        required>
    </div>

    <div class="form-group">
      <label for="bio">Biografia</label>
      <textarea 
        id="bio" 
        name="bio" 
        rows="4"
        placeholder="Conte sobre você"
        maxlength="200"></textarea>
    </div>

    <div class="form-group">
      <input type="checkbox" id="termos" name="termos" required>
      <label for="termos">Aceito os termos de uso</label>
    </div>
  </fieldset>

  <button type="submit">Enviar Cadastro</button>
</form>
```

## 9. CSS Completo

```css
/* Fieldset */
fieldset {
  border: 2px solid #e0e0e0;
  border-radius: 10px;
  padding: 25px;
  margin: 20px 0;
  background-color: #fafafa;
}

legend {
  padding: 0 15px;
  font-weight: bold;
  font-size: 1.2em;
  color: #333;
}

/* Form groups */
.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: 500;
}

/* Campos de entrada */
input, textarea, select {
  width: 100%;
  padding: 10px;
  border: 2px solid #ddd;
  border-radius: 5px;
  font-size: 16px;
  transition: all 0.3s ease;
}

/* Foco */
input:focus, textarea:focus, select:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
}

/* Placeholder */
input::placeholder, textarea::placeholder {
  color: #aaa;
  font-style: italic;
}

input:focus::placeholder {
  opacity: 0.5;
}

/* Obrigatórios com indicador */
input:required {
  border-left: 4px solid #ffc107;
}

label:has(+ input:required)::after {
  content: " *";
  color: #dc3545;
  font-weight: bold;
}

/* Validação visual */
input:valid:not(:placeholder-shown) {
  border-left-color: #28a745;
  background-color: #f0fff4;
}

input:invalid:not(:focus):not(:placeholder-shown) {
  border-left-color: #dc3545;
  background-color: #fff5f5;
}

/* Range numérico */
input[type="number"]:out-of-range {
  border-color: #ff6b6b;
  animation: shake 0.3s;
}

@keyframes shake {
  0%, 100% { transform: translateX(0); }
  25% { transform: translateX(-5px); }
  75% { transform: translateX(5px); }
}

/* Checkbox checked */
input[type="checkbox"]:checked + label {
  color: #28a745;
  font-weight: bold;
}

/* Disabled */
input:disabled, textarea:disabled {
  background-color: #e9ecef;
  cursor: not-allowed;
  opacity: 0.7;
}

/* Read-only */
input:read-only {
  background-color: #f8f9fa;
  border-style: dashed;
}

/* Botões */
button {
  padding: 12px 30px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover:not(:disabled) {
  background-color: #0056b3;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

button:active {
  transform: translateY(0);
}

button:disabled {
  background-color: #6c757d;
  cursor: not-allowed;
  opacity: 0.5;
}

/* Form válido */
form:valid button[type="submit"] {
  background-color: #28a745;
}
```

## 10. JavaScript Útil

```javascript
// Prevenir submit padrão
const form = document.querySelector('form');
form.addEventListener('submit', function(e) {
  e.preventDefault();
  
  // Obter dados do formulário
  const dados = new FormData(form);
  
  for (let [campo, valor] of dados.entries()) {
    console.log(campo, valor);
  }
});

// Validação customizada
const input = document.querySelector('#email');
input.addEventListener('input', function() {
  if (!this.value.includes('@')) {
    this.setCustomValidity('Email deve conter @');
  } else {
    this.setCustomValidity('');
  }
});

// Checkbox indeterminado
document.querySelector('#checkbox').indeterminate = true;

// Contador de caracteres
const textarea = document.querySelector('textarea');
textarea.addEventListener('input', function() {
  const atual = this.value.length;
  const maximo = this.maxLength;
  console.log(`${atual}/${maximo}`);
});
```

## 11. Boas Práticas

✅ Sempre use `<label>` associado aos campos (atributo `for`)  
✅ Use `name` em todos os campos para envio de dados  
✅ Use `id` para acessibilidade e JavaScript  
✅ Agrupe campos relacionados com `<fieldset>` e `<legend>`  
✅ Forneça feedback visual para validação  
✅ Use `placeholder` para dicas, não para rótulos  
✅ Teste acessibilidade com leitores de tela  
✅ Valide no cliente E no servidor  
✅ Use tipos específicos de input (email, tel, number, etc)  
✅ Adicione mensagens de erro claras  

## 12. Resumo de Pseudo-classes

| Pseudo-classe | Descrição |
|--------------|-----------|
| `:focus` | Elemento com foco |
| `:hover` | Mouse sobre o elemento |
| `:active` | Elemento sendo clicado |
| `:valid` | Campo com valor válido |
| `:invalid` | Campo com valor inválido |
| `:required` | Campo obrigatório |
| `:optional` | Campo opcional |
| `:disabled` | Campo desabilitado |
| `:enabled` | Campo habilitado |
| `:read-only` | Campo somente leitura |
| `:read-write` | Campo editável |
| `:checked` | Checkbox/radio marcado |
| `:indeterminate` | Checkbox indeterminado |
| `:placeholder-shown` | Placeholder visível |
| `:in-range` | Valor dentro do range |
| `:out-of-range` | Valor fora do range |

## 13. Pseudo-elemento

| Pseudo-elemento | Descrição |
|----------------|-----------|
| `::placeholder` | Estiliza o texto do placeholder |