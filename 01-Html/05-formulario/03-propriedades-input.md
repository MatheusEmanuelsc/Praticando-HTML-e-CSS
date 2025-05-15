
## Propriedades de Campos de Entrada (`<input>`)

Os campos de entrada (`<input>`) em HTML possuem várias propriedades que podem ser utilizadas para personalizar seu comportamento e aparência. Abaixo estão algumas das propriedades mais comuns:

1. **`type`**
   - Define o tipo de campo de entrada. Pode ser `text`, `password`, `checkbox`, `radio`, etc.

   ```html
   <input type="text" name="username" placeholder="Digite seu nome de usuário">
   ```

2. **`name`**
   - Atribui um nome ao campo de entrada. É usado ao enviar dados do formulário para o servidor.

   ```html
   <input type="text" name="username">
   ```

3. **`id`**
   - Define um identificador único para o campo de entrada. Pode ser útil para referências em estilos ou scripts.

   ```html
   <input type="text" id="username" name="username">
   ```

4. **`value`**
   - Especifica um valor padrão para o campo de entrada.

   ```html
   <input type="text" name="username" value="Valor Padrão">
   ```

5. **`placeholder`**
   - Exibe um texto de exemplo dentro do campo de entrada para orientar o usuário sobre o que inserir.

   ```html
   <input type="text" name="username" placeholder="Digite seu nome de usuário">
   ```

6. **`readonly`**
   - Torna o campo de entrada somente leitura, impedindo que os usuários o alterem.

   ```html
   <input type="text" name="username" readonly>
   ```

7. **`disabled`**
   - Desabilita o campo de entrada, impedindo que os usuários o utilizem.

   ```html
   <input type="text" name="username" disabled>
   ```

8. **`required`**
   - Indica que o campo de entrada deve ser preenchido antes de enviar o formulário.

   ```html
   <input type="text" name="username" required>
   ```

9. **`maxlength`**
   - Define o número máximo de caracteres que um usuário pode inserir no campo de entrada.

   ```html
   <input type="text" name="username" maxlength="30">
   ```

10. **`min` e `max`** (para `type="number"`)
    - Define os valores mínimo e máximo permitidos para um campo de entrada numérico.

    ```html
    <input type="number" name="idade" min="18" max="99">
    ```

11. **`pattern`** (para `type="text"`)
    - Especifica um padrão (expressão regular) que o valor do campo de entrada deve corresponder.

    ```html
    <input type="text" name="codigo" pattern="[A-Za-z0-9]{8}">
    ```

12. **`autocomplete`**
    - Controla a funcionalidade de preenchimento automático do navegador para o campo de entrada.

    ```html
    <input type="text" name="cidade" autocomplete="off">
    ```

13. **`autofocus`**
    - Define que o campo de entrada deve receber automaticamente o foco quando a página é carregada.

    ```html
    <input type="text" name="username" autofocus>
    ```

Lembre-se de que nem todos os tipos de campo suportam todas as propriedades. A escolha das propriedades dependerá do tipo específico de campo e dos requisitos do seu formulário.