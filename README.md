# Repositório de Estudos: HTML e CSS

Este repositório serve como um guia e registro dos meus estudos em HTML e CSS. Aqui estão compiladas minhas anotações, exemplos de código e os principais conceitos que aprendi, desde a estrutura básica de uma página web até estilizações mais avançadas.

## Estrutura dos Arquivos

O projeto está organizado da seguinte forma para manter o código limpo e de fácil manutenção:

```
/
|-- index.html       # Arquivo principal com a estrutura da página
|-- css/
|   |-- style.css    # Arquivo com todos os estilos da aplicação
|-- img/
    |-- (imagens)    # Pasta para armazenar as imagens do projeto
```

-----

## HTML: A Estrutura da Web

HTML (HyperText Markup Language) é a linguagem de marcação que define a estrutura e o conteúdo de uma página web.

### Estrutura Básica de um Documento

Todo arquivo HTML segue uma estrutura padrão:

  - `index.html`: É o nome de arquivo convencional para a página inicial de um site.
  - **Tags (`<>`)**: São os elementos que compõem o HTML.
  - `<head>`: Contém as configurações e metadados da página que não são visíveis para o usuário, como o título da aba (`<title>`), links para folhas de estilo (`<link>`) e scripts.
  - `<body>`: Contém todo o conteúdo visível da página, como textos, imagens e links.

### Tags Essenciais

| Tag                                 | Descrição                                                                       | Exemplo                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| `<h1>` a `<h6>`                       | Títulos de diferentes níveis de importância.                                      | `<h1>Título Principal</h1>`                                    |
| `<p>`                               | Define um parágrafo.                                                              | `<p>Este é um parágrafo.</p>`                                  |
| `<a href="">`                        | Cria um link (âncora). O `href` é um **atributo** que define o destino do link.  | `<a href="https://google.com">Acessar Google</a>`             |
| `<img src="" alt="">`               | Insere uma imagem. `src` define o caminho e `alt` fornece um texto alternativo.   | `<img src="img/foto.png" alt="Descrição da foto">`            |
| `<br>`                              | Quebra de linha (pula uma linha).                                                 | `Primeira linha.<br>Segunda linha.`                            |
| `<hr>`                              | Cria uma linha horizontal, usada para separar conteúdos.                          | `<hr>`                                                        |
| `<div>`                             | Um "contêiner" genérico usado para agrupar elementos e aplicar estilos em bloco.  | `<div><h3>Produto</h3><p>Descrição</p></div>`                |
| `<ul>`, `<ol>`, `<li>`                | `<ul>` (lista não ordenada), `<ol>` (lista ordenada) e `<li>` (item da lista).    | `<ul><li>Item 1</li></ul>`                                    |
| `<span>`                            | Um contêiner genérico em linha, usado para estilizar partes de um texto.          | `<p>Um texto com uma <span style="color:red;">palavra</span>.</p>` |
| `                      | Usado para adicionar comentários no código que não são exibidos na página.        | `                               |

-----

## CSS: O Estilo da Web

CSS (Cascading Style Sheets) é a linguagem utilizada para estilizar os elementos HTML, controlando cores, fontes, espaçamentos e layout.

### Formas de Adicionar CSS

1.  **CSS Inline (Não recomendado)**: Aplicado diretamente na tag HTML através do atributo `style`. É pouco prático para manutenção.
    ```html
    <p style="color: red;">Texto em vermelho.</p>
    ```
2.  **CSS Interno**: Declarado dentro da tag `<style>` no `<head>` do documento HTML. Útil para estilos específicos de uma única página.
    ```html
    <head>
        <style>
            h1 {
                color: purple;
            }
        </style>
    </head>
    ```
3.  **CSS Externo (Melhor prática)**: Criado em um arquivo separado (`.css`) e vinculado ao HTML através da tag `<link>` no `<head>`. É a forma mais organizada e reutilizável.
    ```html
    <head>
        <link rel="stylesheet" href="css/style.css" />
    </head>
    ```

### Seletores

