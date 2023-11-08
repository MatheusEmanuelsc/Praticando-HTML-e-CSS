# Seletores CSS e Exemplos

Os seletores CSS são usados para selecionar elementos HTML e aplicar estilos a eles. Abaixo estão alguns dos seletores mais comuns, acompanhados de exemplos para ilustrar seu uso:

## Seletores Básicos

1. **Seletores de tipo**: Selecionam elementos com base em seus tipos HTML.

   Exemplo:
   ```css
   p {
       color: blue;
   }
   ```

2. **Seletores de classe**: Selecionam elementos com base em suas classes atribuídas.

   Exemplo:
   ```css
   .destaque {
       font-weight: bold;
   }
   ```

3. **Seletores de ID**: Selecionam elementos com base em seus IDs únicos.

   Exemplo:
   ```css
   #cabecalho {
       background-color: #333;
   }
   ```

4. **Seletores universais**: Selecionam todos os elementos.

   Exemplo:
   ```css
   * {
       margin: 0;
       padding: 0;
   }
   ```

## Seletores de Atributos

5. **Seletores de atributos**: Selecionam elementos com base em atributos e valores específicos.

   Exemplo:
   ```css
   [href^="https://"] {
       color: green;
   }
   ```

## Seletores Combinados

6. **Seletores descendentes**: Selecionam elementos aninhados dentro de outros elementos.

   Exemplo:
   ```css
   .menu ul li {
       list-style: none;
   }
   ```

7. **Seletores filhos diretos**: Selecionam elementos filhos diretos.

   Exemplo:
   ```css
   div > p {
       font-size: 18px;
   }
   ```

8. **Seletores irmãos adjacentes**: Selecionam elementos que são irmãos diretos.

   Exemplo:
   ```css
   h2 + p {
       margin-top: 10px;
   }
   ```

9. **Seletores irmãos gerais**: Selecionam todos os irmãos que compartilham o mesmo pai.

   Exemplo:
   ```css
   .destaque ~ p {
       color: red;
   }
   ```

## Seletores Pseudo-classes

10. **Pseudo-classe `:hover`**: Aplicam estilos quando o mouse está sobre o elemento.

    Exemplo:
    ```css
    a:hover {
        text-decoration: underline;
    }
    ```

11. **Pseudo-classe `:nth-child(n)`**: Selecionam elementos com base em sua posição dentro do pai.

    Exemplo:
    ```css
    li:nth-child(odd) {
        background-color: #f2f2f2;
    }
    ```

## Seletores Pseudo-elementos

12. **Pseudo-elemento `::before`**: Criam pseudo-elementos antes do conteúdo do elemento.

    Exemplo:
    ```css
    h1::before {
        content: "Título: ";
    }
    ```

13. **Pseudo-elemento `::after`**: Criam pseudo-elementos após o conteúdo do elemento.

    Exemplo:
    ```css
    p::after {
        content: " (fim)";
    }
    ```

## Seletores de Estado

14. **Seletores de estado `:checked`**: Selecionam elementos de entrada que estão marcados.

    Exemplo:
    ```css
    input[type="checkbox"]:checked + label {
        text-decoration: line-through;
    }
    ```

15. **Seletores de estado `:disabled`**: Selecionam elementos que estão desabilitados.

    Exemplo:
    ```css
    input:disabled {
        opacity: 0.5;
    }
    ```

Estes exemplos ajudam a compreender como cada tipo de seletor CSS pode ser aplicado para estilizar elementos em uma página da web. Lembre-se de que a sintaxe e o suporte a seletores podem variar entre diferentes navegadores, portanto, é importante considerar a compatibilidade ao usá-los em projetos reais.