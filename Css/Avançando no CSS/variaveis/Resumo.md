# Módulo 1: Variáveis no CSS

## Índice
1. [Introdução](#introdução)
2. [Declaração de Variáveis](#declaração-de-variáveis)
3. [Utilizando Variáveis](#utilizando-variáveis)
4. [Vantagens das Variáveis](#vantagens-das-variáveis)
5. [Exemplo Prático](#exemplo-prático)
6. [Conclusão](#conclusão)

### Introdução
Variáveis no CSS oferecem uma maneira eficiente de gerenciar e reutilizar valores em folhas de estilo. Elas são especialmente úteis para simplificar o código, facilitar a manutenção e tornar o design mais consistente.

### Declaração de Variáveis
Para declarar uma variável no CSS, utilize o seletor `:root` para definir variáveis globais. A sintaxe básica é:
```css
:root {
  --nome-da-variavel: valor;
}
```

### Utilizando Variáveis
As variáveis podem ser utilizadas em qualquer parte do seu código CSS. Para isso, utilize a função `var()`:
```css
seletor {
  propriedade: var(--nome-da-variavel);
}
```

### Vantagens das Variáveis
- **Manutenção Simples:** Alterar o valor de uma variável atualiza automaticamente todos os elementos que a utilizam.
- **Consistência:** Garante consistência visual ao longo da folha de estilo.
- **Legibilidade:** Torna o código mais legível e fácil de entender.

### Exemplo Prático
```css
:root {
  --cor-primaria: #3498db;
  --cor-secundaria: #2ecc71;
}

body {
  background-color: var(--cor-primaria);
  color: var(--cor-secundaria);
}

.header {
  border-bottom: 2px solid var(--cor-secundaria);
}
```

### Conclusão
O uso de variáveis no CSS é uma prática recomendada para melhorar a organização e manutenção do código, além de promover consistência visual.

---

# Módulo 2: Escopo em CSS

## Índice
1. [Introdução ao Escopo](#introdução-ao-escopo)
2. [Escopo Global](#escopo-global)
3. [Escopo Local](#escopo-local)
4. [Conclusão](#conclusão-escopo)

### Introdução ao Escopo
Em CSS, o escopo refere-se à área do código onde uma determinada regra ou estilo é aplicado. Compreender o escopo é crucial para evitar conflitos e garantir que as estilizações sejam aplicadas conforme desejado.

### Escopo Global
As regras definidas fora de qualquer seletor têm escopo global e afetam todos os elementos na página. Exemplo:
```css
body {
  font-family: 'Arial', sans-serif;
}
```

### Escopo Local
Regras dentro de um seletor específico têm escopo local e afetam apenas os elementos correspondentes. Exemplo:
```css
.header {
  background-color: #333;
  color: #fff;
}
```

### Conclusão - Escopo
Compreender o escopo em CSS é fundamental para evitar conflitos entre estilos e garantir que as regras se apliquem conforme a intenção do desenvolvedor. O uso consciente do escopo contribui para um código mais limpo e manutenível.

