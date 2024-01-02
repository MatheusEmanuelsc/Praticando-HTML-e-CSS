# Pseudo-classes no CSS

As pseudo-classes no CSS são seletores que permitem selecionar elementos com base em seu estado ou posição no documento. Elas proporcionam uma maneira de estilizar elementos de acordo com interações do usuário ou contextos específicos.

## Pseudo-classes de interação:

### 1. `:hover`
Acionada quando o usuário passa o mouse sobre um elemento.

### 2. `:active`
Aplicada quando o elemento está sendo ativado, geralmente quando o botão do mouse está pressionado.

### 3. `:focus`
Aplicada quando um elemento está com foco, como quando um campo de formulário é selecionado.

## Pseudo-classes de posicionamento:

### 4. `:first-child`
Seleciona o primeiro filho de um elemento pai.

### 5. `:last-child`
Seleciona o último filho de um elemento pai.

### 6. `:nth-child`
Seleciona elementos com base em sua posição em relação aos irmãos.

### 7. `:nth-last-child`
Semelhante a `:nth-child`, mas conta as posições a partir do final.

### 8. `:nth-of-type`
Seleciona elementos com base em sua posição em relação aos irmãos do mesmo tipo.

### 9. `:nth-last-of-type`
Semelhante a `:nth-of-type`, mas conta as posições a partir do final.

## Pseudo-classes de estado:

### 10. `:checked`
Aplicada a elementos de input quando estão marcados (checkboxes ou radio buttons).

### 11. `:disabled`
Aplicada a elementos desativados.

### 12. `:enabled`
Aplicada a elementos ativados.

### 13. `:read-only` e `:read-write`
Aplicadas a elementos de input com atributos `readonly` e `readwrite`, respectivamente.

### 14. `:required` e `:optional`
Aplicadas a elementos de input com atributos `required` e `optional`, respectivamente.

## Pseudo-classes de negação:

### 15. `:not`
Nega a seleção de elementos que correspondem ao seletor especificado.

```css
/* Exemplo de :not */
input:not([type="submit"]) {
  border: 1px solid #ccc;
}
```

Essas são apenas algumas das pseudo-classes disponíveis no CSS. Cada uma delas oferece uma maneira única de selecionar e estilizar elementos com base em diferentes condições, proporcionando maior flexibilidade no design e na interação do usuário.