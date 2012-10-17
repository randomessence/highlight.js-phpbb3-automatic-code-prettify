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

Help: if you code is being incorrectly detected use this code and specify a syntax or type `no-highlight`