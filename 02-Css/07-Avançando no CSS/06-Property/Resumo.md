# 🎨 CSS `@property` – Resumo Completo

## 🧠 O que é `@property`?

A diretiva `@property` do CSS permite **registrar propriedades personalizadas (CSS Custom Properties)** com tipos, valores iniciais e comportamento animável.

Antes do `@property`, variáveis CSS (`--minha-var`) eram apenas valores estáticos (strings). Com `@property`, essas variáveis se tornam **tipadas e animáveis**, o que permite criar **animações suaves com `transition` ou `@keyframes`** em propriedades personalizadas.

---

## 🚀 Para que serve?

- **Permitir animações com `transition` usando variáveis CSS.**
- **Melhorar desempenho e previsibilidade com tipagem.**
- **Definir um valor padrão para propriedades personalizadas.**

---

## 🔧 Sintaxe

```css
@property --nome-da-propriedade {
  syntax: "<tipo>";
  inherits: true | false;
  initial-value: valor;
}
```

---

## 🧩 Explicação dos Campos

| Campo           | Descrição                                                                |
| --------------- | ------------------------------------------------------------------------ |
| `--nome`        | Nome da propriedade personalizada (obrigatoriamente começando com `--`). |
| `syntax`        | Define o tipo de valor que a propriedade aceita (ver tabela abaixo).     |
| `inherits`      | Define se a propriedade deve herdar valor do elemento pai.               |
| `initial-value` | Valor inicial padrão caso a variável não seja definida.                  |

---

## 🎛️ Tipos disponíveis em `syntax`

| Valor          | Aceita                               | Exemplo                   |
| -------------- | ------------------------------------ | ------------------------- |
| `<length>`     | unidades como `px`, `em`, `%`        | `10px`                    |
| `<number>`     | números sem unidade                  | `3.14`                    |
| `<color>`      | qualquer cor CSS                     | `#f00`, `rgba(0,0,0,0.5)` |
| `<percentage>` | porcentagens                         | `50%`                     |
| `<integer>`    | números inteiros                     | `5`                       |
| `<angle>`      | ângulos (`deg`, `rad`)               | `90deg`                   |
| `<time>`       | tempo (`s`, `ms`)                    | `0.3s`                    |
| `<image>`      | imagens como `url()` ou `gradient()` | `linear-gradient(...)`    |
| `*`            | qualquer valor                       | -                         |

---

## 📦 Exemplo Completo

```css
@property --my-color {
  syntax: "<color>";
  inherits: false;
  initial-value: red;
}

.box {
  --my-color: red;
  background-color: var(--my-color);
  transition: --my-color 1s;
}

.box:hover {
  --my-color: blue;
}
```

### ✅ Resultado:

A caixa muda de **vermelho para azul com transição suave**, mesmo sendo uma variável CSS — o que antes **não era possível**.

---

## ⚠️ Suporte dos Navegadores

- `@property` é suportado **apenas no Chromium (Chrome, Edge, Opera)** por enquanto.
- **Firefox e Safari ainda não implementaram** ou estão em fase experimental.
- Verifique: [https://caniuse.com/mdn-css_at-rules_property](https://caniuse.com/mdn-css_at-rules_property)

---

## 💡 Dicas de Uso

- Use `@property` para variáveis animáveis como cor, tamanho, espaçamento, rotação.
- Ideal para componentes com temas dinâmicos, botões, indicadores de progresso etc.
- Combine com `transition` ou `@keyframes` para efeitos avançados.
- Sempre forneça um `initial-value` para evitar valores `unset`.

---

## 🧪 Exemplo com `@keyframes`

```css
@property --rotate {
  syntax: "<angle>";
  inherits: false;
  initial-value: 0deg;
}

.spinner {
  --rotate: 0deg;
  transform: rotate(var(--rotate));
  animation: spin 2s linear infinite;
}

@keyframes spin {
  to {
    --rotate: 360deg;
  }
}
```

---

## ✅ Conclusão

`@property` é um avanço poderoso no CSS moderno, permitindo animações suaves com variáveis tipadas. Ele **expande o poder das Custom Properties**, tornando-as animáveis e previsíveis.

> ⚠️ Use com atenção em projetos reais, devido à limitação de suporte nos navegadores atuais.

---
