# Guia: Quando Usar Fieldset em Formulários

## O que é Fieldset?

O `<fieldset>` é um elemento HTML usado para **agrupar campos relacionados** dentro de um formulário. Ele trabalha em conjunto com `<legend>` que fornece um título para o grupo.

```html
<fieldset>
  <legend>Título do Grupo</legend>
  <!-- campos relacionados aqui -->
</fieldset>
```

## ⚠️ Fieldset NÃO é obrigatório

Formulários funcionam perfeitamente sem `<fieldset>`. Ele é uma ferramenta **opcional** para melhorar organização, semântica e acessibilidade quando faz sentido.

## ✅ Quando USAR Fieldset

### 1. Formulários com múltiplas seções distintas

Quando há **divisões lógicas claras** que separam informações de natureza diferente:

```html
<form>
  <fieldset>
    <legend>Dados Pessoais</legend>
    <input type="text" name="nome" placeholder="Nome completo">
    <input type="email" name="email" placeholder="Email">
    <input type="tel" name="telefone" placeholder="Telefone">
  </fieldset>

  <fieldset>
    <legend>Endereço</legend>
    <input type="text" name="rua" placeholder="Rua">
    <input type="text" name="cidade" placeholder="Cidade">
    <input type="text" name="cep" placeholder="CEP">
  </fieldset>

  <fieldset>
    <legend>Informações de Pagamento</legend>
    <input type="text" name="cartao" placeholder="Número do cartão">
    <input type="text" name="cvv" placeholder="CVV">
    <input type="text" name="validade" placeholder="Validade">
  </fieldset>

  <button type="submit">Finalizar Cadastro</button>
</form>
```

**Por quê?** Cada seção tem um propósito distinto (pessoal, localização, pagamento).

### 2. Grupos de Radio Buttons

**Sempre recomendado** para melhorar acessibilidade:

```html
<fieldset>
  <legend>Escolha seu plano:</legend>
  
  <input type="radio" id="basico" name="plano" value="basico">
  <label for="basico">Plano Básico - R$ 29,90/mês</label>
  
  <input type="radio" id="plus" name="plano" value="plus">
  <label for="plus">Plano Plus - R$ 49,90/mês</label>
  
  <input type="radio" id="premium" name="plano" value="premium">
  <label for="premium">Plano Premium - R$ 99,90/mês</label>
</fieldset>
```

**Por quê?** Leitores de tela anunciam o contexto (pergunta) ao navegar pelas opções.

### 3. Grupos de Checkboxes relacionados

```html
<fieldset>
  <legend>Selecione suas áreas de interesse:</legend>
  
  <input type="checkbox" id="tech" name="interesses" value="tech">
  <label for="tech">Tecnologia</label>
  
  <input type="checkbox" id="design" name="interesses" value="design">
  <label for="design">Design</label>
  
  <input type="checkbox" id="marketing" name="interesses" value="marketing">
  <label for="marketing">Marketing</label>
  
  <input type="checkbox" id="vendas" name="interesses" value="vendas">
  <label for="vendas">Vendas</label>
</fieldset>
```

**Por quê?** Agrupa escolhas múltiplas sob um mesmo contexto/pergunta.

### 4. Quando precisa desabilitar um grupo inteiro

O atributo `disabled` no fieldset desabilita **todos os campos internos**:

```html
<fieldset disabled>
  <legend>Informações de Cobrança (indisponível)</legend>
  <input type="text" name="cartao">
  <input type="text" name="cvv">
  <input type="text" name="validade">
</fieldset>
```

**Por quê?** É a única forma de desabilitar múltiplos campos com um único atributo.

### 5. Formulários complexos com etapas

```html
<form>
  <fieldset>
    <legend>Etapa 1: Informações Básicas</legend>
    <!-- campos -->
  </fieldset>

  <fieldset>
    <legend>Etapa 2: Detalhes Adicionais</legend>
    <!-- campos -->
  </fieldset>

  <fieldset>
    <legend>Etapa 3: Confirmação</legend>
    <!-- campos -->
  </fieldset>
</form>
```

**Por quê?** Clarifica visualmente e semanticamente as etapas do processo.

## ❌ Quando NÃO USAR Fieldset

### 1. Formulários simples e curtos

```html
<!-- ❌ Desnecessário -->
<form>
  <fieldset>
    <legend>Login</legend>
    <input type="text" name="usuario">
    <input type="password" name="senha">
  </fieldset>
  <button type="submit">Entrar</button>
</form>

<!-- ✅ Melhor assim -->
<form>
  <h2>Login</h2>
  <label for="usuario">Usuário</label>
  <input type="text" id="usuario" name="usuario">
  
  <label for="senha">Senha</label>
  <input type="password" id="senha" name="senha">
  
  <button type="submit">Entrar</button>
</form>
```

