`````md
# 🎬 Atributo `kind` no HTML (`

<track>`)

## 📌 O que é?

O atributo `kind` é usado dentro da tag `

<track>` (usada em elementos `<video>` ou `<audio>`) para indicar **o tipo de faixa de texto** que está sendo adicionada
        ao conteúdo multimídia, como **legendas, capítulos, descrições ou metadados**.

        ---

        ## ✅ Onde usar?

        Você usa `
        <track>` dentro do elemento `<video>` ou `<audio>`, e define o tipo da faixa com o atributo `kind`.

                ### Exemplo básico:

                ```html
                <video controls width="600">
                    <source src="filme.mp4" type="video/mp4">
                    <track src="legendas.vtt" kind="subtitles" srclang="pt" label="Português">
                </video>
                ````

                ---

                ## 📄 Valores possíveis de `kind`

                | Valor | Descrição |
                | -------------- |
                ------------------------------------------------------------------------------------------- |
                | `subtitles` | Mostra **legendas traduzidas**, sem duplicar falas no idioma original. |
                | `captions` | Mostra **tudo que é falado e ouvido** (diálogos, sons, efeitos). Usado para
                acessibilidade. |
                | `descriptions` | Faixa de **descrições visuais** para deficientes visuais (narrações do que acontece).
                |
                | `chapters` | Divide o vídeo em **capítulos navegáveis**. |
                | `metadata` | **Informações não exibidas**, mas acessíveis via JavaScript (ex: tags ocultas,
                marcadores). |

                ---

                ## 🧪 Exemplo com várias faixas `
                <track>`

                ```html
                <video controls width="600">
                    <source src="filme.mp4" type="video/mp4">

                    <!-- Legendas traduzidas -->
                    <track src="legenda-pt.vtt" kind="subtitles" srclang="pt" label="Português">

                    <!-- Legendas completas para acessibilidade -->
                    <track src="captions-en.vtt" kind="captions" srclang="en" label="English Captions" default>

                    <!-- Capítulos do vídeo -->
                    <track src="capitulos.vtt" kind="chapters" srclang="pt" label="Capítulos">

                    <!-- Metadados ocultos -->
                    <track src="infos.vtt" kind="metadata" label="Meta info">
                </video>
                ```

                ---

                ## 📂 Sobre arquivos `.vtt` (WebVTT)

                As faixas de texto geralmente são arquivos `.vtt`, com o seguinte formato:

                ```vtt
                WEBVTT

                00:00:01.000 --> 00:00:04.000
                Olá, bem-vindo ao vídeo!

                00:00:05.000 --> 00:00:07.000
                Este é um exemplo de legenda.
                ```

                ---

                ## 💡 Dicas

                * Use vários `
                <source>` para compatibilidade entre navegadores (mp4, webm, ogg).
                * O atributo `default` pode ser usado para ativar uma faixa automaticamente.
                * As faixas `metadata` não são exibidas na tela, mas podem ser lidas com JavaScript.
                * Para **acessibilidade**, sempre ofereça `captions` junto ao conteúdo de vídeo.

                ---

                Se quiser, posso complementar esse resumo com um exemplo prático interativo ou adicionar um guia para
                criar arquivos `.vtt`. Deseja?

                ```
`````
