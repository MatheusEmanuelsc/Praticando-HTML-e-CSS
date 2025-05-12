# Tabelas em HTML e CSS

Este documento fornece um resumo abrangente sobre o uso de tabelas em HTML e sua estilização com CSS, dividindo o conteúdo em módulos distintos.

## Módulo 1: Tabelas em HTML

### Estrutura Básica da Tabela

```html
<table>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Cell 1</td>
      <td>Row 1, Cell 2</td>
    </tr>
    <tr>
      <td>Row 2, Cell 1</td>
      <td>Row 2, Cell 2</td>
    </tr>
  </tbody>
</table>
```

### Elementos Importantes

- `<table>`: Define a tabela.
- `<thead>`: Cabeçalho da tabela.
- `<tbody>`: Corpo da tabela.
- `<tr>`: Linha da tabela.
- `<th>`: Cabeçalho da célula.
- `<td>`: Célula padrão.

### Atributos Importantes

- `colspan`: Especifica o número de colunas que uma célula deve se estender.
- `rowspan`: Especifica o número de linhas que uma célula deve se estender.

## Módulo 2: Estilização com CSS

### Seletores Básicos

```css
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}

th {
  background-color: #f2f2f2;
}
```

### Propriedades Importantes

- `border-collapse`: Define a modelagem da borda das células.
- `border`: Define a largura, estilo e cor da borda.
- `padding`: Espaçamento interno da célula.
- `text-align`: Alinhamento do texto na célula.
- `background-color`: Cor de fundo da célula.

## Módulo 3: Responsividade

### Uso de Media Queries

```css
@media (max-width: 600px) {
  th, td {
    display: block;
    width: 100%;
  }
}
```

### Tornando a Tabela Responsiva

- Utilize media queries para ajustar o layout em dispositivos de tela pequena.
- Converta as células em blocos para empilhamento vertical.

Este resumo oferece uma visão abrangente sobre a criação e estilização de tabelas em HTML e CSS, destacando elementos essenciais e técnicas de responsividade para uma experiência de usuário otimizada.