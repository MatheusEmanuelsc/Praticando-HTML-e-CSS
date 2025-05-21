# 🧬 CSS Nesting – Resumo Completo

## 🧠 O que é CSS Nesting?

**Nesting** (aninhamento) é um recurso moderno do CSS que permite **aninhar seletores dentro de outros seletores**, semelhante ao que já era possível com pré-processadores como Sass ou Less.

Isso melhora a **organização e legibilidade** do CSS, agrupando regras relacionadas de forma hierárquica e clara.

---

## 🧪 Suporte nativo

> ✅ **CSS Nesting é suportado nativamente** em navegadores modernos com base no Chromium (Chrome, Edge) e Safari.  
> ⚠️ Firefox está implementando.

Verifique em: [https://caniuse.com/css-nesting](https://caniuse.com/css-nesting)

---

## 🔧 Como utilizar

### ✅ Sintaxe com `&` (recomendada)

```css
.card {
  padding: 1rem;
  background: white;

  & h2 {
    font-size: 1.5rem;
  }

  & .btn {
    background: blue;
    color: white;
  }

  &:hover {
    background: #f0f0f0;
  }
}
```

> O `&` representa o seletor pai no contexto atual.

---

### ✅ Sintaxe com blocos aninhados

Você também pode aninhar diretamente sem `&`, para tags internas:

```css
nav {
  ul {
    list-style: none;
    padding: 0;

    li {
      display: inline-block;

      a {
        text-decoration: none;
        color: black;

        &:hover {
          color: red;
        }
      }
    }
  }
}
```

---

## 📜 Regras do CSS Nesting

- O nesting **não pode ser arbitrário** — ele deve ser feito dentro de um seletor válido.
- Dentro de um bloco aninhado, o seletor pai deve ser representado por `&` se quiser reutilizá-lo.
- Pode ser usado com pseudo-classes (`:hover`, `:focus`) e combinadores (`>`, `+`, `~`).

---

## 📦 Exemplo Prático Completo

```css
.button {
  padding: 1rem;
  border: none;
  background-color: #333;
  color: white;

  &:hover {
    background-color: #555;
  }

  &.primary {
    background-color: blue;

    &:hover {
      background-color: darkblue;
    }
  }

  svg {
    margin-right: 0.5rem;
  }
}
```

---

## ✅ Vantagens

- 🔹 Código mais **limpo e legível**.
- 🔹 Organização **hierárquica** entre elementos relacionados.
- 🔹 Evita repetição de seletores pais (`.classe .subclasse`).

---

## ⚠️ Cuidados

- ❌ Não aninhar excessivamente (evite profundidade exagerada).
- ❌ Não usar nesting para tudo — apenas quando houver relação direta.
- ❌ Verifique **compatibilidade de navegadores** se estiver em produção.

---

## 📁 Exemplo com media queries

Você também pode aninhar media queries:

```css
.container {
  width: 100%;

  @media (min-width: 768px) {
    width: 750px;
  }
}
```

---

## ✅ Conclusão

O **CSS Nesting nativo** permite trazer o poder e organização dos pré-processadores diretamente para o CSS moderno, com **legibilidade, reutilização e hierarquia**.