Seletores são regras que definem quais elementos HTML serão estilizados.

  - **ID (`#`)**: É um identificador **único** para um elemento. Só pode haver um elemento com um determinado ID na página.
    ```css
    #titulo-principal {
        color: green;
    }
    ```
  - **Classe (`.`)**: É um identificador que **pode ser reutilizado** em vários elementos.
    ```css
    .paragrafo-destaque {
        font-weight: bold;
    }
    ```
  - **Combinado**: Você pode aplicar a mesma regra a múltiplos seletores, separando-os por vírgula.
    ```css
    h1, .titulo-secao {
        font-family: Arial;
    }
    ```

-----

## Conceitos Fundamentais de CSS

### Box Model

O Box Model é o conceito mais importante para o layout em CSS. Todo elemento HTML é uma caixa retangular composta por quatro partes:

1.  **Conteúdo**: O texto, imagem ou outro elemento.
2.  **Padding**: O espaçamento **interno**, entre o conteúdo e a borda.
3.  **Border**: A linha que fica ao redor do padding.
4.  **Margin**: O espaçamento **externo**, entre a borda do elemento e os elementos vizinhos.

<!-- end list -->

```css
.caixa-exemplo {
    width: 200px;         /* Largura do conteúdo */
    height: 100px;        /* Altura do conteúdo */
    padding: 20px;        /* Espaçamento interno */
    border: 3px solid red; /* Borda */
    margin: 30px;         /* Espaçamento externo */
    background-color: #f0f0f0;
}
```

### Propriedades de Estilo

#### Cores

As cores podem ser definidas de várias formas, sendo as mais comuns:

  - **Hexadecimal**: `#RRGGBB` (ex: `#FF5733`).
  - **RGB**: `rgb(red, green, blue)` (ex: `rgb(255, 87, 51)`).
  - **HSL**: `hsl(hue, saturation, lightness)` (ex: `hsl(10, 100%, 60%)`).

Esses formatos são mais flexíveis que os nomes de cores (`red`, `blue`), pois permitem total controle sobre a tonalidade.

#### Background (Fundo)

  - `background-color`: Define a cor de fundo de um elemento.
  - `background-image`: Define uma imagem como fundo.
    ```css
    .fundo-imagem {
        background-image: url("../img/minha-imagem.jpg");
    }
    ```

#### Bordas

  - `border`: Uma propriedade "shorthand" para definir a espessura, estilo (`solid`, `dashed`) e cor da borda.
  - `border-radius`: Arredonda os cantos da borda de um elemento.

#### Texto e Fontes

  - `text-align`: Alinha o texto (`left`, `center`, `right`).
  - `text-decoration`: Adiciona decoração (`underline`, `line-through`, `none`).
  - `text-transform`: Transforma o texto (`uppercase`, `lowercase`).
  - `font-size`: Define o tamanho da fonte.
  - `font-family`: Define o tipo da fonte (`Arial`, `Georgia`, `cursive`).

### Layout e Posicionamento

#### Display

A propriedade `display` controla como um elemento é exibido.

  - **`block`**: Ocupa toda a largura disponível e começa em uma nova linha (ex: `<p>`, `<div>`).
  - **`inline`**: Ocupa apenas o espaço necessário e não quebra a linha (ex: `<span>`, `<a>`).
  - **`inline-block`**: Comporta-se como um elemento `inline` (não quebra a linha), mas permite definir `width` e `height`, como um elemento `block`.
  - **`none`**: Oculta o elemento da página.

#### Position

A propriedade `position` define como um elemento é posicionado no documento.

  - **`static`**: Posição padrão. O elemento segue o fluxo normal da página.
  - **`relative`**: O elemento é posicionado em relação à sua posição normal. Pode ser movido com `top`, `right`, `bottom` e `left`.
  - **`absolute`**: O elemento é posicionado em relação ao ancestral posicionado mais próximo (ou ao `<body>` se não houver). Ele é removido do fluxo normal da página.
  - **`fixed`**: O elemento é posicionado em relação à janela do navegador (viewport). Ele permanece fixo mesmo quando a página é rolada.
