---

---
-- -

### Introdução


*HTML* é uma linguagem de marcação usada para construção da estrutura de páginas web. Para a execução de um código fonte HTML é necessário um **editor de texto** e um **browser**.

Ao contrário de linguagens de programação, o HTML **não executa lógica** ou comandos, mas **organiza e define a hierarquia** dos elementos de uma página, como títulos, parágrafos, links, imagens, listas, tabelas e formulários.

O HTML funciona em conjunto com outras tecnologias:

- [[CSS (Cascading Style Sheets)]] (Cascading Style Sheets): define o estilo e layout visual.
- [[JavaScript]]: adiciona interatividade e comportamento dinâmico.

-- -
### Estrutura Base


A estrutura básica de um documento HTML é dado da seguinte forma:

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8">
    <title>Minha Página</title>
  </head>
  <body>
    <h1>Olá, mundo!</h1>
  </body>
</html>
```

**Explicação:**

-  `<!DOCTYPE html>`:  declara que é um documento HTML5.
-  `<html>`:  raiz da página.
-  `<head>`:  configurações, título, metadados.
-  `<body>`:  onde fica o conteúdo visível da página.

-- -
### Tags


A estrutura HTML é composta por **elementos (ou "tags")**, que indicam ao navegador como exibir o conteúdo. Esses elementos são geralmente escritos em pares, com uma **tag de abertura** (`<tag>`) e uma **tag de fechamento** (`</tag>`), envolvendo o conteúdo a ser representado.

> Algumas das principais tags utilizadas comumente são:


📄 ***Estrutura e Texto***

| Tag             |     | Função                                              |
| :-------------- | :-- | :-------------------------------------------------- |
|                 |     |                                                     |
| `<h1>` a `<h6>` |     | Títulos de diferentes níveis (h1 = mais importante) |
| `<p>`           |     | Parágrafo                                           |
| `<br>`          |     | Quebra de linha                                     |
| `<hr>`          |     | Linha horizontal (divisor)                          |
| `<strong>`      |     | Texto em negrito (ênfase forte)                     |
| `<em>`          |     | Texto em itálico (ênfase leve)                      |
| `<span>`        |     | Conteúdo inline (usado com CSS)                     |
| `<div>`         |     | Bloco genérico (usado para estrutura e CSS)         |


🔗 ***Links e Imagens***

| Tag                                      |     | Função                          |
| ---------------------------------------- | --- | ------------------------------- |
|                                          |     |                                 |
| `<a href="url">`                         |     | Cria um **link** clicável       |
| `<img src="imagem.jpg" alt="Descrição">` |     | Insere uma **imagem** na página |


📋 ***Listas***

| Tag    |     | Função                                           |
| ------ | --- | ------------------------------------------------ |
|        |     |                                                  |
| `<ul>` |     | Lista não ordenada (com marcadores)              |
| `<ol>` |     | Lista ordenada (numerada)                        |
| `<li>` |     | Item de lista (usado dentro de `<ul>` ou `<ol>`) |


📄 ***Tabelas***

| Tag       |     | Função              |
| --------- | --- | ------------------- |
|           |     |                     |
| `<table>` |     | Cria uma tabela     |
| `<tr>`    |     | Linha da tabela     |
| `<td>`    |     | Célula comum        |
| `<th>`    |     | Célula de cabeçalho |


🧾 ***Formulários***

| Tag                     |     | Função               |
| ----------------------- | --- | -------------------- |
|                         |     |                      |
| `<form>`                |     | Define um formulário |
| `<input>`               |     | Entrada de dados     |
| `<label>`               |     | Rótulo de campo      |
| `<textarea>`            |     | Área de texto longa  |
| `<button>`              |     | Botão                |
| `<select>` e `<option>` |     | Lista suspensa       |

#### Atributos

Em HTML, atributos são palavras especiais dentro de uma tag de abertura que modificam o comportamento, a aparência ou a funcionalidade de um elemento HTML. Eles fornecem informações adicionais sobre o elemento e são essenciais para definir como ele se comporta na página.

A seguir, são apresentados alguns dos principais atributos utilizados:


📝 ***Atributos Globais (presentes em quase todas as tags)***

| Atributo          |     | Função                                                         |
| ----------------- | --- | -------------------------------------------------------------- |
|                   |     |                                                                |
| `id`              |     | Identificador único para o elemento. Usado com CSS/JS.         |
| `class`           |     | Nome de classe. Pode ser compartilhado entre vários elementos. |
| `style`           |     | Estilo inline CSS direto na tag.                               |
| `title`           |     | Texto de dica (tooltip) ao passar o mouse.                     |
| `hidden`          |     | Oculta o elemento da página.                                   |
| `tabindex`        |     | Define a ordem de navegação com Tab.                           |
| `contenteditable` |     | Permite edição do conteúdo diretamente na página.              |


🎯 ***Atributos por Tag***


-  `<a>` (links) :

| Atributo |     | Função                                                                   |
| -------- | --- | ------------------------------------------------------------------------ |
|          |     |                                                                          |
| `href`   |     | Endereço do link. Pode ser URL ou âncora (`#id`).                        |
| `target` |     | Define onde abrir o link: `_blank` (nova aba), `_self` (mesma aba), etc. |
| `rel`    |     | Indica a relação do link com a página (ex: `noopener`, `nofollow`).      |


