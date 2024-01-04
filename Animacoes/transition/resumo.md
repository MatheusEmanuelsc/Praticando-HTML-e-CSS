

### `transition`

- **Explicação:** Define a transição suave entre os estados de um elemento, permitindo animações de propriedades específicas quando ocorrem alterações.

- **Sintaxe:**
  ```css
  transition: propriedade duração [função-tempo] [atraso];
  ```

  - `propriedade`: Nome da propriedade CSS a ser animada (por exemplo, `color`, `opacity`).
  - `duração`: Tempo que a transição deve levar para ser concluída (em segundos ou milissegundos).
  - `[função-tempo]`: (Opcional) Função de tempo que define a curva de aceleração da transição (por exemplo, `ease`, `linear`, `ease-in-out`).
  - `[atraso]`: (Opcional) Atraso antes que a transição comece (em segundos ou milissegundos).

- **Exemplo:**
  ```css
  .elemento {
    transition: width 0.3s ease-in-out 0.2s;
  }
  ```

  Neste exemplo, a largura do elemento terá uma transição de 0.3 segundos, usando a função de tempo `ease-in-out`, com um atraso de 0.2 segundos antes do início da transição.

- **Utilização com Pseudo-Elementos e Pseudo-Classes:**
  A propriedade `transition` pode ser usada em conjunto com pseudo-elementos (`::before`, `::after`) e pseudo-classes (`:hover`, `:focus`) para criar transições em diferentes estados ou interações do usuário.

- **Observações:**
  - A propriedade `transition` é uma maneira eficaz de adicionar animações suaves a elementos sem a necessidade de usar keyframes.
  - As transições podem ser aplicadas a várias propriedades simultaneamente, separando-as por vírgulas.

Este resumo fornece uma visão geral da propriedade `transition` e suas principais características. Para mais detalhes e opções avançadas, consulte a documentação oficial do CSS.