### 2. Formulário de busca

```html
<!-- ❌ Exagero -->
<form role="search">
  <fieldset>
    <legend>Buscar</legend>
    <input type="search" name="q">
    <button type="submit">Buscar</button>
  </fieldset>
</form>

<!-- ✅ Adequado -->
<form role="search">
  <input type="search" name="q" placeholder="Buscar...">
  <button type="submit">Buscar</button>
</form>
```

### 3. Newsletter/Inscrição simples

```html
<!-- ❌ Over-engineering -->
<form>
  <fieldset>
    <legend>Receba novidades</legend>
    <input type="email" name="email">
    <button type="submit">Inscrever</button>
  </fieldset>
</form>

<!-- ✅ Direto ao ponto -->
<form>
  <label for="email">Receba nossas novidades:</label>
  <input type="email" id="email" name="email" placeholder="seu@email.com">
  <button type="submit">Inscrever</button>
</form>
```

### 4. Formulário de contato com poucos campos

**Exemplo: Nome, Email, Assunto, Mensagem**

```html
<!-- ❌ Divisão artificial e desnecessária -->
<form>
  <fieldset>
    <legend>Dados de Contato</legend>
    <input type="text" name="nome">
    <input type="email" name="email">
  </fieldset>
  
  <fieldset>
    <legend>Mensagem</legend>
    <input type="text" name="assunto">
    <textarea name="mensagem"></textarea>
  </fieldset>
  
  <button type="submit">Enviar</button>
</form>

<!-- ✅ Fluxo natural sem divisões forçadas -->
<form>
  <h2>Entre em Contato</h2>
  
  <label for="nome">Nome</label>
  <input type="text" id="nome" name="nome" required>
  
  <label for="email">Email</label>
  <input type="email" id="email" name="email" required>
  
  <label for="assunto">Assunto</label>
  <input type="text" id="assunto" name="assunto" required>
  
  <label for="mensagem">Mensagem</label>
  <textarea id="mensagem" name="mensagem" rows="5" required></textarea>
  
  <button type="submit">Enviar Mensagem</button>
</form>
```

**Por quê não usar?** Todos os campos têm o mesmo objetivo (enviar uma mensagem). Não há divisões naturais que justifiquem fieldsets.

## 📊 Tabela de Decisão Rápida

| Situação | Usar Fieldset? | Motivo |
|----------|----------------|--------|
| Formulário com seções distintas (cadastro, endereço, pagamento) | ✅ Sim | Agrupamento lógico claro |
| Grupo de radio buttons | ✅ Sim | Melhora acessibilidade |
| Grupo de checkboxes relacionados | ✅ Sim | Contexto comum |
| Precisa desabilitar grupo inteiro | ✅ Sim | Funcionalidade única |
| Login simples (2-3 campos) | ❌ Não | Desnecessário |
| Busca simples | ❌ Não | Over-engineering |
| Newsletter | ❌ Não | Muito simples |
| Contato com 4-5 campos lineares | ❌ Não | Sem divisão natural |
| Formulário de comentário | ❌ Não | Propósito único |

## 🎯 Regra de Ouro

> **Use `<fieldset>` quando houver um agrupamento lógico claro que beneficie a compreensão, acessibilidade ou funcionalidade do formulário.**

### Perguntas para decidir:

1. **Os campos formam grupos lógicos distintos?** → Se sim, use fieldset
2. **São radio buttons ou checkboxes relacionados?** → Use fieldset
3. **É um formulário simples e direto?** → Não use fieldset
4. **Preciso desabilitar um grupo inteiro?** → Use fieldset
5. **Estou dividindo artificialmente?** → Não use fieldset

## 💡 Benefícios do Fieldset (quando usado corretamente)

### 1. Acessibilidade
Leitores de tela anunciam o `<legend>` ao entrar no grupo, dando contexto aos usuários:

```
Usuário entra no grupo → "Dados Pessoais, grupo"
Navega para campo → "Nome, campo de texto"
```

### 2. Semântica
Torna explícita a relação entre campos para navegadores e tecnologias assistivas.

### 3. Funcionalidade
```html
<fieldset disabled>
  <!-- Todos os campos aqui ficam desabilitados -->
</fieldset>
```

### 4. Estilização em grupo
```css
fieldset {
  border: 2px solid #ddd;
  padding: 20px;
  margin: 20px 0;
}

fieldset:has(input:invalid) {
  border-color: red;
}
```

## 📝 Exemplos Práticos Comparados

### Exemplo 1: Cadastro Complexo

