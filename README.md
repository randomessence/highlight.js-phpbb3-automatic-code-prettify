highlight.js-phpbb3-automatic-code-prettify
===========================================

this is a mod using [highlight.js](http://softwaremaniacs.org/soft/highlight/en/) to automatically detect syntax and prettify code. it's awesome.

How does it work? well so far it laods the scripts into the overall header and with the use of a simple bbcode will detect, identify and [54 languages and is bundled with 26 style themes.](http://softwaremaniacs.org/media/soft/highlight/test.html)


BBcodes:

Standar highlighting with automatic detection and prettifying. 

`[highlight]{TEXT}[/highlight]`

`<pre><code>{TEXT}</code></pre>`

**If you are getting a bad match use this custom code.**


`[highlight={SIMPLETEXT}]{TEXT}[/highlight]`

`<pre><code class="{SIMPLETEXT}">{TEXT}</code></pre>`

**Help:** if you code is being incorrectly detected use this code and specify a syntax or type `no-highlight` in this way `[highlight=no-highlight]thsi code[/highlight]`


##Notes

This mod can be made to automatically detect and prettify code used in the stock bbcode `[code]` tag. Sadly there are some pre requisites to make this work.

this mod must be installed from phpbb.com.  [code enhancements](https://www.phpbb.com/customise/db/mod/code_enhancements/)

then 2 edits are required to complete this.

open the `prosilver/template/bbcode.html` and find

```html
<!-- BEGIN code_open --><dl class="codebox"><dt>{L_CODE}: <a href="#" onclick="selectCode(this); return false;">{L_SELECT_ALL_CODE}</a></dt><dd><pre><!-- END code_open -->
<!-- BEGIN code_close --></pre></dd></dl><!-- END code_close -->
```

and replace it with

```html
<!-- BEGIN code_open --><dl class="codebox"><dt>{L_CODE}: <a href="#" onclick="selectCode(this); return false;">{L_SELECT_ALL_CODE}</a></dt><dd><pre><code><!-- END code_open -->
<!-- BEGIN code_close --></code></pre></dd></dl><!-- END code_close -->
```

the open the `prosilver/template/forum_fn.js` and find

`	var e = a.parentNode.parentNode.getElementsByTagName('PRE')[0];`

replace it with

`	var e = a.parentNode.parentNode.getElementsByTagName('CODE')[0];`


the first edit makes it so all code is detected and prettifed in stock tags + fixes from the mod we installed.

the second edit it jsut to the Select all feature works again if you remove `highlight.js from the `overall+header.html`