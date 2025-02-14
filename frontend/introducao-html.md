# 📌 Introdução ao HTML

## O que é HTML?

- O `HyperText Markup Language` é a linguagem padrão utilizada para criar e estruturar conteúdo na web. A estrutura é composta por elementos comumente chamados de **tags**. Da mesma maneira que uma frase começa com letra maíuscula e termina com ponto final, no HTML as tags iniciam com `<tag>` e terminam com `</tag>`. Para iniciar uma seção, por exemplo, `<section> Hi lorena </section>`.

### Uso

- Definir títulos, parágrafos, listas, imagens, links, formulários, tabelas e muitos outros elementos (**tags**).
- A escolha correta dos elementos para cada parte da página irá facilitar o entendimento por outro desenvolvedor e também facilitará a acessibilidade por leitores de tela.

### Tags de bloco e inline

- Elementos de bloco iniciam em uma nova linha e ocupam todo o espaço do elemento pai por padrão. Ex: `<div>, <p>, <h1> até <h6>, <header>, <footer>, <section>, <article>.`
- Elementos inline, por padrão, não iniciam em uma nova linha e ocupam somente o espaço necessário para o seu conteúdo, permitindo que outros elementos fiquem na mesma linha. Ex: `<span>, <a>, <strong>, <em>, <img>`

### HTML semântico

- Algumas tags HTML são semânticas, ou seja, especificam a finalidade de cada parte da aplicação:
  - `<header>` - Funciona como cabeçalho da página. Contém informações como título, logotipo, informações introdutórias, menu de navegação.
  - `<nav>` - Utilizada para agrupar links de navegação e redirecionamento.
  - `<article>` - Empregado para encapsular conteúdos independentes e reutilizáveis separadamente do restante da página.
  - `<section>` - Utilizada para separar partes do conteúdo que possuem um tema ou próposito em comum, como "Sobre", "Serviços", "Depoimentos", entre outros.
  - `<footer>` - Identificando o rodapé, a tag `<footer>` oferece navegação secundária, dados institucionais, políticas de privacidade (ou qualquer outra) e dados para contato.
  - <p>Este é um texto com uma palavra <span style="color: red;">destacada</span> no meio.</p>
  ```html
  <p>Este é um texto com uma palavra <span style="color: red;">destacada</span> no meio.</p>
  ```

### Exemplo

```html
<!DOCTYPE html>

<html lang="pt">
  <head>
    <meta charset="UTF-8" />
    <title>Minha Página Web</title>
  </head>
  <body>
    <header>
      <h1>Bem-vindo ao meu site!</h1>
    </header>

    <nav>
      <ul>
        <li><a href="#inicio">Início</a></li>
        <li><a href="#sobre">Sobre</a></li>
        <li><a href="#contato">Contato</a></li>
      </ul>
    </nav>

    <main>
      <article>
        <h2>Introdução</h2>
        <p>Este é um exemplo básico de como estruturar uma página utilizando HTML.</p>
      </article>
    </main>

    <footer>
      <p>&copy; 2025 Meu Site. Todos os direitos reservados.</p>
    </footer>
  </body>
</html>
```

## Resumo das principais tags

### 🔹 Estrutura Básica da Página

- `<html>` → Define a raiz do documento HTML.
- `<head>` → Contém metadados como `<title>`, `<meta>`, `<link>`, `<script>`.
- `<body>` → Contém o conteúdo visível da página.

### 🔹 Cabeçalhos e Textos

- `<h1> ... <h6>` → Títulos e subtítulos (níveis de importância).
- `<p>` → Parágrafos de texto.
- `<span>` → Destacar uma parte do texto (inline).
- `<strong>` → Texto em **negrito** com importância semântica.
- `<em>` → Texto em _itálico_ com ênfase semântica.
- `<blockquote>` → Citação longa.
- `<cite>` → Referência a uma fonte.
- `<abbr>` → Abreviações e siglas (`title` para significado).

### 🔹 Listas

- `<ul>` → Lista não ordenada (com marcadores).
- `<ol>` → Lista ordenada (com números).
- `<li>` → Itens dentro de `<ul>` ou `<ol>`.
- `<dl>` → Lista de definição.
- `<dt>` → Termo a ser definido.
- `<dd>` → Descrição do termo.

### 🔹 Links e Navegação

- `<a>` → Link para outra página ou âncora interna (`href`).
- `<nav>` → Agrupa links de navegação.
- `<button>` → Botão clicável.

### 🔹 Imagens e Mídia

- `<img>` → Exibe imagens (`src` para URL, `alt` para descrição).
- `<figure>` → Agrupa imagem e legenda.
- `<figcaption>` → Legenda de uma imagem.
- `<audio>` → Adiciona áudio (`controls` para player).
- `<video>` → Adiciona vídeo (`controls` para player, `poster` para thumbnail).
- `<source>` → Define fontes alternativas para `<audio>` e `<video>`.

### 🔹 Tabelas

- `<table>` → Define uma tabela.
- `<tr>` → Linha da tabela.
- `<th>` → Célula de cabeçalho.
- `<td>` → Célula de dados.
- `<thead>` → Agrupa cabeçalho da tabela.
- `<tbody>` → Agrupa corpo da tabela.
- `<tfoot>` → Agrupa rodapé da tabela.

### 🔹 Formulários e Interação

- `<form>` → Agrupa campos de formulário.
- `<input>` → Campo de entrada (texto, senha, email, etc.).
- `<label>` → Define um rótulo para `<input>`.
- `<select>` → Caixa de seleção.
- `<option>` → Opções dentro de `<select>`.
- `<textarea>` → Área de texto maior.
- `<fieldset>` → Agrupa elementos do formulário.
- `<legend>` → Título do `<fieldset>`.

### 🔹 Estrutura e Layout

- `<header>` → Cabeçalho da página ou seção.
- `<footer>` → Rodapé da página ou seção.
- `<main>` → Conteúdo principal da página.
- `<section>` → Agrupa conteúdo relacionado.
- `<article>` → Conteúdo independente (post, notícia).
- `<aside>` → Conteúdo complementar (barras laterais).
- `<div>` → Agrupa elementos para estilização/layout.

### 🔹 Outros Elementos Úteis

- `<iframe>` → Incorporar páginas externas.
- `<script>` → Código JavaScript.
- `<noscript>` → Exibir conteúdo caso JavaScript esteja desativado.
- `<meta>` → Metadados da página (SEO, encoding).
- `<link>` → Conectar arquivos CSS e ícones.
- `<style>` → Definir CSS diretamente no HTML.