```html
<!-- ✅ USO CORRETO - Múltiplas seções distintas -->
<form>
  <fieldset>
    <legend>Informações Pessoais</legend>
    <input type="text" name="nome">
    <input type="email" name="email">
    <input type="date" name="nascimento">
  </fieldset>

  <fieldset>
    <legend>Endereço Residencial</legend>
    <input type="text" name="rua">
    <input type="text" name="numero">
    <input type="text" name="bairro">
    <input type="text" name="cidade">
  </fieldset>

  <fieldset>
    <legend>Preferências de Contato</legend>
    <input type="checkbox" id="email-pref" name="contato" value="email">
    <label for="email-pref">Email</label>
    
    <input type="checkbox" id="sms-pref" name="contato" value="sms">
    <label for="sms-pref">SMS</label>
    
    <input type="checkbox" id="tel-pref" name="contato" value="telefone">
    <label for="tel-pref">Telefone</label>
  </fieldset>

  <button type="submit">Cadastrar</button>
</form>
```

### Exemplo 2: Contato Simples

```html
<!-- ✅ USO CORRETO - Sem fieldset desnecessário -->
<form>
  <h2>Fale Conosco</h2>
  
  <div class="form-group">
    <label for="nome">Nome completo</label>
    <input type="text" id="nome" name="nome" required>
  </div>
  
  <div class="form-group">
    <label for="email">Seu email</label>
    <input type="email" id="email" name="email" required>
  </div>
  
  <div class="form-group">
    <label for="assunto">Assunto</label>
    <input type="text" id="assunto" name="assunto" required>
  </div>
  
  <div class="form-group">
    <label for="mensagem">Sua mensagem</label>
    <textarea id="mensagem" name="mensagem" rows="6" required></textarea>
  </div>
  
  <button type="submit">Enviar</button>
</form>
```

### Exemplo 3: Pesquisa com Filtros

```html
<!-- ✅ USO MISTO - Fieldset apenas onde faz sentido -->
<form>
  <!-- Busca simples sem fieldset -->
  <label for="busca">O que você procura?</label>
  <input type="search" id="busca" name="q">
  
  <!-- Filtros com fieldset -->
  <fieldset>
    <legend>Faixa de Preço</legend>
    <input type="radio" id="ate50" name="preco" value="0-50">
    <label for="ate50">Até R$ 50</label>
    
    <input type="radio" id="ate100" name="preco" value="50-100">
    <label for="ate100">R$ 50 - R$ 100</label>
    
    <input type="radio" id="acima100" name="preco" value="100+">
    <label for="acima100">Acima de R$ 100</label>
  </fieldset>
  
  <fieldset>
    <legend>Categorias</legend>
    <input type="checkbox" id="eletro" name="cat" value="eletronicos">
    <label for="eletro">Eletrônicos</label>
    
    <input type="checkbox" id="livros" name="cat" value="livros">
    <label for="livros">Livros</label>
    
    <input type="checkbox" id="roupas" name="cat" value="roupas">
    <label for="roupas">Roupas</label>
  </fieldset>
  
  <button type="submit">Buscar</button>
</form>
```

## 🎨 Estilização Básica

```css
fieldset {
  border: 2px solid #e0e0e0;
  border-radius: 8px;
  padding: 20px;
  margin: 20px 0;
  background-color: #fafafa;
}

legend {
  padding: 0 10px;
  font-weight: bold;
  font-size: 1.1em;
  color: #333;
}

/* Fieldset desabilitado */
fieldset:disabled {
  opacity: 0.6;
  background-color: #f5f5f5;
}

/* Remover bordas (manter semântica) */
fieldset.sem-borda {
  border: none;
  padding: 0;
  margin: 0;
}
```

## 🚫 Erros Comuns

### ❌ Erro 1: Usar fieldset em tudo
```html
<!-- Exagero desnecessário -->
<form>
  <fieldset>
    <legend>Email</legend>
    <input type="email" name="email">
  </fieldset>
  
  <fieldset>
    <legend>Senha</legend>
    <input type="password" name="senha">
  </fieldset>
</form>
```

### ❌ Erro 2: Fieldset sem legend
```html
<!-- Legend é obrigatório para acessibilidade -->
<fieldset>
  <!-- ❌ Sem legend! -->
  <input type="radio" name="opcao" value="1">
  <input type="radio" name="opcao" value="2">
</fieldset>
```

### ❌ Erro 3: Usar fieldset só por estética
```html
<!-- Use CSS para bordas, não fieldset -->
<fieldset>
  <legend>Título Bonito</legend>
  <!-- campos sem relação lógica -->
</fieldset>
```

## ✅ Conclusão

**Fieldset é uma ferramenta poderosa, mas opcional:**

- ✅ Use quando há agrupamento lógico real
- ✅ Use sempre com radio/checkbox relacionados
- ✅ Use para formulários complexos com seções
- ❌ Não use em formulários simples
- ❌ Não use para forçar divisões artificiais
- ❌ Não use só por estética

**A simplicidade é sempre melhor quando o formulário é simples!**