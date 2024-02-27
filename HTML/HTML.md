# HTML

# Sumário

<a name="item"></a>
1. [Tags & Attributes](#item1)
1.1. [Padrões no HTML](#item11)
1.2. [Tags & Meta Tags](#item12)
2. [Links & Images](#item2)
2.1. [Links](#item21)
2.2. [Images](#item22)
3. [Lists & Tables](#item3)
3.1. [Lists](#item31)
3.2. [Tables](#item32)
4. [Forms & Input](#item4)
5. [Block & Inline Elements](#item5)
5.1. [Block Elements](#item51)
5.2. [Inline Elements](#item52)
6. [Divs & Spans & Classes & Ids](#item6)
6.1. [Divs](#item61)
6.2. [Spans](#item62)
6.3. [Classes](#item63)
6.4. [Ids](#item64)
7. [Entities](#item7)

<a id="item1"></a>
## Tags & Attributes

Tags podem ser iniciadas e finalizadas por marcadores entre `<>`.

Tags podem não necessitar de final, ficando apenas com `<>` de início.

<a id="item11"></a>
### Padrões no HTML

O início de um arquivo html deve conter `<!DOCTYPE>` que especifica o tipo de documento que está sendo escrito e `<html>` que indica o início e fim do arquivo. A partir disso, títulos podem ser adicionados com `<title>` e o corpo do texto com `<body>`. 

Comentários podem ser adicionados com `<!-- -->`.

<a id="item12"></a>
### Tags & Meta Tags

Meta tags são tags que não aparecem na página, mas que são lidas pelo navegador. Elas podem ser usadas para especificar o tipo de codificação do arquivo, a descrição da página, palavras-chave, autor, etc.

Lista Completa de Meta Tags & Tags: Tags.md

<a id="item2"></a>
## Links & Images

<a id="item21"></a>
### Links

Links podem ser adicionados com `<a href="link">`.

A adição do parâmetro target= '_blank' faz com que o link seja aberto em uma nova aba.

Um link interno pode ser feito a partir da especificação de um caminho para o arquivo. Ex: `<a href="HTML/HTML.md">`.

<a id="item22"></a>
### Images

Imagens podem ser adicionadas com `<img src="link">`. Este link pode ser interno ou externo.

<a id="item3"></a>
## Lists & Tables

<a id="item31"></a>
### Lists

* Listas não ordenadas podem ser feitas com `<ul>` e `<li>`. Listas não ordenadas são marcadas com bolinhas.

* Listas ordenadas podem ser feitas com `<ol>` e `<li>`. Listas ordenadas são marcadas com números. Listas ordenadas podem ser numeradas com o parâmetro `type="1"`, `type="A"`, `type="a"`, etc.

<a id="item32"></a>
### Tables

Tabelas podem ser feitas com `<table>`, `<tr>`, `<td>`, `<th>`. `<table>` indica o início e fim da tabela. `<tr>` indica o início e fim de uma linha. `<td>` indica o início e fim de uma célula. `<th>` indica o início e fim de uma célula de cabeçalho.

<a id="item4"></a>
## Forms & Input

Formulários podem ser feitos com `<form>`, `<input>`, `<textarea>`, `<select>`, `<option>`, `<button>`, `<label>`, `<fieldset>`, `<legend>`, `<datalist>`, `<output>`, `<progress>`, `<meter>`, `<keygen>`, `<output>`.

<a id="item5"></a>
## Block & Inline Elements

<a id="item51"></a>
### Block Elements

Block elements são elementos que ocupam toda a largura da página. Ex: `<div>`, `<p>`, `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>`, `<header>`, `<footer>`, `<section>`, `<article>`, `<aside>`, `<nav>`, `<address>`, `<blockquote>`, `<canvas>`, `<dd>`, `<dl>`, `<dt>`, `<fieldset>`, `<figcaption>`, `<figure>`, `<hr>`, `<main>`, `<noscript>`, `<pre>`, `<video>`, `<audio>`, `<embed>`, `<iframe>`, `<object>`, `<script>`, `<source>`, `<style>`, `<title>`, `<track>`, `<map>`, `<area>`, `<time>`, `<meter>`, `<progress>`, `<output>`, `<datalist>`, `<keygen>`, `<ruby>`, `<rt>`, `<rp>`, `<bdi>`, `<bdo>`, `<wbr>`, `<details>`, `<summary>`, `<menu>`, `<menuitem>`, `<dialog>`, `<slot>`, `<template>`, `<acronym>`, `<applet>`, `<basefont>`, `<big>`, `<blink>`, `<center>`, `<command>`, `<content>`, `<dir>`, `<element>`, `<font>`, `<frame>`, `<frameset>`, `<image>`, `<isindex>`, `<listing>`, `<marquee>`, `<multicol>`, `<nextid>`, `<noembed>`, `<plaintext>`, `<shadow>`, `<spacer>`, `<strike>`, `<tt>`, `<xmp>`, `<base>`, `<body>`, `<head>`, `<html>`, `<meta>`, `<param>`, `<title>`.

<a id="item52"></a>
### Inline Elements

Inline elements são elementos que ocupam apenas o espaço necessário para o conteúdo. Ex: `<a>`, `<abbr>`, `<acronym>`, `<b>`, `<bdo>`, `<big>`, `<br>`, `<button>`, `<cite>`, `<code>`, `<dfn>`, `<em>`, `<i>`, `<img>`, `<input>`, `<kbd>`, `<label>`, `<map>`, `<object>`, `<output>`, `<q>`, `<samp>`, `<script>`, `<select>`, `<small>`, `<span>`, `<strong>`, `<sub>`, `<sup>`, `<textarea>`, `<time>`, `<tt>`, `<var>`, `<wbr>`, `<datalist>`, `<keygen>`, `<ruby>`, `<rt>`, `<rp>`, `<bdi>`, `<bdo>`, `<wbr>`, `<details>`, `<summary>`, `<menu>`, `<menuitem>`, `<dialog>`, `<slot>`, `<template>`, `<acronym>`, `<applet>`, `<basefont>`, `<big>`, `<blink>`, `<center>`, `<command>`, `<content>`, `<dir>`, `<element>`, `<font>`, `<frame>`, `<frameset>`, `<image>`, `<isindex>`, `<listing>`, `<marquee>`, `<multicol>`, `<nextid>`, `<noembed>`, `<plaintext>`, `<shadow>`, `<spacer>`, `<strike>`, `<tt>`, `<xmp>`, `<base>`, `<body>`, `<head>`, `<html>`, `<meta>`, `<param>`, `<title>`.

<a id="item6"></a>
## Divs & Spans Classes & Ids

<a id="item61"></a>
### Divs

Elemento de marcação utilizado para criar divisões ou seções em uma página web.

<a id="item62"></a>
### Spans

Elemento de marcação mais leve e não implica em quebras de linha.

<a id="item63"></a>
### Classes

Atributo que pode ser adicionado a elementos HTML para associá-los a uma ou mais classes CSS. Ex: `<p class="class">`.

<a id="item64"></a>
### Ids

Permite que esse elemento seja referenciado exclusivamente dentro de uma página webs. Ex: `<p id="id">`.

<a id="item7"></a>
## Entities

Entities são caracteres especiais que não podem ser usados diretamente no HTML. Ex: `&copy;` para ©.