-  `<img>` (imagens) :

| Atributo           |     | Função                                      |
| ------------------ | --- | ------------------------------------------- |
|                    |     |                                             |
| `src`              |     | Caminho da imagem.                          |
| `alt`              |     | Texto alternativo (acessibilidade).         |
| `width` / `height` |     | Define dimensões da imagem (em px, %, etc). |
| `loading`          |     | Pode ser `lazy` para carregar sob demanda.  |


-  `<input>` (campos de formulário) :

| Atributo      |     | Função                                                            |
| ------------- | --- | ----------------------------------------------------------------- |
|               |     |                                                                   |
| `type`        |     | Tipo de entrada (ex: `text`, `email`, `number`, `password`, etc). |
| `name`        |     | Nome do campo (usado para envio dos dados).                       |
| `value`       |     | Valor padrão do campo.                                            |
| `placeholder` |     | Texto de sugestão (dentro do campo).                              |
| `required`    |     | Torna o campo obrigatório.                                        |
| `disabled`    |     | Desabilita o campo.                                               |
| `readonly`    |     | Campo somente leitura.                                            |
| `maxlength`   |     | Número máximo de caracteres.                                      |


-  `<form>` :

| Atributo       |     | Função                                              |
| -------------- | --- | --------------------------------------------------- |
|                |     |                                                     |
| `action`       |     | URL de destino para onde o formulário será enviado. |
| `method`       |     | Método HTTP (`get` ou `post`).                      |
| `autocomplete` |     | Liga/desliga preenchimento automático.              |


-  `<button>` :

| Atributo         |     | Função                                  |
| ---------------- | --- | --------------------------------------- |
|                  |     |                                         |
| `type`           |     | Pode ser `submit`, `reset` ou `button`. |
| `disabled`       |     | Desativa o botão.                       |
| `name` / `value` |     | Enviam dados junto com o formulário.    |


-  `<label>` :

| Atributo |     | Função                                                                              |
| -------- | --- | ----------------------------------------------------------------------------------- |
|          |     |                                                                                     |
| `for`    |     | ID do `<input>` que o rótulo representa. Permite que clique no texto ative o campo. |


-  `<script> / <link>` :

| Atributo          |     | Função                                                  |
| ----------------- | --- | ------------------------------------------------------- |
|                   |     |                                                         |
| `src`             |     | Caminho para um script JS.                              |
| `href`            |     | Caminho para um CSS externo.                            |
| `type`            |     | Tipo MIME (geralmente `text/javascript` ou `text/css`). |
| `rel`             |     | Tipo de relação (ex: `stylesheet`).                     |
| `async` / `defer` |     | Modo de carregamento de scripts JS.                     |


-  `<meta>` :

| Atributo  |     | Função                                            |
| --------- | --- | ------------------------------------------------- |
|           |     |                                                   |
| `charset` |     | Codificação da página (ex: `UTF-8`).              |
| `name`    |     | Nome do metadado (ex: `viewport`, `description`). |
| `content` |     | Conteúdo do metadado.                             |

#### Tag `<div></div>`

A tag é uma caixa genérica de bloco usada para agrupar elementos e aplicar estilos ou scripts. É muito usada com [[CSS (Cascading Style Sheets)]] para montar o layout da página.


🎯 ***Para que serve?***

| Uso comum         |     | Exemplo                             |
| ----------------- | --- | ----------------------------------- |
|                   |     |                                     |
| Agrupar conteúdos |     | `<div>Texto + imagem</div>`         |
| Criar layouts     |     | `<div class="coluna-esquerda">`     |
| Aplicar CSS       |     | `.menu { background-color: blue; }` |
| Interações JS     |     | `<div id="modal">`                  |
