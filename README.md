---
title: |
  CSS Notes for Professionals
  by web@petercv.com, PDF https://goalkicker.com/CSSBook
author: "bbauska"
date last editted: "7/6/2024 Sat 3+am"
output: 
  markdown:
    with some style
---

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>CSS-Notes4Pros</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS Notes For Professionals - intermediate level CSS learning course.  
All on-line.  No money, unless you'd like to donate. I'm game for that.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1 align="center">Advanced CSS Notes for Professionals</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h6 align="center">(by web@petercs.com, lecturer - PDF @https://goalkicker.com)</h6>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~ readme.md of CSS Advanced - Notes for Professionals ~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ CSS-Notes4Pros.bauska.github.io ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 01/02. javascript/css logos (01) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image001.jpg"
  style="width:20%"
  title="JavaScript coffee cup logo version"
  alt="JavaScript coffee cup logo version." />
<img src="./images/image002.jpg"
  style="width:20%"
  title="CSS logo"
  alt=" logo." />
</p>

<h2 id="about">About</h2>

<p align="center">Please feel free to share this Advanced CSS website with anyone, latest
version of this book can be downloaded from:<br>
<a href="https://goalkicker.com/CSSBook">Advanced CSS Book</a>.</p>

<p align="center">This <i>CSS Notes for Professionals</i> book is compiled from 
<a href="https://archive.org/details/documentation-dump.7z">Stack Overflow 
Documentation</a>, the content is written by the beautiful people at Stack Overflow.<br/>
Text content is released under Creative Commons BY-SA, see credits at
the end of this book whom contributed to the various chapters. Images
may be copyright of their respective owners unless otherwise specified.</p>

<p align="center">This is an unofficial free book created for educational purposes and
is not affiliated with official CSS group(s) or company(s) nor Stack
Overflow. All trademarks and registered trademarks are the property of
their respective company owners.</p>

<p align="center">The information presented in this book is not guaranteed to be correct
nor accurate, use at your own risk.</p>

<p align="center">Please send feedback and corrections to <a href="web@petercv.com">web@petercv.com</a></p>
<!-- page 2 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch1">Chapter 1: Getting started with CSS</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-1">Section 1.1: External Stylesheet</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>An external CSS stylesheet can be applied to any number of HTML
documents by placing a <b>&lt;link&gt;</b> element in each HTML document.</p>

<p>The attribute rel of the <b>&lt;link&gt;</b> tag has to be set to &quot; $\color{red}{stylesheet}$ &quot;,
and the href attribute to the relative or absolute path to the
stylesheet. While using relative URL paths is generally considered
good practice, absolute paths can be used, too. In HTML5 the type
attribute <a href="https://html.spec.whatwg.org/multipage/semantics.html#the-link-element">
can be omitted</a>.</p>

<p>It is recommended that the <b>&lt;link&gt;</b> tag be placed in the HTML file's <b>&lt;head&gt;</b>
tag so that the styles are loaded before the elements they style.
Otherwise, <a href="http://stackoverflow.com/a/1642259/2397327"> 
users will see a flash of unstyled content</a>.</p>

<h4>Example</h4>
<h4>hello-world.html</h4>

<pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;meta charset="utf-8"/&gt;
    &lt;link rel="stylesheet" type="text/css" href="style.css"&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;Hello world!&lt;/h1&gt;
    &lt;p&gt;I ♥ CSS&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre>

<h4>style.css</h4>

<pre><code>h1 {
  color: green;
  text-decoration: underline;
}

p {
  font-size: 25px;
  font-family: 'Trebuchet MS', sans-serif;
}
</code></pre>

<p>Make sure you include the correct path to your CSS file in the href.
If the CSS file is in the same folder as your HTML file then no path
is required (like the example above) but if it's saved in a folder,
then specify it like this;<br>
href="foldername/style.css"</p>

<pre><code>&lt;link rel="stylesheet" type="text/css" href="foldername/style.css"&gt;</code></pre>

<p>External stylesheets are considered the best way to handle your CSS.
There&apos;s a very simple reason for this: when you&apos;re managing a site
of, say, 100 pages, all controlled by a single stylesheet, and you
want to change your link colors from blue to green, it&apos;s a lot easier
to make the change in your CSS file and let the changes &quot;cascade&quot;
throughout all 100 pages than it is to go into 100 separate pages and
make the same change 100 times. Again, if you want to completely
change the look of your website, you only need to update this one
file.</p>
<!-- 6 lines up at 'colors from blue to green' - begin pg 3 -->
<p>You can load as many CSS files in your HTML page as needed.</p>

<pre><code>&lt;link rel="stylesheet" type="text/css" href="main.css"&gt;
&lt;link rel="stylesheet" type="text/css" href="override.css"&gt;</code></pre>

<p>CSS rules are applied with some basic rules, and order does matter.
For example, if you have a main.css file with some code in it:</p>

<pre><code>p.green { color: #00ff00; }</code></pre>

<p>All your paragraphs with the &apos;green&apos; class will be written in light
green, but you can override this with another .css file just by
including it *after* main.css. You can have override.css with the
following code follow main.css, for example:</p>

<pre><code>p.green { color: #006600; }</code></pre>

<p>Now all your paragraphs with the &apos;green&apos; class will be written in
darker green rather than light green.</p>

<p>Other principles apply, such as the &apos;!important&apos; rule, specificity,
and inheritance.</p>

<p>When someone first visits your website, their browser downloads the
HTML of the current page plus the linked CSS file. Then when they
navigate to another page, their browser only needs to download the
HTML of that page; the CSS file is cached, so it does not need to be
downloaded again. Since browsers cache the external stylesheet, your
pages load faster.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-2">Section 1.2: Internal Styles</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS enclosed in <b>&ltstyle&gt;&lt;/style&gt;</b> tags within an HTML document 
function like an external stylesheet, except that it lives in the HTML document it
styles instead of in a separate file, and therefore can only be applied to the 
document in which it lives. Note that this element <i>must</i> be inside the 
<b>&lt;head&gt;</b> element for HTML validation (though it
will work in all current &lt;head&gt; browsers if placed in body).</p>

<pre><code>&lt;head&gt;
  &lt;style&gt;
    h1 {
      color: green;
      text-decoration: underline;
    }
    p {
      font-size: 25px;
      font-family: 'Trebuchet MS', sans-serif;
    }
  &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;h1&gt;Hello world!&lt;/h1&gt;
  &lt;p&gt;I ♥ CSS&lt;/p&gt;
&lt;/body&gt;
</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-3">Section 1.3: CSS &commat;import rule (one of CSS at-rule)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 4 -->
<p>The &commat;import CSS at-rule is used to import style rules from other style 
sheets. These rules must precede all other types of rules, except &commat;charset 
rules; as it is not a nested statement, &commat;import cannot be used inside 
conditional group at-rules <a href="https://developer.mozilla.org/en/docs/Web/CSS/@import">&commat;import</a>.

<h4>How to use &commat;import</h4>

<p>You can use &commat;import rule in the following ways:</p>

A.  <b>With internal style tag</b>

<pre><code>  <style>
    @import url('/css/styles.css');
  </style></code></pre>

B.  <b>With external stylesheet</b>

<p>The following line imports a CSS file named additional-styles.css in
the root directory into the CSS file in which it appears:</p>

<pre><code>@import '/additional-styles.css';</code></pre>

<p>Importing external CSS is also possible. A common use case are font
files.</p>

<pre><code>@import 'https://fonts.googleapis.com/css?family=Lato';</code></pre>

<p>An optional second argument to &commat;import rule is a list of media
queries:</p>

<pre><code>@import '/print-styles.css' print;
@import url('landscape.css') screen and (orientation: landscape);</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-4">Section 1.4: Inline Styles</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Use inline styles to apply styling to a specific element. Note that
this is <b><i>not</i></b> optimal. Placing style rules in a <b>&lt;style&gt;</b> tag or
external CSS file is encouraged in order to maintain a distinction
between content and presentation.</p>

<p>Inline styles override any CSS in a <b>&lt;style&gt;</b> tag or external style
sheet. While this can be useful in some circumstances, this fact more
often than not reduces a project&apos;s maintainability.</p>

<p>The styles in the following example apply directly to the elements to
which they are attached.</p>

<pre><code>&lt;h1 style="color: green; text-decoration: underline;"&gt;Hello world!&lt;/h1&gt;
&lt;p style="font-size: 25px; font-family: 'Trebuchet MS';"&gt;I ♥ CSS&lt;/p&gt;</code></pre>

<p>Inline styles are generally the safest way to ensure rendering
compatibility across various email clients, programs and devices, but
can be time-consuming to write and a bit challenging to manage.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="#ch1-5">Section 1.5: Changing CSS with JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Pure JavaScript</h4>

<p>It&apos;s possible to add, remove or change CSS property values with JavaScript 
through an element&apos;s style property.</p>
<!-- page 5 -->
<pre><code>var el = document.getElementById("element");
el.style.opacity = 0.5;
el.style.fontFamily = 'sans-serif';</code></pre>

<p>Note that style properties are named in lower camel case style. In the
example you see that the css property fontfamily becomes fontFamily in
javascript.</p>

<p>As an alternative to working directly on elements, you can create a 
<b>&lt;style&gt;</b> or <b>&lt;link&gt;</b> element in JavaScript and append it 
to the <b>&lt;body&gt;</b> or <b>&lt;head&gt;</b> of the HTML document.</p>

<h4>jQuery</h4>

<p>Modifying CSS properties with jQuery is even simpler.</p>

<pre><code>$('#element').css('margin', '5px');</code></pre>

<p>If you need to change more than one style rule:</p>

<pre><code>$('#element').css({
  margin:"5px",
  padding:"10px",
  color:"black"
});</code></pre>

<p>jQuery includes two ways to change css rules that have hyphens in them
(i.e. font-size). You can put them in quotes or camel-case the style
rule name.</p>

<pre><code>$('.example-class').css({
  "background-color": "blue", 
  fontSize: "10px" 
});</code></pre>

<h4>See also;</h4>

<ul>
  <li>JavaScript documentation - Reading and Changing CSS Style.</li>
  <li>jQuery documentation - CSS Manipulation</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-6">Section 1.6: Styling Lists with CSS</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>There are three different properties for styling list-items:
list-style-type, list-style-image, and list-style position, which
should be declared in that order. The default values are disc,
outside, and none, respectively. Each property can be declared
separately, or using the list-style shorthand property.</p>

<p><b>list-style-type</b> defines the shape or type of bullet point used for each list-item.</p>
<p>Some of the acceptable values for list-style-type:</p>

<ul>
  <li>disc</li>
  <li>circle</li>
  <li>square</li>
  <li>decimal</li>
  <li>lower-roman</li>
  <li>upper-roman</li>
  <li>none</li>
</ul>

<p>(For an exhaustive list, see the 
<a href="https://www.w3.org/wiki/CSS/Properties/list-style-type">W3C specification WIKI</a>).</p>
<!-- page 6 -->
<p>To use square bullet points for each list-item, for example, you would use 
the following property-value pair:</p>

<pre><code>li {
  list-style-type: square;
}</code></pre>

<p>The <b>list-style-image</b> property determines whether the list-item
icon is set with an image, and accepts a value of none or a URL that
points to an image.</p>

<pre><code>li {
  list-style-image: url (images/bullet.png);
}</code></pre>

<p>The <b>list-style-position</b> property defines where to position the
list-item marker, and it accepts one of two values: &quot;inside&quot; or
&quot;outside&quot;.</p>

<pre><code>li {list-style-position: inside;
}</code></pre>
<!-- page 7 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch2">Chapter 2: Structure and Formatting of a CSS Rule</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-1">Section 2.1: Property Lists</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Some properties can take multiple values, collectively known as a
<b>property list</b>.

<pre><code>/* Two values in this property list */
span {
  text-shadow: yellow 0 0 3px, green 4px 4px 10px;
}

/* Alternate Formatting */
span {
  text-shadow:
    yellow 0 0 3px,
    green 4px 4px 10px;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-2">Section 2.2: Multiple Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When you group CSS selectors, you apply the same styles to several
different elements without repeating the styles in your style sheet.
Use a comma to separate multiple grouped selectors.</p>

<pre><code>div, p {color: blue }</code></pre>

<p>So the blue color applies to all <b>&lt;div&gt;</b> elements and all <b>&lt;p&gt;</b>
elements.  Without the comma only <b>&lt;p&gt;</b> elements that are a child of 
a <b>&lt;div&gt;</b> would be red.</p>

<p>This also applies to all types of selectors.</p>

<pre><code>p, .blue, #first, div span{ color : blue }</code></pre>

<p>This rule applies to:</p>

<ul>
  <li><b>&lt;p&gt;</b></li>
  <li>elements of the blue class</li>
  <li>element with the ID first</li>
  <li>every <b>&lt;span&gt;</b> inside of a <b>&lt;div&gt;</b>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-3">Section 2.3: Rules, Selectors, and Declaration Blocks</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A CSS <b>rule</b> consists of a <b>selector</b> (e.g. h1) and <b>declaration block</b> ({}).

<pre><code>h1 {}</code></pre>
<!-- page 8 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3">Chapter 3: Comments</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-1">Section 3.1: Single Line</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>/* This is a CSS comment */
div {
  color: red; /* This is a CSS comment */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-2">Section 3.2: Multiple Line</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>/*
  This
  is
  a
  CSS
  comment
*/
div {
  color: red;
}</code></pre>
<!-- page 9 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4">Chapter 4: Selectors</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS selectors identify specific HTML elements as targets for CSS
styles. This topic covers how CSS selectors target HTML elements.
Selectors use a wide range of over 50 selection methods offered by the
CSS language, including elements, classes, IDs, pseudo-elements and
pseudo-classes, and patterns.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-1">Section 4.1: Basic selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| Selector     | Description                                         |
|--------------|-----------------------------------------------------|
|  &ast;       | Universal selector (all elements) |
|  div           | Tag selector (all <b>&lt;div&gt;</b> elements) |
|  .blue       | Class selector (all elements with class blue) |
|  .blue.red   | All elements with class blue and red (a type of Compound selector) |
|  #headline   | ID selector (the element with "id" attribute set to headline) |
|  :pseudo-class | All Elements with pseudo-class |
|  ::pseudo-element | Element that matches pseudo-element |
|  :lang(en)        | Element that matches :lang declaration, for example <b>&lt;span lang="en"&gt;</b> |
|  div &gt; p            | child selector |
  
<blockquote>
  <b>Note:</b> The value of an ID must be unique in a web page. It is a
  violation of the <a href="https://www.w3.org/TR/html/dom.html#the-id-attribute">
  HTML standard</a> to use the value of an ID more than once in the same document tree.
</blockquote>

<p>A complete list of selectors can be found in the 
<a href="https://www.w3.org/TR/css3-selectors/#selectors">CSS Selectors Level
3 specification</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-2">Section 4.2: Attribute Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Overview:</h4>

<p>Attribute selectors can be used with various types of operators that
change the selection criteria accordingly. They select an element
using the presence of a given attribute or attribute value.</p>

| Selector(1)     | Matched element            | Selects elements...                |
|----------------:|----------------------------|------------------------------------|
| &lbrack;attr&rbrack;          | &lt;div attr&gt;                 | With attribute attr                |
| &lbrack;attr='val'&rbrack;    | &lt;div attr="val"&gt;           | Where attribute attr has value val |
| &lbrack;attr~='val'&rbrack;   | &lt;div attr="val val2 val3"&gt; | Where val appears in the           |
|                 |                            | whitespace-separated list of attr  |
| &lbrack;attr^='val'&rbrack;   | &lt;div attr="val1 val2"&gt;     | Where attr's value begins with val |
| &lbrack;attr$='val'&rbrack;   | &lt;div attr="sth aval"&gt;      | Where attr's value ends with val   |
| &lbrack;attr&ast;='val'&rbrack;    | &lt;div attr="somevalhere"&gt;   | Where attr contains val anywhere   |
| &lbrack;attr&vert;='val'&rbrack;   | &lt;div attr="val-sth etc"&gt;   | Where attr's value is exactly val, |
|                 |                            | or starts with val and immediately |
|                 |                            | followed by - (U+002D) |
| &lbrack;attr&vert;='val' i&rbrack; | &lt;div attr="val"&gt;           | Where attr has val, |
|                 |                            | ignoring val's letter casing. |

<b>Notes:</b>

1.  The attribute value can be surrounded by either single-quotes or
    double-quotes. No quotes at all may also work, but it&apos;s not valid
    according to the CSS standard, and is discouraged.
<!-- page 10 -->
2.  There is no single, integrated CSS4 specification, because it is
    split into separate modules. However, there are &quot;level 4&quot; modules.
    <a href="http://caniuse.com/#feat=css-case-insensitive">See browser support</a>.

<h4>Details<br>
&lbrack;<b>attribute</b>&rbrack;</h4>

<p>Selects elements with the given attribute.</p>

<pre><code>div&lbrack;data-color&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div data-color="red"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-color="green"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-background="red"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/cezale/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value.</p>

<pre><code>div&lbrack;data-color="red"&rbrack; {
  <b>color</b>: red;
  }

<b>&lt;div data-color="red"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-color="green"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-background="blue"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/waxoked/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute*="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute contains the given value anywhere (as a substring).</p>

<pre><code>&lbrack;class*= "foo"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="foo-123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foo123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="bar123foo"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="barfooo123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="barfo0"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/dazige/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute~="value"</b>&rbrack;</pre></code>

<p>Selects elements with the given attribute and value where the given
value appears in a whitespace-separated list.</p>

<pre><code>&lbrack;class~="color-red"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="color-red foo-bar the-div"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="color-blue" foo-bar the-div"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>
<!-- page 11 -->
<a href="http://jsbin.com/posuhim/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute^="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute begins with the value.</p>

<pre><code>&lbrack;class^="foo-"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-input"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute$="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute ends with the given value.</p>

<pre><code>&lbrack;class$="file"&rbrack; {
  <b>color</b>: red;
}
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-input"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/2/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute&vert;="value"</b>&rbrack;</code></pre>

<p>Selects elements with a given attribute and value where the
attribute&apos;s value can be represented as Value, VALUE, vAlUe 
or any other case-sensitive possibility.</p>

<pre><code>&lbrack;lang&vert;="<b>EN</b>" i&rbrack; {
  <b>color</b>: red;
  }
<b>&lt;div lang="EN-us"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="EN-gb"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="PT-pt"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/3/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute</b>=<b>"value" i</b>&rbrack;</code></pre>

<p>Selects elements with a given attribute and value where the
attribute&apos;s value can be represented as Value, VALUE, vAlUe or any
other case-insensitive possibility.</p>

<pre><code>&lbrack;lang|=<b>"EN"</b>&rbrack; {
  <b>color</b>: red;
}
<b>&lt;div lang="EN-us"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="EN-gb"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="PT-pt"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/4/edit?html,css,output">Live Demo on JSBin</a>
<!-- page 12 -->
<h4>Specificity of attribute selectors<br>
0-1-0</h4>

<p>Same as class selector and pseudoclass.</p>

<pre><code>*&lbrack;type=checkbox&rbrack; // 0-1-0</code></pre>

<p>Note that this means an attribute selector can be used to select an
element by its ID at a lower level of specificity than if it was
selected with an ID selector: &lbrack;id=<b>"my-ID"</b>&rbrack; targets the same element as <b>#my-ID</b>
but with lower specificity.</p>

<p>See the Syntax Section for more details.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-3">Section 4.3: Combinators</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<b>Overview</b>
<b>Selector Description</b>

| Selector  | Description |
|-----------|-------------------------------------------------------------------------------------|
| div span |  Descendant selector (all <b>&lt;span&gt;</b>s that are descendants of a <b>&lt;div&gt;</b>) |
| div &gt; span | Child selector (all <b>&lt;span&gt;</b>s that are direct child of a <b>&lt;div&gt;</b>) |
| a ~ span | General Sibling selector (all <b>&lt;span&gt;</b>s that are siblings after an <b>&lt;a&gt;</b>) |
| a + span | Adjacent Sibling selector (all <b>&lt;span&gt;</b> that are immediately after an <b>&lt;a&gt;</b>) |

> <b>Note:</b> Sibling selectors target elements that come after them in
> the source document. CSS, by its nature (it cascades), cannot target
> <i>previous</i> or <i>parent</i> elements. However, using the flex order
> property, a <a href="http://stackoverflow.com/a/36118012/3597276">
> previous sibling selector can be simulated on visual media</a>.

<h4>Descendant Combinator: selector selector</h4>

<p>A descendant combinator, represented by at least one space character
(), selects elements that are a descendant of the defined element.
This combinator selects <b>all</b> descendants of the element (from child
elements on down).</p>

<pre><code>div p {
  <b>color</b>: red;
}

<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
  <b>&lt;section&gt;</b>
    <b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
  <b>&lt;/section&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/2/edit?html,css,output">Live Demo on JSBin</a>

<p>In the above example, the first two <b>&lt;p&gt;</b> elements are selected since they are
both descendants of the <b>&lt;div&gt;</b>.</p>

<h4>Child Combinator: selector &gt; selector</h4>

<p>The child (&gt;) combinator is used to select elements that are
<b>children</b>, or <b>direct descendants</b>, of the specified element.</p>
<!-- page 13 -->
<pre><code>div &gt; p {
  <b>color</b>: <span style='color: red;'>red</span>;
}
<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>My text is <span style='color: red;'>red</span><b>&lt;/p&gt;</b>
  <b>&lt;section&gt;</b>
    <b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
  <b>&lt;/section&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/3/edit?html,css,output">Live Demo on JSBin</a>

<p>The above CSS selects only the first <b>&lt;p&gt;</b> element, as it is the only paragraph directly descended from a <b>&lt;div&gt;</b>.</p>
<p>The second <b>&lt;p&gt;</b> element is not selected because it is not a direct child of the <b>&lt;div&gt;</b>.</p>

<h4>Adjacent Sibling Combinator: selector &plus; selector</h4>

<p>The adjacent sibling (+) combinator selects a sibling element that immediate follows a specified element.</p>

<pre><code>p &plus; p {
  <b>color: #ff0000; /* red */</b>
}

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
<b>&lt;hr&gt;</b>
<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/4/edit?html,css,output">Live Demo on JSBin</a>

<p>The above example selects only those <b>&lt;p&gt;</b> elements which are <i>directly preceded</i> by another <b>&lt;p&gt;</b> element.</p>

<h4>General Sibling Combinator: selector &#126; selector</h4>

<p>The general sibling (&#126;) combinator selects <i>all</i> siblings that follow the specified element.</p>

<pre><code>p &#126; p
  <b>color</b>: <span style='color: #ff0000;'>red</span>;
}

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is <span style='color: #ff0000;'>red</span>&lt;/p&gt;
<b>&lt;hr&gt;</b>
<b>&lt;h1&gt;</b>And now a title&lt;/h1&gt;
<b>&lt;p&gt;</b><span style='color: #ff0000;'>My text is red</span><b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/5/edit?html,css,output">Live Demo on JSBin</a>

The above example selects all <b>&lt;p&gt;</b> elements that are <i>preceded</i> by another <b>&lt;p&gt;</b> element,
whether or not they are immediately adjacent.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-4">Section 4.4: Pseudo-classes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 14 -->
<p><a href="https://www.w3.org/TR/selectors/#pseudo-classes">Pseudo-classes</a> are <b>keywords</b> 
which allow selection based on information that lies outside of the document tree that cannot 
be expressed by other selectors or combinators. This information can be associate to a
certain state (<a href="https://www.w3.org/TR/selectors/#UIstates">state</a> and 
<a href="https://www.w3.org/TR/selectors/#dynamic-pseudos">dynamic</a> pseudo-classes), to locations 
(<a href="https://www.w3.org/TR/selectors/#structural-pseudos">structural and 
<a href="https://www.w3.org/TR/selectors/#target-pseudo">target</a> pseudo-classes), 
to negations of the former (<a href="https://www.w3.org/TR/selectors/#negation">negation</a> 
pseudo-class) or the languages (<a href="https://www.w3.org/TR/selectors/#lang-pseudo">lang</a> 
pseudo-class). Examples include whether or not a link has been followed (:visited), 
the mouse is over an element (:hover), a checkbox is checked (:checked), etc.</p>

<h4>Syntax:</h4>

<pre><code>selector:pseudo-class {
  property: <b>VALUE</b>;
}</code></pre>

<b>List of pseudo-classes:</b>

| Name          | Description |
|---------------|---------------------------------------------------------------------------------|
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:active</a>  | Applies to any element being activated (i.e. clicked) by the user. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:any">:any</a> | Allows you to build sets of related selectors by creating groups that |
|               | included items will match. This is an alternative to repeating an entire selector. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target">:target</a>  | Selects the current active #news element (clicked on a URL |
|               | containing that anchor name)
| <a href="https://www.w3.org/TR/css3-selectors/#checked">:checked</a>  | Applies to radio, checkbox, or option elements that are checked |
|               | or toggled into an "on" state. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:default">:default</a> | Represents any user interface element that is the default among a group of |
|               | similar elements. |
| <a href="https://www.w3.org/TR/css3-selectors/#enableddisabled">:disabled</a> | Applies to any UI element which is in a disabled state. |
| <a href="https://www.w3.org/TR/selectors/#empty-pseudo">:empty</a>   | Applies to any element which has no children. |
| <a href="https://www.w3.org/TR/css3-selectors/#enableddisabled">:enabled</a>  | Applies to any UI element which is in an enabled state. |
| <a href="http://tympanus.net/codrops/css_reference/first">:first</a> | Used in conjunction with @page rule, this selects the first page in a |
|               | printed document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child">:first-child</a>  | Represents any element that is the first child element of its parent. |
| <a href="https://www.w3.org/TR/css3-selectors/#first-of-type-pseudo">:first-of-type</a> | Applies when an element is the first of the selected element type |
|              | inside its parent. This may or may not be the first-child. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:focus</a>  | Applies to any element which has the user's focus. This can be given by the |
|              | user's keyboard, mouse events, or other forms of input. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within">:focus-within</a> | Can be used to highlight a whole section when one element inside it is focused. It matches |
|              | any element that the :focus pseudo-class matches or that has a descendant focused. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen">:full-screen</a>  | Applies to any element displayed in full-screen mode. It selects the whole stack |
|              | of elements and not just the top level element. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:hover</a> | Applies to any element being hovered by the user&apos;s pointing device, but |
|              | not activated. |
| <a href="https://www.w3.org/TR/css3-selectors/#indeterminate">:indeterminate</a> | Applies radio or checkbox UI elements which are neither checked nor |
|             | unchecked, but are in an indeterminate state. This can be due to an |
|             | element's attribute or DOM manipulation. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range">:in-range</a>  | The :in-range CSS pseudo-class matches when an element has |
|             | its value attribute inside the specified range limitations for this element. |
|             | It allows the page to give a feedback that the value currently defined |
|             | using the elements is inside the range limits. |
| <a href="http://tympanus.net/codrops/css_reference/invalid/">:invalid</a>  | Applies to &lt;input&gt; elements whose values are invalid according to |
|             | the type specified in the type= attribute. |
| <a href="https://www.w3.org/TR/css3-selectors/#lang-pseudo">:lang</a>  | Applies to any element who&apos;s wrapping &lt;body&gt; element has a properly |
|             | designated lang= attribute. For the pseudo-class to be valid, it must |
|             | contain a <a href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes">valid two or three langauge code</a>. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child">:last-child</a>  | Represents any element that is the last child element of its parent. |
| <a href="https://www.w3.org/TR/css3-selectors/#last-of-type-pseudo">:last-of-type</a>  | Applies when an element is the last of the selected element type inside |
|             | its parent. This may or may not be the last-child. |
| <a href="http://tympanus.net/codrops/css_reference/left_pseudo-class/">:left</a> | Used in conjunction with the &commat;page rule, this selects all the left |
|             | pages in a printed document. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-link-pseudo-classes-link-and-visited">:link | Applies to any links which haven&apos;t been visited by the user. |
| <a href="https://www.w3.org/wiki/CSS/Selectors/pseudo-classes/:not">:not() | Applies to all elements which <b>do not</b> match the value passed to |
|                 | :not(p) or :not(.class-name) for example. It must have a value to be |
|                 | valid and it can only contain one selector. However, youi can chain multiple |
|                 | together.
| <a href="https://www.w3.org/TR/css3-selectors/#nth-child-pseudo">:nth-child | Applies when an element is the n-th element of its parent, where n |
|                       | can be an integer, a mathematical expression (e.g n+3) or the keywords |
|                       | odd or even. |
| <a href="https://www.w3.org/TR/css3-selectors/#nth-of-type-pseudo">:nth-of-type | Applies when an eleent is the n-th element of its parent of the |
|                         | same element type, where n can be an integer, a mathematical |
|                         | expression (e.g n+3) or the keywords odd or even. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child">:only-child | The :only-child CSS pseudo-class represents any element |
|                        | which is the only child of a parent.  This is the same as |
|                        | :first-child:last-child or :nth-child(1):nth-last-child(1), |
|                        | but with a lower specificity. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:optional">:optional | The :optional CSS pseudo-class represents any element |
|                      | that does not have the required attribute set on it. This allows |
|                      | forms to easily indicate optional fields and to style them accordingly. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range">:out-of-range | The :out-of-range CSS pseudo-class matches when an element has its |
|                          | value attribute outside the specified range limitations for this element. |
|                          | It allows the page to give a feedback that the value currently defined using the |
|                          | element is outside the range limits. A value can be outside of a range if it is |
|                          | either smaller or larger than maximum and minimum set values. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown">:placeholder-shown | <b>Experimental:</b> Applies to any form element currently displaying placeholder text. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only">:read-only | Applies to any element which is not editable by the user. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write">:read-write | Applies to any element that is editable by a user, such as <b>&lt;input&gt;</b> elements. |
| <a href="http://tympanus.net/codrops/css_reference/right_pseudo-class">:right | Used in conjunction with the @page rule, this selects all the right pages in a |
|                   | printed document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:root">:root | Matches the root element of a tree representing the document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:scope">:scope | CSS pseudo-class matches the elements that are a reference |
|                   | point for selectors to match against. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target">:target | Selects the current active #news element (clicked on a URL |
|                    | containing that anchor name). |
| <a href="https://www.w3.org/TR/css3-selectors/#the-link-pseudo-classes-link-and-visited">:visited | Applies to any links which have been visited by the user. |

> The :visited pseudo-class can't be used for most styling in a lot of modern browsers anymore because
> it's a security hole. See this <a href="https://hacks.mozilla.org/2010/03/privacy-related-changes-coming-to-css-visited/">link</a> for reference.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown"><b>Experimental.</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-5">Section 4.5: Child Pseudo Class</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
&quot;The :nth-child(an+b) CSS pseudo-class matches an element that has
an+b-1 siblings before it in the document tree, for a given positive
<b>or zero value</b> for n&quot; - &lbrack;MDN :nth-child&rbrack;

| <b>pseudo-selector</b>       | <b>1&nbsp;&nbsp;2&nbsp;&nbsp;&nbsp;3&nbsp;&nbsp;&nbsp;4&nbsp;&nbsp;&nbsp;5&nbsp;&nbsp;&nbsp;6&nbsp;&nbsp;&nbsp;7&nbsp;&nbsp;&nbsp;8&nbsp;&nbsp;&nbsp;9&nbsp;&nbsp;&nbsp;10</b> |
|------------------------------|---------------------------------------------------------------------------------|
| :first-child                 |  ✔ |
| :nth-child (3)                | &nbsp;&nbsp;&nbsp;✔ |
| :nth-child (n+3)              | &nbsp;&nbsp;✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔ |
| :nth-child (3n)               |         ✔       ✔       ✔ |
| :nth-child (3n+1)             | ✔         ✔       ✔       ✔ |
| :nth-child (-n+3)             | ✔  ✔  ✔ |
| :nth-child (odd)              | ✔      ✔      ✔     ✔     ✔ |
| :nth-child (even)             |     ✔      ✔      ✔     ✔        ✔ |
| :last-child                   | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;✔ |
| :nth-last-child(3)            | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;✔ |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-6">Section 4.6: Class Name Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The class name selector select all elements with the targeted class
name. For example, the class name .warning would select the following
<b>&lt;div&gt;</b> element:

<pre><code>&lt;div class="warning"&gt;
  &lt;p&gt;This would be some warning copy.&lt;/p&gt;
&lt;/div&gt;</code></pre>

<p>You can also combine class names to target elements more specifically.
Let&apos;s build on the example above to showcase a more complicated class
selection.</p>

<h4>CSS:</h4>

<pre><code>.important {
  color: orange;
}
.warning {
  color: #0000ff; /* blue */
}
.warning .important {
  color: #de1205; /* red */
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div class="warning"&gt;</b>
  <b>&lt;p&gt;</b>This would be some warning copy.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div class="important warning"&gt;</b>
  <b>&lt;p class="important"&gt;</b>This is some really important warning copy.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>In this example, all elements with the .warning class will have a blue
text color, elements with the .important class with have an orange
text color, and all elements that have <i>both</i> the .important and
.warning class name will have a red text color.</p>

<p>Notice that within the CSS, the .warning.important declaration did not have any spaces
between the two class names. This means it will only find elements
which contain both class names warning and important in their class
attribute. Those class names could be in any order on the element.</p>

<p>If a space was included between the two classes in the CSS
declaration, it would only select elements that have parent elements
with a .warning class names and child elements with .important class
names.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-7">Section 4.7: Select element using its ID without the high specificity of the ID selector</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This trick helps you select an element using the ID as a value for an
attribute selector to avoid the high specificity of the ID selector.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div id="element"&gt;</b>. . .<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>#element { . . . } /* High specificity will override many selectors */
&lbrack;id="element"&rbrack; { . . .} /* Low specificity, can be overridden easily */</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-8">Section 4.8: The :last-of-type selector</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The :last-of-type selects the element that is the last child, of a particular type,
of its parent. In the example below, the css selects the last
paragraph and the last heading h1.</p>

<pre><code>p: last-of-type {
  <b>background: #C5CAE9;</b>
}

h1: last-of-type {
  <b>background: #CDDC39;</b>
}
<b>&lt;div class="container"&gt;</b>
  <b>&lt;p&gt;</b>First paragraph<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Second paragraph<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Last paragraph<b>&lt;/p&gt;</b>
  <b>&lt;h1&gt;</b>Heading 1<b>&lt;/h1&gt;</b>
  <b>&lt;h2&gt;</b>First Heading 2<b>&lt;/h2&gt;</b>
  <b>&lt;h2&gt;</b>Last heading 2<b>&lt;/h2&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<image left justified>

<a href="http://jsfiddle.net/MadalinaTn/YmMZZ/113/">jsFiddle</a>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-9">Section 4.9: CSS3 :in-range selector example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b>&lt;style&gt;</b>
input:in-range {
  border: 1px solid blue;
}
<b>&lt;/style&gt;</b>

<b>&lt;input</b> type="number" min="10" max="20" value="15"&gt;
<b>&lt;p&gt;</b>The border for this value will be blue<b>&lt;/p&gt;</b></code></pre>

<!-- page 18 -->
<p>The :in-range CSS pseudo-class matches when an element has its value attribute
inside the specified range limitations for this element. It allows the
page to give a feedback that the value currently defined using the
element is inside the range limits.&lbrack;<a href=https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range">:in-range</a>&rbrack;.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-10">Section 4.10: A. The :not pseudo-class example & B. :focuswithin CSS pseudo-class</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>A. The syntax is presented above.</h4>

<p>The following selector matches all <b>&lt;input&gt;</b> elements in an HTML document
that are not disabled and don&apos;t have the class .example:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;form&gt;</b>
  Phone: <b>&lt;input</b> type="tel" class="example"&gt;
  E-mail: <b>&lt;input</b> type="email" disabled="disabled"&gt;
  Password: <b>&lt;input</b> type="password"&gt;
<b>&lt;/form&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>input:not(&lbrack;disabled&rbrack;):not(.example){
  <b>background-color</b>: #ccc;
}</code></pre>

<p>The :not() pseudo-class will also support comma-separated selectors in
Selectors Level 4:</p>

<h4>CSS:</h4>

<pre><code>input:not(&lbrack;disabled&rbrack;):not(.example){
  <b>background-color</b>: #ccc;
}</code></pre>

<a href="http://jsbin.com/japere/edit?html,css,output">Live Demo on JSBin</a>

<p>See background syntax here.</p>

<h4>B. The :focus-within CSS pseudo-classHTML:</h4>

<h4>HTML:</h4>

<pre><code>  <b>&lt;h3&gt;</b>Background is blue if the input is focused.<b>&lt;/p&gt;</b>
  <b>&lt;div&gt;</b>
    <b>&lt;input</b> type="text"&gt;
  <b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~ 02. input focused, background blue (19) ~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<div style="load: right">
  <img src="./images/image002.png"
    align="right"
	width="50%"
    title="Input focused, background blue"
    alt="Input focused, background blue." />
</div>
<p>
  <pre><code>div {
    <b>height</b>: 80px;
  }
  input {
    <b>margin</b>: 30px;
  }
  div:focus-within {
    <b>background-color</b>: #1565C0;
  }</code></pre>
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~ 03. :focus-within css pseudo-class (19) ~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image003.png"
  style="width:100%"
  title=":focus-within CSS pseudo-class"
  alt=":focus-within CSS pseudo-class." />
</p>
<!-- page 19 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-11">Section 4.11: Global boolean with checkbox:checked and &#126; (general sibling combinator)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>With the &#126; selector, you can easily implement a global accessible
boolean without using JavaScript.</p>

<h4>Add boolean as a checkbox</h4>

<p>To the very beginning of your document, add as much booleans as you
want with a unique id and the hidden attribute set:</p>

<pre><code>&lt;input type="checkbox" dis="sidebarShown" hidden /&gt;
&lt;input type="checkbox" dis="darkThemeUsed" hidden /&gt;

&lt;!-- here begins actual content, for example: --&gt;
&lt;div id="container"&gt;
  &lt;div id="sider"&gt;
    &lt;!-- Menu, Search, ... --&gt;
  &lt;/div&gt;
    &lt;!-- Some more content ... --&gt;
 &lt;/div&gt;
 
 &lt;div id="footer"&gt;
   &lt;!-- ... --&gt;
 &lt;/div&gt;</code></pre>

<h4>Change the boolean&apos;s value</h4>
<!-- page 20 -->
<p>You can toggle the boolean by adding a label with the for attribute set:</p>

<pre><code><b>&lt;label</b> for=&quot;sidebarShown&quot;&gt;Show/Hide the sidebar!<b>&lt;/label&gt;</b></code></pre>

<h4>Accessing boolean value with CSS;</h4>

<p>The normal selector (like .color-red) specifies the default
properties. They can be overridden by following true / false
selectors:</p>

<pre><code>/* true: */
&lt;checkbox&gt;:checked &bsim; &lbrack;sibling of checkbox & parent of target&rbrack; &lt;target&gt;

/* false: */
&lt;checkbox&gt;:not(:checked) ~ &lbrack;sibling of checkbox & parent of target&rbrack; &lt;target&gt;</code></pre>

Note that &lt;checkbox&gt;, &lbrack;sibling ...&rbrack; and &lt;target&gt; should be replaced by the proper selectors. &lbrack;sibling ...&rbrack;
can be a specific selector, (often if you're lazy) simply * or nothing if the target is already a sibling of the checkbox.

Examples for the above HTML structure would be:

<pre><code>#sidebarShown:checked ~ #container #sidebar {
  margin-left: 300px;
}

#darkThemeUsed:checked ~ #container,
#darkThemeUsed:checked ~ #footer {
  background: #333;
}</code></pre>

<h4>In action:</h4>

<p>See <a href="https://jsfiddle.net/yokosbm0/1/">this Fiddle for
an implementation of these global booleans</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-12">Section 4.12: ID selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>ID selectors select DOM elements with the targeted ID. To select an
element by a specific ID in CSS, the &num; prefix is used.</p>

<p>For example, the following HTML div element...</p>

<pre><code>&lt;div id="exampleID"&gt;
  &lt;p&gt;Example&lt;/p&gt;
&lt;/div&gt;</code></pre>

<p>...can be selected by #exampleID in CSS as shown below:</p>

<pre><code>#exampleID {
  width: 20px;
}</code></pre>

<blockquote>
  <b>Note</b>: The HTML specs do not allow multiple elements with the same ID.
</blockquote>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-13">Section 4.13: How to style a Range input</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 21 -->
<h4>HTML:</h4>

<pre><code>&lt;input type="range"&gt;&lt;/input&gt;</code></pre>

<h4>CSS:</h4>

| <b>Effect</b>  | <b>Pseudo Selector</b>                             |
|----------------|----------------------------------------------------|
| Thumb          | input&lbrack;type=range&rbrack;::-webkit-slider-thumb, input&lbrack;type=range&rbrack;::-moz-range-thumb, |
|                | input&lbrack;type=range&rbrack;::-ms-thumb               |
| Track          | input&lbrack;type=range&rbrack;::-webkit-slider-runnable-track, input&lbrack;type=range&rbrack;::-moz-range-track, |
|                | input&lbrack;type=range&rbrack;::-ms-track |
| OnFocus        | input&lbrack;type=range&rbrack;:focus |
| Lower part of  | input&lbrack;type=range&rbrack;::-moz-range-progress, input&lbrack;type=range&rbrack;::-mx-fill-lower(not possible |
| the track      | in WebKit browsers currently -JS needed) |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-14">Section 4.14: The :only-child pseudo-class selector example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The :only-child CSS pseudo-class represents any element which is the only 
child of its parent.</p>

<h4>HTML:</h4>

<pre><code>&lt;div&gt;
  &lt;p>This paragraph is the only child of the div, it will have the color blue&lt;/p&gt;
&lt;/div&gt;

&lt;div&gt;
  &lt;p&gt;This paragraph is one of the two children of the div&lt;/p&gt;
  &lt;p&gt;This paragraph is one of the two children of its parent&lt;/p&gt;
&lt;/div&gt;
</code></pre>

<h4>CSS:</h4>

<pre><code>p:only-child {
  color: blue;
}</code></pre>

<p>The above example selects the &lt;p&gt; element that is the unique child from its 
parent, in this case a &lt;div&gt;.</p>

<p><a href="https://jsbin.com/dizosi/edit?html,css">Live Demo on JSBin</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch5">Chapter 5: Backgrounds</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 22 -->
<p>With CSS you can set colors, gradients, and images as the background
of an element.</p>

<p>It is possible to specify various combinations of images, colors, and
gradients, and adjust the size, positioning, and repetition (among
others) of these.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-1">Section 5.1: Background Color</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-color property sets the background color of an element
using a color value or through keywords, such as transparent, inherit
or initial.</p>

<ul>
  <li><b>transparent</b>, specifies that the background color should be
    transparent. This is default.</li>
  <li><b>inherit</b>, inherits this property from its parent element.</li>
  <li><b>initial</b>, sets this property to its default value.</li>
</ul>

<p>This can be applied to all elements, and ::first-letter/::first-line pseudo-elements.</p>

<p>Colors in CSS can be specified by different methods.</p>

<h4>Color names:</h4>

<h4>CSS:</h4>

<pre><code>div {
  <b>background-color</b>: #de1205; /* red */
}</code></pre>

<h4>HTML:</h4>

<pre><code>&lt;div&gt;This will have a red background&lt;/div&gt;</code></pre>

<ul>
  <li>The example used above is one of several ways that CSS has to represent
    a single color.</li>
</ul>

<h4>Hex color codes:</h4>

<p>Hex code is used to denote RGB components of a color in base-16
hexadecimal notation. &num;ff0000, for example, is bright red, where the
red component of the color is 256 bits (ff) and the corresponding
green and blue portions of the color is 0 (00).</p>
<p>If both values in each of the three RGB pairings (R, G, and B) are the
same, then the color code can be shortened into three characters (the
first digit of each pairing). &num;ff0000 can be shortened to &num;f00, and
&num;ffffff can be shortened to &num;fff.</p>
<p>Hex notation is case-insensitive.</p>

<pre><code>body {
  background-color: #de1205; /* red */
}

.main {
  background-color: #00f; /* blue */
}</code></pre>

<h4>RGB / RGBa:</h4>

<p>Another way to declare a color is to use RGB or RGBa.

<p>RGB stands for Red, Green and Blue, and requires of three separate
values between 0 and 255, put between brackets, that correspond with
the decimal color values for respectively red, green and blue.</p>

<p>RGBa allows you to add an additional alpha parameter between 0.0 and
1.0 to define opacity.</p>

<pre><code>header {
  <b>background-color</b>: rgb(0, 0, 0); /* black */
}
footer {
  <b>background-color</b>: rgba(0, 0, 0, 0.5); /* black with 50% opacity */
}</code></pre>

<h4>HSL / HSLa:</h4>

<p>Another way to declare a color is to use HSL or HSLa and is similar to
RGB and RGBa.</p>

<p>HSL stands for hue, saturation, and lightness, and is also often
called HLS:</p>

<ul>
  <li>Hue is a degree on the color wheel (from 0 to 360).</li>
  <li>Saturation is a percentage between 0% and 100%.</li>
  <li>Lightness is also a percentage between 0% and 100%.</li>
</ul>

<p>HSLa allows you to add an additional alpha parameter between 0.0 and
1.0 to define opacity.</p>

<pre><code>li a {
<b>background-color</b>: hsl(120, 100&percnt;, 50&percnt;); /* green */
}
#p1 {
<b>background-color</b>: hsla(120, 100&percnt;, 50&percnt;, .3); /* green with 30% opacity */
}</code></pre>

<h4>Interaction with background-image</h4>

<p>The following statements are all equivalent:</p>

<pre><code>body {
  <b>background:</b> red;
  <b>background-image:</b> url (partiallytransparentimage.png);
}
body {
  <b>background-color:</b> red;
  <b>background-image:</b> url (partiallytransparentimage.png);
}
body {
  <b>background-image:</b> url(partiallytransparentimage.png);
  <b>background-color:</b> red;
}
body {
  <b>background:</b> red url (partiallytransparentimage.png);
}</code></pre>

<!-- page 24 -->
<p>They will all lead to the red color being shown underneath the image,
where the parts of the image are transparent, or the image is not
showing (perhaps as a result of background-repeat).</p>

<p>Note that the following is not equivalent:</p>

<pre><code>body {
  <b>background-image</b>: url(partiallytransparentimage.png);
  <b>background</b>: #ff0000;  /* red */
}</code></pre>

<p>Here, the value of background overrides your background-image.</p>

<p>For more info on the background property, see Background Shorthand.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-2">Section 5.2: Background Gradients</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Gradients are new image types, added in CSS3. As an image, gradients
are set with the background-image property, or the background
shorthand.</p>

<p>There are two types of gradient functions, linear and radial. Each
type has a non-repeating variant and a repeating variant:</p>

<ul>
  <li>linear-gradient()</li>
  <li>repeating-linear-gradient()</li>
  <li>radial-gradient()</li>
  <li>repeating-radial-gradient()</li>
</ul>

<h4>linear-gradient()</h4>

<p>A linear-gradient has the following syntax</p>

<p><b>background</b>: linear-gradient( &lt;direction&gt;?, &lt;color-stop-1&gt;, &lt;color-stop-2&gt;, ...);</p>

| Value             | Meaning |
|:-----------------:|-----------------------------------------------|
| &lt;direction&gt; | Could be an argument like to top, to bottom, to right or to left; or an <a href="https://www.w3.org/TR/css3-values/#angles">angle</a> as 0deg, |
|                   | 90deg... . The angle starts from top and rotates clockwise. Can be specified in <a href="https://www.w3.org/TR/css3-values/#deg">deg</a>, <a href="https://www.w3.org/TR/css3-values/#grad">grad</a>, <a href="https://www.w3.org/TR/css3-values/#rad">rad</a>, |
|                   | or <a href="https://www.w3.org/TR/css3-values/#turn">turn</a>. If omitted, the gradient flows from top to bottom. |
| &lt;color-stop-list&gt; | List of colors, optionally followed each one by a percentage or length to display it at. For |
|                   | example, yellow 10%, rgba(0,0,0,.5) 40px, #fff 100%... |


<h4>Can be specified in;</h4>
<ul>
  <li><a href="https://www.w3.org/TR/css3-values/#deg">deg</a>,</li>
  <li><a href="https://www.w3.org/TR/css3-values/#grad">grad</a>,</li>
  <li><a href="https://www.w3.org/TR/css3-values/#rad">rad</a>, or</li>
  <li><a href="https://www.w3.org/TR/css3-values/#turn">turn</a>.</li>
</ul>

<p>For example, this creates a linear gradient that starts from the right and transitions from red to blue.</p>

<pre><code>.linear-gradient {
  <b>background</b>: linear-gradient (to left, red, blue); /* you can also use 270deg */
}</code></pre>

<p>You can create a diagonal gradient by declaring both a horizontal and vertical starting position.</p>

<pre><code>.diagonal-linear-gradient {
  <b>background</b>: linear-gradient (to left top, red, yellow 10&percnt;);
}</code></pre>
<!-- page 25 -->
<p>It is possible to specify any number of color stops in a gradient by
separating them with commas. The following examples will create a
gradient with 8 color stops;</p>

<pre><code>.linear-gradient-rainbow {
  <b>background</b>: linear-gradient(to left, red, orange, yellow, green, blue, indigo, violet);
}</code></pre>

<h4>radial-gradient()</h4>

<pre><code>.radial-gradient-simple {
  <b>background</b>: radial-gradient(red, blue);
}
.radial-gradient {
  <b>background</b>: radial-gradient(circle farthest-corner at top left, red, blue);
}</code></pre>

| Value    | Meaning   |
|----------|----------------------------------------------------------------------|
| circle   | Shape of gradient. Values are circle or ellipse, default is ellipse. |
| farthest-corner | Keywords describing how big the ending shape must be. Values  |
|                 | are closest-side, farthest-side, closest-corner, farthest-corner |
| top left   | Sets the position of the gradient center, in the same way as |
|            | background-position. |

<h4>Repeating gradients</h4>

<p>Repeating gradient functions take the same arguments as the above
examples, but tile the gradient across the background of the element.</p>

<pre><code>.bullseye {
  <b>background</b>: repeating-radial-gradient(red, red 10&percnt;, white 10&percnt;, white 20&percnt;);
}
.warning {
  <b>background</b>: repeating-linear-gradient(-45deg, yellow, yellow 10&percnt;, black 10&percnt;, black 20&percnt;);
}</code/></pre>

| <b>Value</b>   | <b>Meaning</b>  |
|----------------|-----------------|
| -45deg         | <a href="https://www.w3.org/TR/css3-values/#angles">Angle unit</a>. The angle starts from the top and rotates clockwise. Can be specified in <a href="https://www.w3.org/TR/css3-values/#deg">deg</a>, <a href="https://www.w3.org/TR/css3-values/#grad">grad</a>, <a href="https://www.w3.org/TR/css3-values/#rad">rad</a>, or |
|                | <a href="https://www.w3.org/TR/css3-values/#turn">turn</a>. |
| to left        | Direction of gradient, default is to bottom. Syntax: to &lbrack;y-axis(top or bottom)&rbrack; &lbrackx-asis(left OR |
|                | right)&rbrack; ie to top right. |
| yellow 10%     | Color, optionally followed by a percentage or length to display it at. Repeated two or more times. |

<p>Note that HEX, RGB, RGBa, HSL, and HSLa color codes may be used instead of color names. Color names were used
for the sake of illustration. Also note that the radial-gradient syntax is much more complex than linear-gradient, 
and a simplified version is shown here. For a full explanation and specs, see the 
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/radial-gradient">MDN Docs</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-3">Section 5.3: Background Image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-image property is used to specify a background image to
be applied to all matched elements. By default, this image is tiled to
cover the entire element, excluding margin.</p>

<pre><code>.myClass {
  <b>background-image</b>: url (&apos;/path/to/image.jpg&apos;);
}</code></pre>

<!-- page 26 -->
<p>To use multiple images as background-image, define comma separated url().</p>

<pre><code>.myClass {
  <b>background-image</b>: url (&apos;/path/to/image.jpg&apos;), 
                    url (&apos;/path/to/image2.jpg&apos;);
}</code></pre>

<p>The images will stack according to their order with the first declared
image on top of the others and so on.</p>

| <b>Value</b>  |   <b>Result</b>    |
|---------------|--------------------|
| url (&apos;/path/to/image.jpg&apos;) | Specify background image&apos;s path(s) or an image resource specified with data URI |
|                                      | schema (apostrophes can be omitted), separate multiples by comma. |
| none | No backgound image. |
| initial   | Default value. |
| inherit | Inherit parent's value. |

<h4>More CSS for Background Image:</h4>

<p>The following attributes are very useful and almost essential;</p>

<h4><b>background-size</b>:&nbsp;&nbsp;&nbsp;&nbsp; xpx ypx &vert; x% y%;</h4>

<h4><b>background-repeat</b>:&nbsp; no-repeat &vert; repeat &vert; repeat-x &vert; repeat-y;</h4>
 
<h4><b>background-position</b>: left offset (px/%) right offset (px/%) &vert; center center &vert; left top &vert; right bottom</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-4">Section 5.4: Background Shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background property can be used to set one or more background related properties:</p>

| <b>Value</b> | <b>Description</b>                               |
|--------------|--------------------------------------------------|
| background-image | Background image to use.  |
| background-color | Background color to apply. |
| background-position | Background image&apos;s position. |
| background-size | Background image&apos;s size. |
| background-repeat | How to repeat background image. |
| background-origin | How the background is positioned (ignored when |
|              | background-attachment is fixed).                 |
| background-clip | How the background is painted relative to the |
|              | content-box, border-box, or the padding-box.     |
| background-attachment | How the background image behaves, whether it |
|              | scrolls along with its containing block or has a |
|              | fixed position within the viewport.  |
| initial      | Sets the property value to default. |
| inherit      | Inherits property value from parent.       |

<p>The order of the values does not matter and every value is optional.</p>

<h4>Syntax:</h4>

<p>The syntax of the background shorthand declaration is:</p>

<b>background</b>: &lbrack;&lt;background-image&gt;&rbrack; &lbrack;&lt;background-color&gt;&rbrack;
&lbrack;&lt;background-position&gt;&rbrack;/&lbrack;&lt;background-size&gt;&rbrack;<br>
&lbrack;&lt;background-repeat&gt;&rbrack; &lbrack;&lt;background-origin&gt;&rbrack;
&lbrack;&lt;background-clip&gt;&rbrack; &lbrack;&lt;background-attachment&gt;&rbrack;<br>
&lbrack;&lt;initial&vert;inherit&gt;&rbrack;;

<p>Examples</p>

<pre><code><b>background</b>: #ff0000;</code></pre>

<p>Simply setting a background-color with the red value.</p>

<pre><code><b>background</b>: border-box red;</code></pre>

<p>Setting a background-clip to border-box and a background-color to red.</p>

<pre><code><b>background</b>: no-repeat center url(&quot;somepng.jpg&quot;);</code></pre>

<p>Sets a background-repeat to no-repeat, background-origin to center and
a background-image to an image.</p>

<pre><code><b>background</b>: url(&apos;pattern.png&apos;) green;</code></pre>

<p>In this example, the background-color of the element would be set to
green with pattern.png, if it is available, overlayed on the colour,
repeating as often as necessary to fill the element. If pattern.png
includes any transparency then the green colour will be visible behind
it;</p>

<pre><code><b>background</b>: #000000 url(&quot;picture.png&quot;) top left / 600px auto no-repeat;</code></pre>

<p>In this example we have a black background with an image
&apos;picture.png&apos; on top, the image does not repeat in either axis and
is positioned in the top left corner. The / after the position is to
be able to include the size of the background image which in this case
is set as 600px width and auto for the height. This example could work
well with a feature image that can fade into a solid colour;</p>

<blockquote>
  <b>NOTE:</b> Use of the shorthand background property resets all
  previously set background property values, even if a value is not
  given. If you wish only to modify a background property value
  previously set, use a longhand property instead.
</blockquote>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-5">Section 5.5: Background Size</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>General overview:</h4>

<p>The <a href="https://www.w3.org/TR/2014/CR-css3-background-20140909/#the-background-size">Demo (background-size)</a>
property enables one to control the scaling of the background-image.
It takes up to two values, which determine the scale/size of the
resulting image in vertical and and horizontal direction. If the
property is missing, its deemed auto in both width and height.<br><br>
auto will keep the image&apos;s aspect ratio, if it can be determined. The
height is optional and can be considered auto. Therefore, on a 256 px
× 256 px image, all the following background-size settings would yield
an image with height and width of 50 px:</p>

<pre><code><b>background-size</b>: 50px;
<b>background-size</b>: 50px auto; /* same as above */
<b>background-size</b>: auto 50px;
<b>background-size</b>: 50px 50px;</code></pre>

<p>So if we started with the following picture (which has the mentioned
size of 256 px × 256 px),</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~ 04. 256 x 256 image, circle, triangle and square (28) ~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image004.png"
  style="width:256px height:256px;"
  title="256 x 256 image, circle, triangle and square"
  alt="256 x 256 image, circle, triangle and square." />
</p>
<p>we&apos;ll end up with a 50 px × 50 px on the user&apos;s screen, contained in
the background of our element:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~ 05. 50px x 50px; circle, triangle, and square (28) ~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image005.png"
  style="width:50px height:50px;"
  title="50px by 50px image; circle, triangle, and square"
  alt="50px by 50px image; circle, triangle, and square." />
</p>

<p>One can also use percentage values to scale the image with respect of
the element. The following example would yield a 200 px × 133 px drawn
image:</p>

<pre><code>#withbackground {
  <b>background-image</b>: url(to/some/background.png);
  <b>background-size</b>: 100&percnt; 66&percnt;;
  
  <b>width</b>:200px;
  <b>height</b>: 200px;
  
  <b>padding</b>: 0;
  <b>margin</b>: 0; 
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~ 06. 200x200, circle, triangle and square (28) ~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image006.png"
  style="width:200px height:200px;"
  title="200 by 200; circle, triangle and square"
  alt="200 by 200; circle, triangle and square." />
</p>

<p>The behaviour depends on the 
<a href="https://www.w3.org/TR/2014/CR-css3-background-20140909/#the-background-origin">Demo (background-origin)</a>.</p>

<h4>Keeping the aspect ratio</h4>

<p>The last example in the previos section lost its original aspect
ratio. The circle got into an ellipse, the square into a rectangle,
the triangle into another triangle.</p>

<p>The length or percentage approach isn&apos;t flexible enough to keep the
aspect ratio at all times. auto doesn&apos;t help, since you might not
know which dimension of your element will be larger. However, to cover
certain areas with an image (and correct aspect ratio) completely or
to contain an image with correct aspect ratio completely in a
background area, the values, contain and cover provide the additional
functionality.</p>

<h4>Eggsplanation for <span style="font-family: Consolas; font-size: 16px;">contain</span> and <span style="font-family: consolas">cover</span></h4>

<p>Sorry for the bad pun, but we&apos;re going to use a <a href="https://commons.wikimedia.org/wiki/File:Chicken_Egg_without_Eggshell_5859.jpg">
picture of the day by Biswarup Ganguly</a> for demonstration. Lets say that 
this is your screen, and the gray area is outside of your visible screen. For 
demonstration, we're going to assume a 16 x 9 ratio.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 07. rectangle 16x9 (29) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image007.png"
  style="width:50%"
  title="Rectangle, 16 by 9"
  alt="Rectangle, 16 by 9." />
</p>

<p>We want to use the aforementioned picture of the day as a background.
However, we cropped the image to 4x3 for some reason. We could set the
background-size property to some fixed length, but we will focus on
contain and cover. Note that I also assume that we didn&apos;t mangle the
width and/or height of body.</p>

<h4>contain</h4>

<blockquote>
contain

Scale the image, while preserving its intrinsic aspect ratio (if any), to the largest 
size such that both its width and its height can fit inside the background positioning area.
</blockquote>

<p>This makes sure that the background image is always completely
contained in the background positioning area, however, there could be
some empty space filled with your background-color in this case:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 09. egg in a frame (29) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image009.png"
  style="width:50%"
  title="Egg in a frame"
  alt="Egg in a frame." />
</p>
<!-- [image007.png 4.95x2.79] -->
<h4>cover</h4>

<blockquote>
cover

Scale the image, while preserving its intrinsic aspect ratio (if any), to the smallest size suck
that both its width and height can completely cover the background positioning area.
</blockquote>
<p>This makes sure that the background image is covering everything.
There will be no visible background-color, however depending on the
screen&apos;s ratio a great part of your image could be cut off:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 11. egg in a frame, #2 (30) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image011.png"
  style="width:50%"
  title="Egg in a frame, #2"
  alt="Egg in a frame, #2." />
</p>

<h4>Demonstration with actual code</h4>

<pre><code>div &gt; div {
  <b>background-image</b>: url(http://i.stack.imgur.com/r5CAq.jpg);
  <b>background-repeat</b>: no-repeat;
  <b>background-position</b>: center center;
  <b>background-color</b>: #ccc;
  <b>border</b>: 1px solid;
  <b>width</b>: 20em;
  <b>height</b>: 10em;
}
div .contain {
  <b>background-size</b>: contain;
}
div .cover {
  <b>background-size</b>: cover;
}
/*********************************
Additional styles for the explanation boxes
*********************************/
div &gt; div {
  <b>margin</b>: 0 1ex 1ex 0;
  <b>float</b>: left;
}
div &plus; div {
  <b>clear</b>: both;
  <b>border-top</b>: 1px dashed silver;
  <b>padding-top</b>: 1ex;
}
div &gt; div::after {
  <b>background-color</b>: #000;
  <b>color</b>: #fefefe;
  <b>margin</b>: 1ex;
  <b>padding</b>: 1ex;
  <b>opacity</b>: 0.8;
  <b>display</b>: block;
  <b>width</b>: 10ex;
  <b>font-size</b>: 0.7em;
  <b>content</b>: attr(class);
}
  <b>&lt;div&gt;</b>
    <b>&lt;div</b> class=&quot;contain&quot;<b>&gt;&lt;/div&gt;</b>
    <b>&lt;p&gt;</b>Note the grey background. The image does not cover the whole region, 
      but it&apos;s fully<b>&lt;</b>
  <b>&lt;em&gt;</b>contained<b>&lt;/em&gt;</b>.
  <b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>
<b>&lt;div&gt;</b>
  <b>&lt;div</b> class=&quot;cover&quot;<b>&gt;&lt;/div&gt;</b>
  <b>&lt;p&gt;</b>Note the ducks/geese at the bottom of the image. Most of the water is
    cut, as well as a part of the sky. You don&apos;t see the complete 
    image anymore, but neither do you see any background color;
    the image<b>&lt;em&gt;</b>covers<b>&lt;/em&gt;</b> all of the <b>&lt;code&gt;</b>&lt;div&gt;<b>&lt;/code&gt;</b>.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~ 12. example, contain & cover images (31) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image012.png"
  style="width:50%"
  title="Example, contain and cover images"
  alt="Example, contain and cover images." />
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-6">Section 5.6: Background Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <a href="https://drafts.csswg.org/css-backgrounds-3/#background-position">background-position</a> 
property is used to specify the starting position for a background image or gradient.</p>

<pre><code>.myClass {
  <b>background-image</b>: url(&apos;path/to/image.jpg&apos;);
  <b>background-position</b>: 50&percnt; 50&percnt;;
}</code></pre>

<p>The position is set using an <b>X</b> and <b>Y</b> co-ordinate and be set
using any of the units used within CSS.</p>

| <b>Unit</b>  |  <b>Description</b> |
|--------------|------------------------------------------------------------------|
| value% value% | A percentage for the horizontal offset is relative to (width of |
|               | background positioning area - width of background image). |
|               | A percentage for the vertical offset is relative to |
|              | (height of background positioning area - height of background image) |
|             |  The size of the image is the size given by background-size. |
| valuepx valuepx | Offsets background image by a length given in pixels relative to the |
|                 | top left of the background *value*px *value*px positioning area |


<p>Units in CSS can be specified by different methods (see here).</p>

<h4>Longhand Background Position Properties</h4>

In addition to the shorthand property above, one can also use the
longhand background properties backgroundposition-x and
background-position-y. These allow you to control the x or y positions
separately.

<blockquote>
  <b>NOTE:</b> This is supported in all browsers except Firefox (versions
  31-48)
  &lbrack;2&rbrack;<a href="http://caniuse.com/#search=background-position-x"></a>.
  Firefox 49, to be released September 2016, <i>will</i> support these
  properties. Until then, 
  <a href="http://stackoverflow.com/questions/14844407/background-position-y-doesnt-work-in-firefox-via-css/29282573#29282573">
  there is a Firefox hack within this Stack Overflow answer</a>.
</bockquote>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-7">Section 5.7: The background-origin property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-origin property specifies where the background image is positioned.</p>

<p>Note: If the background-attachment property is set to fixed, this
property has no effect.</p>
<p>Default value: padding-box</p>
<p>Possible values:</p>

<ul>
  <li>padding-box - The position is relative to the padding box</li>
  <li>border-box - The position is relative to the border box</li>
  <li>content-box - The position is relative to the content box</li>
  <li>initial</li>
  <li>inherit</li>
</ul>

<h4>CSS:</h4>

<pre><code>.example {
  <b>width</b>: 300px;
  <b>border</b>: 20px solid black;
  <b>padding</b>: 50px;
  <b>background</b>: url (https://static.pexels.com/photos/6440/magazines-desk-work-workspace-medium.jpg);
  <b>background-repeat</b>: no-repeat;
}

.example1 {}
.example2 { <b>background-origin</b>: border-box; }
.example3 { <b>background-origin</b>: content-box;}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;p&gt;</b>No background-origin (padding-box is default):<b>&lt;/p&gt;</b>
<b>&lt;div</b> class=&quot;example example1&quot;<b>&gt;&lt;h2&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;&lt;p&gt;</b>
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
  tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut
  aliquip ex ea commodo consequat.<b>&lt;/p&gt;
&lt;/div&gt;</b>

<b>&lt;p&gt;</b>background-origin: border-box:<b>&lt;/p&gt;</b>
<b>&lt;div</b> class=&quot;example example2&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b>
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
  tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut 
  aliquip ex ea commodo consequat.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;p&gt;</b>background-origin: content-box:<b>&lt;/p&gt;</b>
  <b>&lt;div</b> class=&quot;example example3&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b> 
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
  tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation
  ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~ 13. background-origin - 3 images (34) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image013.jpg"
  style="width:100%"
  title="no-background-origin (padding-box is default), background origin: 
    border-box, background-origin: content-box"
  alt="no-background-origin (padding-box is default), background origin: 
    border-box, background-origin: content-box." />
</p>

<p>More:</p>

<p><a href="https://www.w3.org/TR/css3-background/#the-background-origin">https://www.w3.org/TR/css3-background/#the-background-origin</a></p>
<p><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin">https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin</a></p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-8">Section 5.8: Multiple Background Image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p> In CSS3, we can stack multiple background in the same element.</p>

<pre><code>#mydiv {
  <b>background-image</b>: url(img_1.png),   /* top image */
                     url (img_2.png), /* middle image */
                     url (img_3.png); /* bottom image */
  <b>background-position</b>: right bottom, 
                       left top,
                       right top;
  <b>background-repeat</b>: no-repeat, 
                     repeat, 
                     no-repeat;
}</code></pre>

<p>Images will be stacked atop one another with the first background on
top and the last background in the back. img_1 will be on top, the
img_2 and img_3 is on bottom.</p>

<p>We can also use background shorthand property for this:</p>

<pre><code>#mydiv {
  <b>background</b>: url(img_1.png) right bottom no-repeat,
              url(img_2.png) left top repeat,
              url(img_3.png) right top no-repeat;
}</code></pre>

<p>We can also stack images and gradients:</p>

<pre><code>#mydiv {
  <b>background</b>: url(image.png) right bottom no-repeat,
              linear-gradient (to bottom, #fff 0&percnt;, #000 100&percnt;);
}</code></pre>


<ul>
  <li><a href="https://jsfiddle.net/z30up2un/">Demo (jsFiddle)</a></li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-9">Section 5.9: Background Attachment</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-attachment property sets whether a background image is
fixed or scrolls with the rest of the page.</p>

<pre><code>body {
  <b>background-image</b>: url(&apos;img.jpg&apos;);
  <b>background-attachment</b>: fixed;
}</code></pre>

| Value | Description |
|------------|---------------------------------------------------|
| scroll | The background scrolls along with the element. This is default. |
| fixed  | The background is fixed with regard to the viewport. |
| local  | The background scrolls along with the element&apos;s contents. |
| initial | Sets this property to its default value. |
| inherit | Inherits this property from its parent element. |

<h4>Examples:</h4>

<h4><i>background-attachment: scroll</i></h4>

<p>The default behaviour, when the body is scrolled the background scrolls with it:</p>

<pre><code>body {
  <b>background-image</b>: url(&apos;image.jpg&apos;);
  <b>background-attachment</b>: scroll;
}</code></pre>

<h4><i>background-attachment: fixed</i></h4>

<p>The background image will be fixed and will not move when the body is scrolled:</p>

<pre><code>body {
  <b>background-image</b>: url(&apos;image.jpg&apos;);
  <b>background-attachment</b>: fixed;
}</code></pre>

<h4><i>background-attachment: local</i></h4>

<p>The background image of the div will scroll when the contents of the
div is scrolled.</p>

<pre><code>div {
  <b>background-image</b>: url(&apos;image.jpg&apos;);
  <b>background-attachment</b>: local;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-10">Section 5.10: Background Clip</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Definition and Usage: The background-clip property specifies the painting area of the background.</p>

<p>Default value: border-box</p>

<p>Values</p>

<ul>
  <li>border-box is the default value. This allows the background to extend
    all the way to the outside edge of the element&apos;s border.</li>
  <li>padding-box clips the background at the outside edge of the element&apos;s padding and
    does not let it extend into the border;</li>
  <li>content-box clips the background at the edge of the content box.</li>
  <li>inherit applies the setting of the parent to the selected element.</li>
</ul>

<h4>CSS:</h4>

<pre><code>.example {
  <b>width</b>:300px;
  <b>border</b>:20px solid black;
  <b>padding</b>:50px;
  <b>background</b>:url (https://static.pexels.com/photos/6440/magazines-desk-work-workspace-medium.jpg);
  <b>background-repeat</b>: no-repeat;
}
.example1 {}
.example2 { <b>background-origin</b>: border-box; }
.example3 { <b>background-origin</b>: content-box; }</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;p&gt;</b>No background-origin (padding-box is default):<b>&lt;/p&gt;</b>

<b>&lt;div</b> class=&quot;example example1&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b>
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod 
    tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut 
    aliquip ex ea commodo consequat.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;p&gt;</b>background-origin: border-box:<b>&lt;/p&gt;</b>
<b>&lt;div</b> class=&quot;example example2&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b>
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
    tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut 
    aliquip ex ea commodo consequat.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;p&gt;</b>background-origin: content-box:<b>&lt;/p&gt;</b>
<b>&lt;div</b> class=&quot;example example3&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b>
  <b>&lt;p&gt;</b>There once was a man fron Sash. His balls were made of glass
  When he rubbed them together, he made stormy weather.
  And lightning struck out of his ass.<b>&lt;/p&gt;</b> 
  <b>&lt;p&gt;</b>And more goes here, as well. It beats Latin. I don't know Latin so better 
  for me the end.<b>&lt;/p&gt; 
&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-11">Section 5.11: Background Repeat</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-repeat property sets if/how a background image will be repeated.</p>

<p>By default, a background-image is repeated both vertically and horizontally.</p>

<pre><code>div {
  <b>background-image</b>: url (&quot;img.jpg&quot;);
  <b>background-repeat</b>: repeat-y;
}</code></pre>

<p>Here's how a <b>background-repeat</b>: repeat-y looks like:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~ 14. cat repeat 7x repeat-y column (37) ~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image014.jpg"
  style="width:75%"
  title="Cat repeat 7x repeat-y furthest left column"
  alt="Cat repeat 7x repeat-y furthest left column." />
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-12">Section 5.12: background-blend-mode Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>.my-div {
  <b>width</b>:300px;
  <b>height</b>:200px;
  <b>background-size</b>:100&percnt;;
  <b>background-repeat</b>:no-repeat;
  <b>background-image</b>:linear-gradient (to right, black 0&percnt; ,white 100&percnt;),
url(&apos;https://static.pexels.com/photos/54624/strawberry-fruit-red-sweet-54624-medium.jpeg&apos;);
  <b>background-blend-mode</b>:saturation;
}
<b>&lt;div</b> class=&quot;my-div&quot;<b>&gt;Lorem ipsum&lt;/div&gt;</b></code></pre>

<p>See result here: <a href="https://jsfiddle.net/MadalinaTn/y69d28Lb/">Demo (jsFiddle)</a>.</p>

<p>CSS Syntax: background-blend-mode: normal &vert; multiply &vert; screen &vert;
overlay &vert; darken &vert; lighten &vert; color-dodge &vert; saturation &vert; color &vert;
luminosity;</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-13">Section 5.13: Background Color with Opacity</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>If you set opacity on an element it will affect all its child elements. To 
set an opacity just on the background of an element you will have to use RGBA 
colors. Following example will have a black background with 0.6 opacity.</p>

<pre><code>/* Fallback for web browsers that don&apos;t support RGBa */
<b>background-color</b>:rgb (0, 0, 0);

/* RGBa with 0.6 opacity */
<b>background-color</b>:rgba (0, 0, 0, 0.6);

/* For IE 5.5 - 7 */
<b>filter</b>: progid:DXImageTransform.Microsoft.gradient(startColorstr = #99000000, endColorstr = #99000000);

/* For IE 8 */
&minus;ms-filter: &quot;progid:DXImageTransform.Microsoft.gradient(startColorstr=#99000000,
endColorstr=#99000000)&quot;;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch6">Chapter 6: Centering</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-1">Section 6.1: Using Flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;container&quot;<b>&gt;</b>
  <b>&lt;img</b> src=&quot;http://lorempixel.com/400/200&quot; <b>/&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>html, body, .container {
  <b>height</b>:100&percnt;;
}
.container {
  <b>display</b>: flex;
  <b>justify-content</b>: center;  /* horizontal center */
}
img {
  <b>align-self</b>:center;  /* vertical center */
}</code></pre>

<p><a href="https://jsfiddle.net/aLu05kjy/1/">Demo (View result-jsFiddle)</a>.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;img</b> src = &quot;http://lorempixel.com/400/200&quot; <b>/&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>html, body {
  <b>height</b>:100&percnt;;
}
body {
  <b>display</b>:flex;
  <b>justify-content</b>:center;  /* horizontal center */
  <b>align-items</b>:center;      /* vertical center */
}</code></pre>

<p><a href="https://jsfiddle.net/ttp0bzfm/1/">Demo (View Result)</a>.</p>

See Dynamic Vertical and Horizontal Centering under the Flexbox
documentation for more details on flexbox and what the styles mean.

<b>Browser Support</b>

<p>Flexbox is supported by all major browsers, <a href="http://caniuse.com/#search=flex">
except IE versions before 10</a>.</p>

<p>Some recent browser versions, such as Safari 8 and IE10, require 
<a href="https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix">vendor prefixes</a>.</p>

<p>For a quick way to generate prefixes there is <a href="https://autoprefixer.github.io/">
Autoprefixer</a>, a third-party tool.</p>

<p>For older shitty browsers (like IE 8 & 9) a <a href="https://github.com/jonathantneal/flexibility">Polyfill</a> is
available.</p>

<p>For a more detailed look at flexbox browser support, see 
<a href="http://stackoverflow.com/a/35137869/3597276">this answer.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-2">Section 6.2: Using CSS transform</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS transforms are based on the size of the elements so if you don&apos;t
know how tall or wide your element is, you can position it absolutely
50% from the top and left of a relative container and translate it by
50% left and upwards to center it vertically and horizontally.</p>

<p>Keep in mind that with this technique, the element could end up being
rendered at a non-integer pixel boundary, making it look blurry. 
See <a href="http://stackoverflow.com/a/32329785/1385678">
this answer in Stack Overflow </a>for a workaround.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;container&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;element&quot;<b>&gt;&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.container {
  <b>position</b>: relative;
}
.element {
  <b>position</b>: absolute;
  <b>top</b>: 50&percnt;;
  <b>left</b>: 50&percnt;;
  <b>transform</b>: translate(-50&percnt;, -50&percnt);
}</code></pre>

<p><a href="https://jsfiddle.net/webtiki/rz3p3ufs/">View example in jsFiddle</a>.</p>

<h4>CROSS BROWSER COMPATIBILITY</h4>

<p>The transform property needs prefixes to be supported by older
browsers. Prefixes are needed for Chrome&lt;=35, Safari&lt;=8, Opera&lt;=22,
Android Browser&lt;=4.4.4, and IE9. CSS transforms are not supported by
IE8 and older versions.</p>

<p>Here is a common transform declaration for the previous example:</p>

<pre><code>-webkit-transform: translate(-50%, -50%); /* Chrome, Safari, Opera, Android */
    -ms-transform: translate(-50%, -50%); /* IE 9 */
     <b>transform</b>: translate(-50%, -50%);</code></pre>

<p>For more information see <a href="http://caniuse.com/#feat=transforms2d">canIuse</a>.</p>

<h4>MORE INFORMATION</h4>

<ul>
  <li>The element is being positioned according to the first non-static
    parent (<b>position</b>: relative, absolute, or fixed). Explore more in this
    <a href="https://jsfiddle.net/siavasfiroozbakht/ox8kyypa/">fiddle </a> and 
	this documentation topic.</li>
  <li>For horizontal-only centering, use <b>left</b>. 50% and <b>transform</b>: translateX(-50%).
    The same goes for vertical-only centering: center with <b>top</b>: 50% and <b>transform</b>: translateY(-50%).</li>
  <li>Using a non-static width/height elements with this method of centering can cause the centered 
    element to appear squished. This mostly happens with elements containing text, and can be fixed 
	by adding: <b>margin-right</b>: -50%; and <b>margin-bottom</b>: -50%;. View this
    <a href="https://jsfiddle.net/4xxmxca0/">fiddle for more information.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-3">Section 6.3: Using margin: 0 auto;</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Objects can be centered by using if they are block elements and have a defined width.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;containerDiv&quot;<b>&gt;</b>
  <b>&lt;div</b> id=&quot;centeredDiv&quot;<b>&gt;&lt;/div&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;containerDiv&quot;<b>&gt;</b>
  <b>&lt;p</b> id=&quot;centeredParagraph&quot;<b>&gt;</b>This is a centered paragraph.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;containerDiv&quot;<b>&gt;</b>
  <b>&lt;img</b> id=&quot;centeredImage&quot;
    src=&quot;https://i.kinja-img.com/gawker-media/image/upload/s--c7Q9b4Eh&minus;-/c_scale,fl_progressive,q_80,w_800/qqyvc3bkpyl3mfhr8all.jpg&quot; <b>/&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.containerDiv {
  <b>width</b>: 100&percnt;;
  <b>height</b>: 100px;
  <b>padding-bottom</b>: 40px;
}
#centeredDiv {
  <b>margin</b>: 0 auto;
  <b>width</b>: 200px;
  <b>height</b>: 100px;
  <b>border</b>: 1px solid #000;
}
#centeredParagraph {
  <b>width</b>: 200px;
  <b>margin</b>: 0 auto;
}
#centeredImage {
  <b>display</b>: block;
  <b>width</b>: 200px;
  <b>margin</b>: 0 auto;
}</code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~ 15. this is a centered paragraph with jet on landing strip (42) ~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image015.jpg"
  style="width:100%"
  title="This is a centered paragraph with jet on landing strip"
  alt="This is a centered paragraph with jet on landing strip." />
</p>

<p>JSFiddle example: Centering objects with margin: 0
auto <a href="https://jsfiddle.net/xf1ze3v9/">Demo (jsFiddle)</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-4">Section 6.4: Using text-align</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The most common and easiest type of centering is that of lines of text
in an element. CSS has the rule <b>text-align</b>: center for this purpose:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;p&gt;</b>Lorem ipsum<b>&lt;/p&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>p {
  <b>text-align</b>: center;
}</code></pre>

<p><i>This does not work for centering entire block elements</i>. text-align
controls only alignment of inline content like text in its parent block element.</p>

<p>See more about text-align in Typography section.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-5">Section 6.5: Using position: absolute</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><i>Working in old browsers (IE &gt;= 8)</i></p>

<p>Automatic margins, paired with values of zero for the left and right
or top and bottom offsets, will center an absolutely positioned
elements within its parent.</p>

<p><a href="https://jsfiddle.net/stuttufu/sj2m0oo2/1/">Demo (View Result)</a>.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;parent&quot;<b>&gt;</b>
  <b>&lt;img</b> class=&quot;center&quot; src=&quot;http://lorempixel.com/400/200/&quot;<b>/&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.parent {
  <b>position</b>: relative;
  <b>height</b>: 500px;
}
.center {
  <b>position</b>: absolute;
  <b>margin</b>: auto;
  <b>top</b>: 0;
  <b>right</b>: 0;
  <b>bottom</b>: 0;
  <b>left</b>: 0;
}</code></pre>

<p>Elements that don&apos;t have their own implicit width and height like
images do, will need those values defined.</p>

<p>Other resources: <a href="http://codepen.io/shshaw/details/gEiDt">Absolute Centering in CSS (CodePen)</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-6">Section 6.6: Using calc()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The calc() function is the part of a new syntax in CSS3 in which you can 
calculate (mathematically) what size/position your element occupies by using 
a variety of values like pixels, percentages, etc. Note: Whenever you use this 
function, always take care of the space between two values calc(100% - 80px).</p>

<h4>CSS:</h4>

<pre><code>.center {
  <b>position</b>: absolute;
  <b>height</b>: 50px;
  <b>width</b>: 50px;
  <b>background</b>: #ff0000; /* red */
  <b>top</b>: calc (50&percnt; &minus; 50px/2); /* height divided by 2 */
  <b>left</b>: calc (50&percnt; &minus; 50px / 2); /* width divided by 2 */
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;center&quot;<b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-7">Section 6.7: Using line-height</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can also use line-height to center vertically a single line of
text inside a container:</p>

<h4>CSS:</h4>

<pre><code>div {
  <b>height</b>: 200px;
  <b>line-height</b>: 200px;
}</code></pre>

<p>That&apos;s quite ugly, but can be useful inside an <b>&lt;input</b> <b>/&gt;</b> 
element. The line-height property works only when the text to be centered spans a 
single line. If the text wraps into multiple lines, the resulting output won&apos;t 
be centered.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-8">Section 6.8: Vertical align anything with 3 lines of code</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><a href="http://caniuse.com/#search=transform">Supported by IE11+</a>.</p>

<p><a href="https://jsfiddle.net/bnqrLgk9/1/">View Result (jsFiddle)</a>.</p>

<p>Use these 3 lines to vertical align practically everything. Just make
sure the div/image you apply the code to has a parent with a height.</p>

<h4>CSS:</h4>

<pre><code>div .vertical {
  <b>position</b>: relative;
  <b>top</b>: 50&percnt;;
  <b>transform</b>: translateY(-50&percnt;);
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;vertical&quot;<b>&gt;</b>Vertical aligned text!<b>&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-9">Section 6.9: Centering in relation to another item</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>We will see how to center content based on the height of a near element.</p>

<p>Compatibility: IE8+, all other modern browsers.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;position-container&quot;<b>&gt;</b>
    <b>&lt;div</b> class=&quot;thumb&quot;<b>&gt;</b>
      <b>&lt;img</b> src=&quot;http://lorempixel.com/400/200/&quot;<b>&gt;</b>
    <b>&lt;/div&gt;</b>
    <b>&lt;div</b> class=&quot;details&quot;<b>&gt;</b>
      <b>&lt;p</b> class=&quot;banner-title&quot;<b>&gt;</b>text 1<b>&lt;/p&gt;</b>
      <b>&lt;p</b> class=&quot;banner-text&quot;<b>&gt;</b>content content content content content content content content
        content content content content content content<b>&lt;/p&gt;</b>
      <b>&lt;button</b> class=&quot;btn&quot;<b>&gt;</b>button<b>&lt;/button&gt;</b>
    <b>&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.content &ast; {
  <b>box-sizing</b>: border-box;
}
.content .position-container {
  <b>display</b>: table;
}
.content .details {
  <b>display</b>: table-cell;
  <b>vertical-align</b>: middle;
  <b>width</b>: 33.333333&percnt;;
  <b>padding</b>: 30px;
  <b>font-size</b>: 17px;
  <b>text-align</b>: center;
}
.content .thumb {
  <b>width</b>: 100&percnt;;
}
.content .thumb img {
  <b>width</b>: 100&percnt;;
}</code></pre>

<p><a href="https://jsfiddle.net/gasp10/6bv92mko/4/">Demo (jsFiddle)</a>.</p>

<p>The main points are the 3 .thumb, .details and .position-container containers:</p>

<ul>
  <li>The .position-container must have <b>display</b>: table.</li>
  <li>The .details must have the real width set width: .... and display: 
    table-cell , vertical-align: middle.</li>
  <li>The .thumb must have <b>width: 100%</b> if you want that it will take all 
    the remaining space and it will be influenced by the .details width.</li>
  <li>The image (if you have an image) inside .thumb should have <b>width: 100%</b>, 
    but it is not necessary if you have correct proportions.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-10">Section 6.10: Ghost element technique (Michał Czernow&apos;s hack)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This technique works even when the container&apos;s dimensions are unknown.</p>

<p>Set up a &quot;ghost&quot; element inside the container to be centered that is
100% height, then use <b>vertical-align</b>: middle on both that and the element to be centered.</p>

<h4>CSS:</h4>

<pre><code>/* This parent can be any width and height */
.block {
  <b>text-align</b>: center;
/* May want to do this if there is risk the container may be 
  narrower than the element inside */
  <b>white-space</b>: nowrap;
}

/* The ghost element */
.block: before {
  <b>content</b>: &apos;&apos;;
  <b>display</b>: inline-block;
  <b>height</b>: 100&percnt;;
  <b>vertical-align</b>: middle;
/* There is a gap between ghost element and .centered,
caused by space character rendered. Could be eliminated by
nudging .centered (nudge distance depends on font family),
or by zeroing font-size in .parent and resetting it back
(probably to 1rem) in .centered. */
  <b>margin-right</b>: -0.25em;
}
/* The element to be centered, can also be of any width and height */
.centered {
  <b>display</b>: inline-block;
  <b>vertical-align</b>: middle;
  <b>width</b>: 300px;
  <b>white-space</b>: normal; /* Resetting inherited nowrap behavior */
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;block&quot;<b>&gt;</b>
  <b>div</b> class=&quot;centered&quot;<b>&gt;&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="6-11">Section 6.11: Centering vertically and horizontally without worrying about height or width</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The following technique allows you to add your content to an HTML
element and center it both horizontally and vertically <b>without
worrying about its height or width</b>.</p>

<h4>The outer container</h4>
<ul>
  <li>should have <b>display</b>: table;</li>
</ul>

<h4>The inner container</h4>

<ul>
  <li>should have <b>display</b>: table-cell;</li>
  <li>should have <b>vertical-align</b>: middle;</li>
  <li>should have <b>text-align</b>: center;</li>
</ul>

<h4>The content box:</h4>
<ul>
  <li>should have <b>display</b>: inline-block;</li>
  <li>should re-adjust the horizontal text-alignment to eg. <b>text-align</b>:
  left; or <b>text-align</b>: right;, unless you want text to be centered</li>
</ul>

<h4>Demo:</h4>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;outer-container&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;inner-container&quot;<b>&gt;</b>
    <b>&lt;div</b> class=&quot;centered-content&quot;<b>&gt;</b>
      You can put anything here!
    <b>&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>body {
  <b>margin</b>: 0;
}
.outer-container {
  <b>position</b>: absolute;
  <b>display</b>: table;
  <b>width</b>: 100&percnt;;  /* This could be ANY width */
  <b>height</b>: 100&percnt;; /* This could be ANY height */
  <b>background</b>: #ccc;
}
.inner-container {
  <b>display</b>: table-cell;
  <b>vertical-align</b>: middle;
  <b>text-align</b>: center;
}
.centered-content {
  <b>display</b>: inline-block;
  <b>text-align</b>: left;
  <b>background</b>: #fff;
  <b>padding</b>: 20px;
  <b>border</b>: 1px solid #000;
}</code></pre>

<p>See also <a href="http://jsfiddle.net/WXLsY/621/">this jsFiddle!</a></p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-12">Section 6.12: Vertically align an image inside div</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;wrap&quot;<b>&gt;</b>
  <b>&lt;img</b> src=&quot;http://lorempixel.com/400/200/&quot;<b>/&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code>.wrap {
  <b>height</b>: 50px; /* max image height */
  <b>width</b>: 100px;
  <b>border</b>: 1px solid blue;
  <b>text-align</b>: center;
}
.wrap:before {
  <b>content</b>:&quot;&quot;;
  <b>display</b>: inline-block;
  <b>height</b>: 100&percnt;;
  <b>vertical-align</b>: middle;
  <b>width</b>: 1px;
}

img {
  <b>vertical-align</b>: middle;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-13">Section 6.13: Centering with fixed size</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>If the size of your content is fixed, you can use absolute positioning to 50% 
with margin that reduces half of your content&apos;s width and height:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;center&quot;<b>&gt;</b>
  Center vertically and horizontally
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.center {
  <b>position</b>: absolute;
  <b>background</b>: #ccc;

  <b>left</b>: 50&percnt;;
  <b>width</b>: 150px;
  <b>margin-left</b>: -75px;  /* width &ast; -0.5 */

  <b>top</b>: 50&percnt;;
  <b>height</b>: 200px;
  <b>margin-top</b>: -100px;  /* height &ast; -0.5 */
}</code></pre>

<h4>Horizontal centering with only fixed width</h4>

<p>You can center the element horizontally even if you don&apos;t know the height 
of the content:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;center&quot;<b>&gt;</b>
  Center only horizontally
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.center {
  <b>position</b>: absolute;
  <b>background</b>: #ccc;
  
  <b>left</b>: 50&percnt;;
  <b>width</b>: 150px;
  <b>margin-left</b>: -75px;  /* width &ast; -0.5 */
}</code></pre>

<h4>Vertical centering with fixed height</h4>

<p>You can center the element vertically if you know the element&apos;s height:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;center&quot;<b>&gt;</b>
  Center only vertically
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.center {
  <b>position</b>: absolute;
  <b>background</b>: #ccc;
  
  <b>top</b>:50&percnt;;
  <b>height</b>: 200px;
  <b>margin-top</b>: -100px;  /* width &ast; -0.5 */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-14">Section 6.14: Vertically align dynamic height elements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Applying css intuitively doesn&apos;t produce the desired results because;</p>
<ul>
  <li><b>vertical-align</b>:middle <a href="http://www.w3.org/TR/CSS21/visudet.html#propdef-vertical-align">
    isn&apos;t applicable to block-level elements</a></li>
  <li><b>margin-top</b>:auto and <b>margin-bottom</b>:auto 
    <a href="http://www.w3.org/TR/CSS2/visudet.html#Computing_heights_and_margins">
	used values would compute as zero</a></li>
  <li><b>margin-top</b>:-50% <a href="http://www.w3.org/TR/CSS2/box.html#margin-properties">
    percentage-based margin values are calculated relative to the width of containing block</a></li>
</ul>

<p>For widest browser support, a workaround with helper elements:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=<span style="color:red;">&quot;vcenter&minus;-container&quot;</span><b>&gt;</b>
  <b>&lt;div</b> class=<span style="color:red;">&quot;vcenter&minus;-helper&quot;</span><b>&gt;</b>
    <b>&lt;div</b> class=<span style="color:red;">&quot;vcenter&minus;-content&quot;</span><b>&gt;</b>
      &lt;!-- stuff --&gt;
    <b>&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><center>.vcenter &minus;- container {
  <b>display</b>: table;
  <b>height</b>: 100&percnt;;
  <b>position</b>: absolute;
  <b>overflow</b>: hidden;
  <b>width</b>: 100&percnt;;
}
.vcenter &minus;- helper {
  <b>display</b>: table-cell;
  <b>vertical-align</b>: middle;
}
.vcenter &minus;- content {
  <b>margin</b>: 0 auto;
  <b>width</b>: 200px;
}</center></pre>

<a href="http://jsfiddle.net/ovfiddle/yVAW9/">Demo (jsFiddle)</a> from
<a href="http://stackoverflow.com/a/12417336/1081234">original question</a>.

<p>This approach;</p>

<ul>
  <li>works with dynamic height elements,</li>
  <li>respects content flow,</li>
  <li>is supported by legacy browsers.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-15">Section 6.15: Horizontal and Vertical centering using table layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>One could easily center a child element using table display property.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=<span style="color:red;">&quot;wrapper&quot;</span><b>&gt;</b>
  <b>&lt;div</b> class=<span style="color:red;">&quot;parent&quot;</span><b>&gt;</b>
    <b>&lt;div</b> class=<span style="color:red;">&quot;child&quot;</span><b>&gt;&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.wrapper {
  <b>display</b>: table;
  <b>vertical-align</b>: center;
  <b>width</b>: 200px;
  <b>height</b>: 200px;
  <b>background-color</b>: #9e9e9e;
}
.parent {
  <b>display</b>: table-cell;
  <b>vertical-align</b>: middle;
  <b>text-align</b>: center;
}
.child {
  <b>display</b>: inline-block;
  <b>vertical-align</b>: middle;
  <b>text-align</b>: center;
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>background-color</b>: teal;
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch7">Chapter 7: The Box Model</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b> | <b>Detail</b> |
|------------------|---------------------------------------------|
| content-box | Width and height of the element only includes content area. |
| padding-box | Width and height of the element includes content and padding. |
| border-box  | Width and height of the element includes content, padding and border. |
| initial | Sets the box model to its default state. |
| inherit | Inherits the box model of the parent element. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch7-1">Section 7.1: What is the Box Model?</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>The Edges</h4>

<p>The browser creates a rectangle for each element in the HTML document.
The Box Model describes how the padding, border, and margin are added
to the content to create this rectangle.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~ 16. box-model: margin, border, padding & content (51) ~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image016.png"
  style="width:50%"
  title="Box-model: margin, border, padding &amp; content"
  alt="Box-model: margin, border, padding &amp; content." />
</p>
<!-- [image016.png](./images/image016.png)  <!-- 4.7" -->

<p>Diagram from <a href="https://www.w3.org/TR/CSS22/box.html#mpb-examples">CSS2.2 Working Draft Demo</a>.</p>

<p>The perimeter of each of the four areas is called an <i>edge</i>. Each edge defines a <i>box</i>.</p>

<ul>
  <li>The innermost rectangle is the <b>content box</b>. The width and height of 
    this depends on the element&apos;s rendered content (text, images and any 
	child elements it may have).</li>
  <li>Next is the <b>padding box</b>, as defined by the padding property. If there 
    is no padding width defined, the padding edge is equal to the content edge.</li>
  <li>Then we have the <b>border box</b>, as defined by the border property. If there 
    is no border width defined, the border edge is equal to the padding edge.</li>
  <li>The outermost rectangle is the <b>margin box</b>, as defined by the margin 
    property. If there is no margin width defined, the margin edge is equal to the 
	border edge.</li>
</ul>

<h4>Example:</h4>

<pre><code>div {
  <b>border</b>: 5px solid #ff0000;
  <b>margin</b>: 50px;
  <b>padding</b>: 20px;
}</code></pre>

<p>This CSS styles all div elements to have a top, right, bottom and left
border of 5px in width; a top, right, bottom and left margin of 50px;
and a top, right, bottom, and left padding of 20px. Ignoring content,
our generated box will look like this:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~ 17. generated box from border 5px, margin 50px, and padding 20px (52) ~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image017.jpg"
  style="width:20%"
  title="Generated box from border 5px, margin 50px, and padding 20px"
  alt="Generated box from border 5px, margin 50px, and padding 20px." />
</p>
<h6><i>Screenshot of Google Chrome&apos;s Element Styles panel</i></h6>

<ul>
  <li>As there is no content, the content region (the blue box in the middle) has no height or width (0px by 0px).</li>
  <li>The padding box by default is the same size as the content box, plus the 20px width on all four edges we&apos;re
    defining above with the padding property (40px by 40px).</li>
  <li>The border box is the same size as the padding box, plus the 5px width we&apos;re defining above with the border
    property (50px by 50px).</li>
  <li>Finally the margin box is the same size as the border box, plus the 50px width we&apos;re defining above with the 
    margin property (giving our element a total size of 150px by 150px).</li>
</ul>

<p>Now lets give our element a sibling with the same style. The browser
looks at the Box Model of both elements to work out where in relation
to the previous element&apos;s content the new element should be
positioned:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~ 18. separate images with 150px gap (52) ~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image018.jpg"
  style="width:40%"
  title="Separate images with 150px gap of padding+border+margin"
  alt="Separate images with 150px gap of padding+border+margin." />
</p>
<!-- [image018.jpg 3.6" width, 1.5" height](./images/image018.jpg) -->

<p>The content of each of element is separated by a 150px gap, but the
two elements&apos; boxes touch each other.</p>

<p>If we then modify our first element to have no right margin, the right
margin edge would be in the same position as the right border edge,
and our two elements would now look like this:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 19. Remove right margin from 1st image (52) ~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image019.jpg"
  style="width:40%"
  title="Remove right margin from 1st image"
  alt="Remove right margin from 1st image." />
</p>
<!-- [image019.jpg 3.45" x 1.54"](./images/image019.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch7-2">Section 7.2: box-sizing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The default box model (content-box) can be counter-intuitive, since
the width / height for an element will not represent its actual width
or height on screen as soon as you start adding padding and border
styles to the element.</p>

<p>The following example demonstrates this potential issue with
content-box:</p>

<pre><code>
textarea {
  <b>width</b>: 100&percnt;;
  <b>padding</b>: 3px;
  <b>box-sizing</b>: content-box; /* default value */
}
</code></pre>

<p>Since the padding will be added to the width of the textarea, the
resulting element is a textarea that is wider than 100%.</p>

<p>Fortunately, CSS allows us to change the box model with the box-sizing
property for an element. There are three different values for the
property available:</p>

<ul>
  <li>content-box: The common box model - width and height only includes the
    content, not the padding or border.</li>
  <li>padding-box: Width and height includes the content and the padding, but 
    not the border.</li>
  <li>border-box: Width and height includes the content, the padding as well as 
    the border.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~ 20. content, padding, border, and margin (53) ~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image020.png"
  style="width:60%"
  title="content, padding, border, and margin"
  alt="content, padding, border, and margin." />
</p>

<p>To solve the textarea problem above, you could just change the
box-sizing property to padding-box or borderbox. border-box is most
commonly used.</p>

<pre><code>textarea {
  <b>width</b>: 100&percnt;;
  <b>padding</b>: 3px;
  <b>box-sizing</b>: border-box;
}</code></pre>

<p>To apply a specific box model to every element on the page, use the following 
snippet:</p>

<pre><code>html {
  <b>box-sizing</b>: border-box;
}

&ast;, &ast;:before, &ast;:after {
  <b>box-sizing</b>: inherit;
}</code></pre>

<p>In this coding <b>box-sizing</b>: border-box; is not directly applied to &ast;, so you can easily
overwrite this property on individual elements.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch8">Chapter 8: Margins</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b>  | <b>Details</b> |
|-------------------|------------------------------------------------------------------|
| 0                 | set margin to none. |
| auto              | used for centering, by evenly setting values on each side units. |
| units (e.g. px)   | see parameter section in Units for a list of valid units.
| inherit           | inherit margin value from parent element. 
| initial           | restore to initial value. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-1">Section 8.1: Margin Collapsing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When two margins are touching each other vertically, they are
collapsed. When two margins touch horizontally, they do not collapse.</p>

<h4>Example of adjacent vertical margins:</h4>

<p>Consider the following styles and markup:</p>

<pre><code>div {
  <b>margin</b>: 10px;
}
<b>&lt;div&gt;</b>
  some content
<b>&lt;/div&gt;</b>
<b>&lt;div&gt;</b>
  some more content
<b>&lt;/div&gt;</b></code></pre>

<p>They will be 10px apart since vertical margins collapse over one and
other. (The spacing will not be the sum of two margins.)</p>

<h4>Example of adjacent horizontal margins:</h4>

<p>Consider the following styles and markup:</p>

<pre><code>span {
  <b>margin</b>: 10px;
}
<b>&lt;span&gt;</b>some<b>&lt;/span&gt;&lt;span&gt;</b>content<b>&lt;/span&gt;</b></code></pre>

<p>They will be 20px apart since horizontal margins don&apos;t collapse over
one and other. (The spacing will be the sum of two margins.)</p>

<h4>Overlapping with different sizes</h4>

<pre><code>.top {
  <b>margin</b>: 10px;
}
.bottom {
 <b>margin</b>: 15px;
}
<b>&lt;div</b> class = &quot;top&quot;<b>&gt;</b>
  some content
<b>&lt;/div&gt;</b>
<b>&lt;div</b> class = &quot;bottom&quot;<b>&gt;</b>
  some more content
<b>&lt;/div&gt;</b></code></pre>

<p>These elements will be spaced 15px apart vertically. The margins
overlap as much as they can, but the larger margin will determine the
spacing between the elements.</p>

<h4>Overlapping margin gotcha</h4>

<pre><code>.outer-top {
  <b>margin</b>: 10px;
}
.inner-top {
  <b>margin</b>: 15px;
}
.outer-bottom {
  <b>margin</b>: 20px;
}
.inner-bottom {
  <b>margin</b>: 25px;
}
<b>&lt;div</b> class =<span style="color:red;">&quot;outer-top&quot;</span><b>&gt;</b>
    <b>&lt;div</b> class=<span style="color:red;">&quot;inner-top&quot;</span><b>&gt;</b>
      some content
    <b>&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=<span style="color:red;">&quot;outer-bottom&quot;</span><b>&gt;</b>
    <b>&lt;div</b> class=<span style="color:red;">&quot;inner-bottom&quot;</span><b>&gt;</b>
      some more content
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>What will be the spacing between the two texts? (hover to see answer)</p>

<blockquote>
  The spacing will be 25px. Since all four margins are touching each
  other, they will collapse, thus using the largest margin of the four.
</blockquote>

<p>Now, what about if we add some borders to the markup above.</p>

<pre><code>div {
  <b>border</b>: 1px solid #ff0000;
}</code></pre>

<p>What will be the spacing between the two texts? (hover to see answer)</p>

<blockquote>
  The spacing will be 59px! Now only the margins of .outer-top and
  .outer-bottom touch each other, and are the only collapsed margins.
  The remaining margins are separated by the borders. So we have 1px +
  10px + 1px + 15px + 20px + 1px + 25px + 1px. (The 1px&apos;s are the
  borders&period;..)
</blockquote>

<h4>Collapsing Margins Between Parent and Child Elements:</h4>

<h4>HTML::</h4>

<pre><code><b>&lt;h1&gt;</b>Title<b>&lt;/h1&gt;</b>
<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>Paragraph<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>h1 {
  <b>margin</b>: 0;
  <b>background</b>: #cff;
}
div {
  <b>margin</b>: 50px 0 0 0;
  <b>background</b>: #cfc;
}
p {
  <b>margin</b>: 25px 0 0 0;
  <b>background</b>: #cf9;
}</code></pre>

<p>In the example above, only the largest margin applies. You may have
expected that the paragraph would be located 60px from the h1 (since
the div element has a margin-top of 40px and the p has a 20px
margin-top). This does not happen because the margins collapse
together to form one margin.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-2">Section 8.2: Apply Margin on a Given Side</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Direction-Specific Properties</h4>

<p>CSS allows you to specify a given side to apply margin to. The four
properties provided for this purpose are:</p>

<ul>
  <li>margin-left</li>
  <li>margin-right</li>
  <li>margin-top</li>
  <li>margin-bottom</li>
</ul>

<p>The following code would apply a margin of 30 pixels to the left side
of the selected div. <a href="https://jsfiddle.net/wm0100x9/1/">View Result</a>.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;myDiv&quot;<b>&gt;&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>#myDiv {
  <b>margin-left</b>: 30px;
  <b>height</b>: 40px;
  <b>width</b>: 40px;
  <b>background-color</b>: #ff0000;
}</code></pre>

| <b>Parameter</b> | <b>Details</b> |
|------------------|-------------------------------------------------|
| margin-left | The direction in which the margin should be applied. |
| 30px | The width of the margin. |

<h4>Specifying Direction Using Shorthand Property</h4>

<p>The standard margin property can be expanded to specify differing
widths to each side of the selected elements. The syntax for doing
this is as follows:</p>

<pre><code><b>margin</b>: &lt;top&gt; &lt;right&gt; &lt;bottom&gt; &lt;left&gt;;</code></pre>

<p>The following example applies a zero-width margin to the top of the
div, a 10px margin to the right side, a 50px margin to the left side,
and a 100px margin to the left side. <a href="https://jsfiddle.net/1979c947/"><i>View
Result</i>.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;myDiv&quot;<b>&gt;&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>#myDiv {
  <b>margin</b>: 0 10px 50px 100px;
  <b>height</b>: 40px;
  <b>width</b>: 40px;
  <b>background-color</b>: #ff0000;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-3">Section 8.3: Margin property simplification</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>p {
  <b>margin</b>: 1px; /* 1px margin in all directions */
  /* equal to: */
  <b>margin</b>: 1px 1px;
  /* equal to: */
  <b>margin</b>: 1px 1px 1px;
  /* equal to: */
  <b>margin</b>: 1px 1px 1px 1px;
}</code></pre>

<p>Another exapmle:</p>

<pre><code>p {
  <b>margin</b>: 10px 15px; /* 10px margin-top & bottom And 15px margin-right & left */
  /* equal to: */
  <b>margin</b>: 10px 15px 10px 15px;
  /* equal to: */
  <b>margin</b>: 10px 15px 10px;
  /* margin left will be calculated from the margin right value (=15px) */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-4">Section 8.4: Horizontally center elements on a page using margin</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>As long as the element is a <b>block</b>, and it has an <b>explicitly set
width value</b>, margins can be used to center block elements on a page
horizontally.</p>

<p>We add a width value that is lower than the width of the window and
the auto property of margin then distributes the remaining space to
the left and the right:</p>

<pre><code>#myDiv {
  <b>width</b>:80&percnt;;
  <b>margin</b>:0 auto;
}</code></pre>

<p>In the example above we use the shorthand margin declaration to first
set 0 to the top and bottom margin values (although this could be any
value) and then we use auto to let the browser allocate the space
automatically to the left and right margin values.</p>

<p>In the example above, the #myDiv element is set to 80% width which
leaves use 20% leftover. The browser distributes this value to the
remaining sides so:</p>

<pre><code>(100% - 80%) / 2 = 10%</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-5">Section 8.5: Example 1:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>It is obvious to assume that the percentage value of margin to
margin-left and margin-right would be relative to its parent element.</p>

<pre><code>.parent {
  <b>width</b> : 500px;
  <b>height</b>: 300px;
}
.child {
  <b>width</b> : 100px;
  <b>height</b>: 100px;
  <b>margin-left</b>: 10&percnt;; /* (parentWidth &ast; 10/100) =&gt; 50px */
}</code></pre>

<p>But that is not the case, when comes to margin-top and margin-bottom.
Both these properties, in percentages, aren&apos;t relative to the height
of the parent container but to the <b>width</b> of the parent container.</p>

<p>So,</p>

<pre><code>.parent {
  <b>width</b> : 500px;
  <b>height</b>: 300px;
}
.child {
  <b>width</b> : 100px;
  <b>height</b>: 100px;
  <b>margin-left</b>: 10&percnt;;  /* (parentWidth &ast; 10/100) =&gt; 50px */
  <b>margin-top</b>: 20&percnt;;   /* (parentWidth &ast; 20/100) =&gt; 100px */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-6">Section 8.6: Negative margins</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Margin is one of a few CSS properties that can be set to negative
values. This property can be used to <b>overlap elements without
absolute positioning</b>.</p>

<pre><code>div {
  <b>display</b>: inline;
}
#over {
  <b>margin-left</b>: -20px;
}
&lt;div&gt;Base div&lt;/div&gt;
&lt;div id=&quot;over&quot;&gt;Overlapping div&lt;/div&gt;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch9">Chapter 9: Padding</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch9-1">Section 9.1: Padding Shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The padding property sets the padding space on all sides of an
element. The padding area is the space between the content of the
element and its border. Negative values are not allowed.</p>

<p>To save adding padding to each side individually (using padding-top,
padding-left etc) can you write it as a shorthand, as below:</p>

<h4><b>Four values:</b></h4>

<pre><code><b>&lt;style&gt;</b>
  .myDiv {
    padding: 25px 50px 75px 100px; /* top right bottom left; */
  }
<b>&lt;/style&gt;</b>
<b>&lt;div</b> class=<span style="color:red;">&quot;myDiv&quot;</span><b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~ 21a. padding: 25, 50, 75 100px (61) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image021a.png"
  style="width:15%"
  title="padding: 25, 50, 75, 100px"
  alt="padding: 25, 50, 75, 100px." />
</p>

<h4><b>Three values:</b></h4>

<pre><code><b>&lt;style&gt;</b>
  .myDiv {
    padding: 25px 50px 75px; /* top left/right bottom */
  }
  <b>&lt;/style&gt;</b>
<b>&lt;div</b> class=<span style="color:red;">&quot;myDiv&quot;</span><b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~ 21b. padding: 25, 50, 75, 50px (61) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image021b.png"
  style="width:15%"
  title="padding: 25, 50, 75, 50px"
  alt="padding: 25, 50, 75, 50px." />
</p>

</h4><b>Two values:</b></h4>

<pre><code><b>&lt;style&gt;</b>
  .myDiv {
    padding: 25px 50px; /* top/bottom left/right */
  }
<b>&lt;/style&gt;</b>
<b>&lt;div</b> class=<span style="color:red;">&quot;myDiv&quot;</span><b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~ 21c. padding: 25, 50, 25, 50px (61) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image021c.png"
  style="width:15%"
  title="padding: 25, 50, 25, 50px"
  alt="padding: 25, 50, 25, 50px." />
</p>

<h4><b>One value:</b></h4>

<pre><code><b>&lt;style&gt;</b>
  .myDiv {
    padding: 25px; /* top/right/bottom/left */
}
<b>&lt;/style&gt;</b>
<b>&lt;div</b> class=<span style="color:red;">&quot;myDiv&quot;</span><b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~ 21d. padding: 25, 25, 25, 25px (62) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image021d.png"
  style="width:15%"
  title="padding: 25, 25, 25, 25px"
  alt="padding: 25, 25, 25, 25px." />
</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch9-2">Section 9.2: Padding on a given side</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The padding property sets the padding space on all sides of an
element. The padding area is the space between the content of the
element and its border. Negative values are not allowed.</p>

<p>You can specify a side individually:</p>

<ul>
  <li>padding-top </li>
  <li>padding-right</li>
  <li>padding-bottom</li>
  <li>padding-left</li>
</ul>

<p>The following code would add a padding of 5px to the top of the div:</p>

<pre><code><b>&lt;style&gt;</b>
  .myClass {
    padding-top: 5px;
}
<b>&lt;/style&gt;</b>
<b>&lt;div</b> class=<span style="color:red;">&quot;myClass&quot;</span><b>&gt;&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch10">Chapter 10: Border</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-1">Section 10.1: border-radius</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-radius property allows you to change the shape of the basic
box model.</p>

<p>Every corner of an element can have up to two values, for the vertical
and horizontal radius of that corner (for a maximum of 8 values).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 25. border top left radius (63) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image025.jpg"
  style="width:60%"
  title="Border top left radius"
  alt="Border top left radius." />
</p>
<!-- [image025.jpg 6.14 x 1.93](./images/image025.jpg) -->

<p>The first set of values defines the horizontal radius. The optional
second set of values, preceded by a '/' , defines the vertical radius.
If only one set of values is supplied, it is used for both the
vertical and horizontal radius.</p>

<pre><code><b>border-radius</b>: 10px 5&percnt; / 20px 25em 30px 35em;</code></pre>

<p>The 10px is the horizontal radius of the top-left-and-bottom-right.
And the 5% is the horizontal radius of the topright-and-bottom-left.
The other four values after &apos;/&apos; are the vertical radii for top-left,
top-right, bottom-right and bottom-left.</p>

<p>As with many CSS properties, shorthands can be used for any or all
possible values. You can therefore specify anything from one to eight
values. The following shorthand allows you to set the horizontal and
vertical radius of every corner to the same value:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=<span style="color:red;">&apos;box&apos;</span><b>&gt;&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.box {
  <b>width</b>: 250px;
  <b>height</b>: 250px;
  <b>background-color</b>: black;
  <b>border-radius</b>: 10px;
}</code></pre>

<p>Border-radius is most commonly used to convert box elements into
circles. By setting the border-radius to half of the length of a
square element, a circular element is created:</p>

<pre><code>.circle {
  <b>width</b>: 200px;
  <b>height</b>: 200px;
  <b>border-radius</b>: 100px;
}</code></pre>

<p>Because border-radius accepts percentages, it is common to use 50% to
avoid manually calculating the borderradius value:</p>

<pre><code>.circle {
  <b>width</b>: 150px;
  <b>height</b>: 150px;
  <b>border-radius</b>: 50&percnt;;
}</code></pre>

<p>If the width and height properties are not equal, the resulting shape
will be an oval rather than a circle.</p>

<p>Browser specific border-radius example:</p>

<pre><code>-webkit-border-top-right-radius: 4px;
-webkit-border-bottom-right-radius: 4px;
-webkit-border-bottom-left-radius: 0;
-webkit-border-top-left-radius: 0;
-moz-border-radius-topright: 4px;
-moz-border-radius-bottomright: 4px;
-moz-border-radius-bottomleft: 0;
-moz-border-radius-topleft: 0;
<b>border-top-right-radius</b>: 4px;
<b>border-bottom-right-radius</b>: 4px;
<b>border-bottom-left-radius</b>: 0;
<b>border-top-left-radius</b>: 0;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-2">Section 10.2: border-style</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-style property sets the style of an element&apos;s border. This
property can have from one to four values (for every side of the
element one value.)</p>

<h4>Examples:</h4>

<pre><code><b>border-style</b>: dotted;
<b>border-style</b>: dotted solid double dashed;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~ 26. border-style property sets the style of an element's border (64) ~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image026.png"
  style="width:60%"
  title="border-style property sets the style of an element's border"
  alt="border-style property sets the style of an element's border." />
</p>

<p>border-style can also have the values none and hidden. They have the
same effect, except hidden works for <b>&lt;table&gt;</b> elements. In a
<b>&lt;table&gt;</b> with multiple borders, none has the lowest priority 
(meaning in a conflict, the border would show), and hidden has the
highest priority (meaning in a conflict, the border would not show).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-3">Section 10.3: Multiple Borders</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Using outline:</p>

<pre><code>.div1 {
  <b>border</b>: 3px solid black;
  <b>outline</b>: 6px solid blue;
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>margin</b>: 20px;
}</code></pre>

<p>Using box-shadow:</p>

<pre><code>.div2 {
  <b>border</b>: 5px solid green;
  <b>box-shadow</b>: 0px 0px 0px 4px #000;
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>margin</b>: 20px;
}</code></pre>

<p>Using a pseudo element:</p>

<pre><code>.div3 {
  <b>position</b>: relative;
  <b>border</b>: 5px solid #000;
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>margin</b>: 20px;
}
.div3:before {
  <b>content</b>: &quot; &quot;;
  <b>position</b>: absolute;
  <b>border</b>: 5px solid blue;
  <b>z-index</b>: &minus;1;
  <b>top</b>: 5px;
  <b>left</b>: 5px;
  <b>right</b>: 5px;
  <b>bottom</b>: 5px;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 27. 3 div border examples (66) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image027.jpg"
  style="width:15%"
  title="3 div border examples"
  alt="3 div border examples." />
</p>
<!-- [image027.jpg 1.458 x 4.021](./images/image027.jpg) -->

<a href="http://jsfiddle.net/MadalinaTn/bvqpcohm/2/&rbrack;&rbrack;(http://jsfiddle.net/MadalinaTn/bvqpcohm/2/">jsFiddle Demo</a>.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-4">Section 10.4: border (shorthands)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>In most cases you want to define several border properties
(border-width, border-style and border-color) for all sides of an
element.</p>

<p>Instead of writing:</p>

<pre><code><b>border-width</b>: 1px;
<b>border-style</b>: solid;
<b>border-color</b>: #000;</code></pre>

<p>You can simply write:</p>

<pre><code><b>border</b>: 1px solid #000;</code></pre>

<p>These shorthands are also available for every side of an element:
border-top, border-left, border-right and border-bottom. So you can
do:</p>

<pre><code><b>border-top</b>: 2px double #aaaaaa;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-5">Section 10.5: border-collapse</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-collapse property applies only to tables (and elements
displayed as or inlinetable) and sets whether the table borders are
collapsed into a single border or detached as in standard HTML.</p>

<pre><code>table {
  <b>border-collapse</b>: separate; /* default */
  <b>border-spacing</b>: 2px; /* Only works if border-collapse is separate */
}</code></pre>

<p>Also see Tables - border-collapse documentation entry</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-6">Section 10.6: border-image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>With the border-image property you have the possibility to set an
image to be used instead of normal border styles.</p>

<p>A border-image essentially consist of a</p>

<ul>
  <li>border-image-source: The path to the image to be used</li>
  <li>border-image-slice: Specifies the offset that is used to divide the image 
    into <b>nine regions</b> (four <b>corners</b>, four <b>edges</b> and a 
	<b>middle</b>)</li>
  <li>border-image-repeat: Specifies how the images for the sides and the middle 
    of the border image are scaled</li>
</ul>

<p>Consider the following example wheras border.png is a image of 90x90 pixels:</p>

<pre><code><b>border-image</b>: url(&quot;border.png&quot;) 30 stretch;</code></pre>

<p>The image will be split into nine regions with 30x30 pixels. The edges
will be used as the corners of the border while the side will be used
in between. If the element is higher / wider than 30px this part of
the image will be <b>stretched</b>. The middle part of the image defaults
to be transparent.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-7">Section 10.7: Creating a multi-colored border using borderimage</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>CSS:</h4>

<pre><code>.bordered {
  <b>border-image</b>: linear-gradient(to right, red 20&percnt;, green 20&percnt;, green 40&percnt;, blue 40&percnt;, blue 60&percnt;, maroon 
  60&percnt;, maroon 80&percnt;, chocolate 80&percnt;); /* gradient with required colors */
  <b>border-image-slice</b>: 1;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=<span style="color:red;">&apos;bordered&apos;</span><b>&gt;</b>Border on all sides<b>&lt;/div&gt;</b></code></pre>

<p>The above example would produce a border that comprises of 5 different
colors. The colors are defined through a linear-gradient (you can find
more information about gradients in the docs). You can find more
information about border-image-slice property in the border-image
example in same page.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 28. border on all sides (67) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image028.png"
  style="width:35%"
  title="Border on ALL sides"
  alt="Border on ALL sides." />
</p>
<!-- [image028.jpg 3.5"x1.437"] -->

<h6><i>(Note: Additional properties were added to the element for presentational purpose.)</i></h6>

<p>You&apos;d have noticed that the left border has only a single color (the
start color of the gradient) while the right border also has only a
single color (the gradient&apos;s end color). This is because of the way
that border image property works. It is as though the gradient is
applied to the entire box and then the colors are masked from the
padding and content areas, thus making it look as though only the
border has the gradient.</p>

<p>Which border(s) have a single color is dependant on the gradient
definition. If the gradient is a gradient, the left border would be
the start color of the gradient and right border would be the end
color. If it was a to bottom gradient the top border would be the
gradient&apos;s start color and bottom border would be end color. Below is
the output of a bottom 5 colored gradient.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~ 29. bottom 5 colored gradient (68) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image029.png"
  style="width:35%"
  title="Bottom 5 colored gradient"
  alt="Bottom 5 colored gradient." />
</p>
<!-- [image029.jpg 3.489 x 1.40]-->

<p>If the border is required only on specific sides of the element then
the border-width property can be used just like with any other normal
border. For example, adding the below code would produce a border only
on the top of the element.</p>

<pre><code><b>border-width</b>: 5px 0px 0px 0px;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~ 30. border-width: 5px 0px 0px 0px (68) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image030.png"
  style="width:35%"
  title="border-width: 5px 0px 0px 0px"
  alt="border-width: 5px 0px 0px 0px." />
</p>
<p>Note that, any element that has border-image property <b>won&apos;t respect
the</b> border-radius (that is the border won&apos;t curve). This is based
on the below statement in the spec:</p>

<blockquote>
  A box&apos;s backgrounds, but not its border-image, are clipped to the
  appropriate curve (as determined by 'background-clip').
</blockquote>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-8">Section 10.8: border-&lbrack;left&vert;right&vert;top&vert;bottom&rbrack;</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-&lbrack;left&vert;right&vert;top&vert;bottom&rbrack; 
property is used to add a border to a specific side of an element.</p>

<p>For example if you wanted to add a border to the left side of an element, you could do:</p>

<pre><code>&num;element {
  <b>border-left</b>: 1px solid black;
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch11">Chapter 11: Outlines</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b> | <b>Details</b> |
|------------------|-----------------------------------------------|
| dotted           | dotted outline |
| dashed           | dashed outline |
| solid |       solid outline |
| double |      double outline |
| groove |      3D grooved outline, depends on the outline-color value |
| ridge  |      3D ridged outline, depends on the outline-color value |
| inset |       3D inset outline, depends on the outline-color value |
|  outset  |     3D outset outline, depends on the outline-color value |
|  none    |     no outline |
|  hidden  |     hidden outline |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch11-1">Section 11.1: Overview</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Outline is a line that goes around the element, outside of the border.
In contrast to border, outlines do not take any space in the box
model. So adding an outline to an element does not affect the position
of the element or other elements.</p>

<p>In addition, outlines can be non-rectangular in some browsers. This
can happen if outline is applied on a span element that has text with
different font-size properties inside it. Unlike borders, outlines
<i>cannot</i> have rounded corners.</p>

<p>The essential parts of outline are outline-color, outline-style and
outline-width.</p>

<p>The definition of an outline is equivalent to the definition of a
border:</p>

<blockquote>
  An outline is a line around an element. It is displayed around the
  margin of the element. However, it is different from the border property.
</blockquote>

<pre><code><b>outline</b>: 1px solid black;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch11-2">Section 11.2: outline-style</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The outline-style property is used to set the style of the outline of
an element.</p>

<pre><code>p {
  <b>border</b>: 1px solid black;
  <b>outline-color</b>: blue;
  <b>line-height</b>: 30px;
}
.p1 {
  <b>outline-style</b>: dotted;
}
.p2 {
  <b>outline-style</b>: dashed;
}
.p3 {
  <b>outline-style</b>: solid;
}
.p4 {
  <b>outline-style</b>: double;
}
.p5 {
  <b>outline-style</b>: groove;
}
.p6 {
  <b>outline-style</b>: ridge;
}
.p7 {
  <b>outline-style</b>: inset;
}
.p8 {
  <b>outline-style</b>: outset;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;p</b> class=&quot;p1&quot;<b>&gt;</b>A dotted outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p2&quot;<b>&gt;</b>A dashed outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p3&quot;<b>&gt;</b>A solid outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p4&quot;<b>&gt;</b>A double outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p5&quot;<b>&gt;</b>A groove outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p6&quot;<b>&gt;</b>A ridge outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p7&quot;<b>&gt;</b> An inset outline<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;p8&quot;<b>&gt;</b> An outset outline<b>&lt;/p&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~ 31. outline-style's 8 options (70) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image031.png"
  style="width:50%"
  title="outline-style's 8 options"
  alt="outline-style's; 8 options." />
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch12">Chapter 12: Overflow</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Overflow Value</b> | <b>Details</b>                           |
|----------------------|-------------------------------------------|
| visible | Shows all overflowing content outside the element |
| scroll  | Hides the overflowing content and adds a scroll bar |
| hidden  | Hides the overflowing content, both scroll bars disappear and the page becomes fixed |
| auto    | Same as scroll if content overflows, but doesn&apos;t add scroll bar if content fits |
| inherit | Inherit&apos;s the parent element&apos;s value for this property |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-1">Section 12.1: overflow-wrap</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>overflow-wrap tells a browser that it can break a line of text inside
a targeted element onto multiple lines in an otherwise unbreakable
place. Helpful in preventing an long string of text causing layout
problems due to overflowing it&apos;s container.</p>

<h4>CSS:</h4>

<pre><code>div {
  <b>width</b>: 100px;
  <b>outline</b>: 1px dashed #bbb;
}
#div1 {
  <b>overflow-wrap</b>:normal;
}
#div2 {
  <b>overflow-wrap</b>:break-word;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;div1&quot;<b>&gt;</b>
  <b>&lt;strong&gt;</b>#div1<b>&lt;/strong&gt;</b>: Small words are displayed normally, but a long word like <b>&lt;span</b> 
     style=&quot;red;&quot;<b>&gt;</b>supercalifragilisticexpialidocious<b>&lt;/span&gt;</b> is too long so it will overflow past the
     edge of the line-break
<b>&lt;/div&gt;</b>

<b>&lt;div</b> id=&quot;div2&quot;<b>&gt;</b>
  <b>&lt;strong&gt;</b>#div2<b>&lt;/strong</b>: Small words are displayed normally, but a long word like <b>&lt;span</b>
    style=&quot;red;&quot;<b>&gt;</b>supercalifragilisticexpialidocious<b>&lt;/span&gt;</b> will be split at the line break and continue
    on the next line.
<b>&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 32. div, overflow-wrap (72) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image032.jpg"
  style="width:75%"
  title="div, overflow-wrap"
  alt="div, overflow-wrap." />
</p>
<!--[image032.jpg 7.48 x 4.27](./images/image032.jpg) -->

| <b>overflow-wrap -- Value</b> | <b>Details</b> |
|------------|-----------------|
| normal     | Lets a word overflow if it is longer than the line. |
| break-word | Will split a word into multiple lines, if necessary. |
| inherit    | Inherits the parent element&apos;s value for this property. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-2">Section 12.2: overflow-x and overflow-y</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>These two properties work in a similar fashion as the overflow
property and accept the same values. The overflow-x parameter works
only on the x or left-to-right axis. The overflow-y works on the y or
top-to-bottom axis.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;div-x&quot;<b>&gt;</b>
  If this div is too small to display its contents,
  the content to the left and right will be clipped.
<b>&lt;/div&gt;</b>

<b>&lt;div</b> id=&quot;div-y&quot;<b>&gt;</b>
  If this div is too small to display its contents,
  the content to the top and bottom will be clipped.
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>div {
  <b>width</b>: 200px;
  <b>height</b>: 200px;
}
#div-x {
  <b>overflow-x</b>: hidden;
}
#div-y {
  <b>overflow-y</b>: hidden;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-3">Section 12.3: overflow: scroll</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div&gt;</b>
  This div is too small to display its contents to display the effects of the overflow property.
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>div {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>overflow</b>: scroll;
}</code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~ 33. width 100, height 100 with overflow: scroll (73) ~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image033.jpg"
  style="width:10%"
  title="width: 100, height: 100 with overflow: scroll"
  alt="width: 100, height: 100 with overflow: scroll." />
</p>
<!-- [image033.jpg 1.16 x 1.18](./images/image033.jpg) -->

<p>The content above is clipped in a 100px by 100px box, with scrolling
available to view overflowing content.</p>

<p>Most desktop browsers will display both horizontal and vertical
scrollbars, whether or not any content is clipped. This can avoid
problems with scrollbars appearing and disappearing in a dynamic
environment. Printers may print overflowing content.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-4">Section 12.4: overflow: visible</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div&gt;</b>
  Even if this div is too small to display its contents, the content is not clipped.
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>div {
  <b>width</b>: 50px;
  <b>height</b>: 50px;
  <b>overflow</b>: visible;
}</code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~ 34. width 50, height 50 with overflow: visible (74) ~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image034.jpg"
  style="width:7%"
  title="width 50, height 50 with overflow: visible"
  alt="width 50, height 50 with overflow: visible." />
</p>
<!-- [image034.jpg .67 x 2.427](./images/image034.jpg) -->

<p>Content is not clipped and will be rendered outside the content box if
it exceeds its container size.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-5">Section 12.5: Block Formatting Context Created with Overflow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Using the overflow property with a value different to visible will
create a new <b>block formatting context</b>. This is useful for aligning
a block element next to a floated element.</p>

<h4>CSS:</h4>

<pre><code>img {
  <b>float</b>: left;
  <b>margin-right</b>: 10px;
}
div {
  <b>overflow</b>: hidden; /* creates block formatting context */
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;img</b> src=<span style="color:red">&quot;http://placehold.it/100x100&quot;</span><b>&gt;</b>
<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, cum no paulo mollis pertinacia.<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Ad case omnis nam, mutat deseruisse persequeris eos ad, in tollit debitis sea.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~ 35. 2 images; without overflow & with overflow: hidden (75) ~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image035.jpg"
  style="width:65%"
  title="2 images; 1 without overflow & 1 with overflow: hidden"
  alt="2 images; 1 without overflow & 1 with overflow: hidden." />
</p>
<!-- [imge035.jpg 6.375 x 3.76](./images/image035.jpg) -->

<p>This example shows how paragraphs within a div with the overflow
property set will interact with a floated image.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch13">Chapter 13: Media Queries</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b>   | <b>Details</b>                                          |
|-------------|--------------------------------------------------------|
| mediatype   | (Optional) This is the type of media. Could be anything in the range of all to screen.  |
| not         | (Optional) Doesn&apos;t apply the CSS for this particular media type and applies for everything |
|             | else.
| media feature | Logic to identify use case for CSS. Options outlined below.  |

| <b>Media Feature</b> | <b>Details</b>                                          |
|----------------------|--------------------------------------------------------|
| aspect-ratio | Describes the aspect ratio of the targeted display area of the output device. |
| color       | Indicates the number of bits per color component of the output device. If the device is not a |
|             | color device, this value is zero. |
| color-index | Indicates the number of entries in the color look-up table for the output device. |
| grid        | Determines whether the output device is a grid device or a bitmap device. |
| height      | The height media feature describes the height of the output device&apos;s rendering surface. |
| max-width   | CSS will not apply on a screen width wider than specified. |
| min-width   | CSS will not apply on a screen width narrower than specified.  |
| max-height  | CSS will not apply on a screen height taller than specified.   |
| min-height  | CSS will not apply on a screen height shorter than specified.  |
| monochrome  | Indicates the number of bits per pixel on a monochrome (greyscale) device. |
| orientation | CSS will only display if device is using specified orientation. See remarks for more details. |
| resolution  | Indicates the resolution (pixel density) of the output device. |
| scan        | Describes the scanning process of television output devices. |
| width       | The width media feature describes the width of the rendering surface of the output device |
|             | (such as the width of the document window, or the width of the page box on a printer). |

| <b>Deprecated Features</b> | <b>Details</b> |
|----------------------------|---------------------------------------|
| device-aspect-ratio | <b>Deprecated</b> CSS will only display on devices whose height/width |
|                     | ratio matches the specified ratio. This is an adeprecated feature and is not guaranteed to work. |
| max-device-width | <b>Deprecated</b> Same as max-width but measures the physical screen width, rather than the |
|                  | display width of the browser. |
| min-device-width | <b>Deprecated</b> Same as min-width but measures the physical screen width, rather than the |
|                  | display width of the browser. |
| max-device-height | <b>Deprecated</b> Same as max-height but measures the physical screen width, rather than the |
|                  | display width of the browser. |
| min-device-height | <b>Deprecated</b> Same as min-height but measures the physical screen width, rather than the |
|                  | display width of the browser. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-1">Section 13.1: Terminology and Structure</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><b>Media queries</b> allow one to apply CSS rules based on the type of
device / media (e.g. screen, print or handheld) called <b>media type</b>,
additional aspects of the device are described with <b>media features</b>
such as the availability of color or viewport dimensions.</p>

<h4>General Structure of a Media Query</h4>
<pre><code><b><span style="color: blue;">&commat;media</span></b> &lbrack;&period;..&rbrack; {
  /* One or more CSS rules to apply when the query is satisfied */
}</code></pre>

<h4>A Media Query containing a Media Type</h4>
<pre><code><b><span style="color: blue;">&commat;media</span></b> print {
  /* One or more CSS rules to apply when the query is satisfied */
}</code></pre>

<h4>A Media Query containing a Media Type and a Media Feature</h4>
<pre><code><b><span style="color: blue;">&commat;media</span></b> screen and (<b>max-width</b>: 600px) {
  /*  One or more CSS rules to apply when the query is satisfied */
}</code></pre>

<h4>A Media Query containing a Media Feature (and an implicit Media Type of &quot;all&quot;)</h4>
<pre><code><b><span style="color: blue;">&commat;media</span></b> (orientation: portrait) {
  /* One or more CSS rules to apply when the query is satisfied */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-2">Section 13.2: Basic Example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b><span style="color: blue;">&commat;media</span></b> screen and (<b>min-width</b>: 720px) {
  body {
    <b>background-color</b>: skyblue;
  }
}</code></pre>

<p>The above media query specifies two conditions:</p>

<ol>
  <li>The page must be viewed on a normal screen (not a printed page,
    projector, etc).</li>
  <li>The width of the user&apos;s view port must be at least 720 pixels.</li>
</ol>

<p>If these conditions are met, the styles inside the media query will be
active, and the background color of the page will be sky blue.</p>

<p>Media queries are applied dynamically. If on page load the conditions
specified in the media query are met, the CSS will be applied, but
will be immediately disabled should the conditions cease to be met.
Conversely, if the conditions are initially not met, the CSS will not
be applied until the specified conditions are met.</p>

<p>In our example, if the user&apos;s view port width is initially greater
than 720 pixels, but the user shrinks the browser&apos;s width, the
background color will cease to be sky blue as soon as the user has
resized the view port to less than 720 pixels in width.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-3">Section 13.3: mediatype</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Media queries have an optional mediatype parameter. This parameter is
placed directly after the &commat;media declaration(<span style="color: blue;">
&commat;media</span> mediatype mediatype), for example:</p>

<pre><code><span style="color: blue;">&commat;media</span> print {
  html {
    <b>background-color</b>: white;
  }
}</code></pre>

<p>The above CSS code will give the DOM HTML element a white background
color when being printed.</p>

<p>The mediatype parameter has an optional not or only prefix that will
apply the styles to everything except the specified mediatype *or*
only the specified media type, respectively. For example, the
following code example will apply the style to every media type except
print.</p>

<pre><code><span style="color: blue;">&commat;media</span> not print {
  html {
    <b>background-color</b>: green;
  }
}</code></pre>

<p>And the same way, for just showing it only on the screen, this can be used:</p>

<pre><code><span style="color: blue;">&commat;media</span> only screen {
  .fadeInEffects {
    <b>display</b>: block;
  }
}</code></pre>

<p>The list of mediatype can be understood better with the following table:</p>

| <b>Media Type</b> | <b>Description</b>
|-------------------|---------------------------------------------------|
| all               | Apply to all devices |
| screen | Default computers |
| print | Printers in general. Used to style print-versions of websites |
| handheld | PDA&apos;s, cellphones and hand-held devices with a small screen |
| projection | For projected presentation, for example projectors |
| aural        | Speech Systems |
| braille | Braille tactile devices |
| embossed | Paged braille printers |
| tv | Television-type devices |
| tty | Devices with a fixed-pitch character grid. Terminals, portables. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-4">Section 13.4: Media Queries for Retina and Non Retina Screens</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Although this works only for WebKit based browsers, this is helpful:</p>

<pre><code>/*----------- Non-Retina Screens -----------*/
<span style="color: blue;">&commat;media</span> screen
  and (<b>min-width</b>: 1200px)
  and (<b>max-width</b>: 1600px)
  and (&minus;webkit-min-device-pixel-ratio: 1) {
}
/*----------- Retina Screens -----------*/
<span style="color: blue;">&commat;media</span> screen
  and (<b>min-width</b>: 1200px)
  and (<b>max-width</b>: 1600px)
  and (&minus;webkit-min-device-pixel-ratio: 2)
  and (min-resolution: 192dpi) {
}</code></pre>

<h4>Background Information</h4>

<p>There are two types of pixels in the display. One is the logical
pixels and the other is the physical pixels. Mostly, the physical
pixels always stay the same, because it is the same for all the
display devices. The logical pixels change based on the resolution of
the devices to display higher quality pixels. The device pixel ratio
is the ratio between physical pixels and logical pixels. For instance,
the MacBook Pro Retina, iPhone 4 and above report a device pixel ratio
of 2, because the physical linear resolution is double the logical
resolution.</p>

<p>The reason why this works only with WebKit based browsers is because of:</p>

<ul>
  <li>The vendor prefix -webkit- before the rule.</li>
  <li>This hasn&apos;t been implemented in engines other than WebKit and Blink.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-5">Section 13.5: Width vs Viewport</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When we are using &quot;width&quot; with media queries it is important to set
the meta tag correctly. Basic meta tag looks like this and it needs to be put 
inside the <b>&lt;head&gt;</b> tag.</p>

<pre><code><b>&lt;meta</b> name=&quot;viewport&quot; content=&quot;width=device-width,initial-scale=1&quot;<b>&gt;</b></code></pre>

<h4>Why this is important?</h4>

Based on MDN&apos;s definition &quot;width&quot; is

<blockquote>
  The width media feature describes the width of the rendering surface
  of the output device (such as the width of the document window, or the
  width of the page box on a printer).
</blockquote>

<p>What does that mean?</p>

<p>View-port is the width of the device itself. If your screen resolution
says the resolution is 1280 x 720, your view-port width is &quot;1280px&quot;.</p>

<p>More often many devices allocate different pixel amount to display one
pixel. For an example iPhone 6 Plus has 1242 x 2208 resolution. But
the actual viewport-width and viewport-height is 414 x 736. That means
3 pixels are used to create 1 pixel.</p>

<p>But if you did not set the meta tag correctly it will try to show your
webpage with its native resolution which results in a zoomed out view
(smaller texts and images).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-6">Section 13.6: Using Media Queries to Target Dierent Screen Sizes0</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Often times, responsive web design involves media queries, which are
CSS blocks that are only executed if a condition is satisfied. This is
useful for responsive web design because you can use media queries to
specify different CSS styles for the mobile version of your website
versus the desktop version.</p>

<pre><code><span style="color:blue">&commat;media</span> only screen and (<b>min-width</b>: 300px) and (<b>max-width</b>: 767px) {
  .site-title {
    <b>font-size</b>: 80&percnt;;
  }
/* Styles in this block are only applied if the screen size is at least 300px wide, 
but no more than 767px */
}
<span style="color:blue">&commat;media</span> only screen and (<b>min-width</b>: 768px) and (<b>max-width</b>:1023px) {
  .site-title {
    <b>font-size</b>: 90&percnt;;
  }
/* Styles in this block are only applied if the screen size is at least 768px wide, but no more 
than 1023px */
}
<span style="color:blue">&commat;media</span> only screen and (<b>min-width</b>: 1024px) {
  .site-title {
    <b>font-size</b>: 120&percnt;;
  }
/* Styles in this block are only applied if the screen size is over 1024px wide. */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-7">Section 13.7: Use on link tag</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b>&lt;link</b> rel=&quot;stylesheet&quot; media=&quot;min-width: 600px&quot; href=&quot;example.css&quot; <b>/&gt;</b></code></pre>

<p>This stylesheet is still downloaded but is applied only on devices
with screen width larger than 600px.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-8">Section 13.8: Media queries and IE8</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><a href="http://www.brianhadaway.com/responsive-web-design-using-css3-media-queries/">
Media queries</a> are not supported at all in IE8 and below (MS managment sucks).</p>

<h4>A Javascript based workaround for MS bullshit</h4>

<p>To add support for IE8, you could use one of several JS solutions. For
example, <a href="https://github.com/scottjehl/Respond">Respond</a> can be added to add media query support for IE8 only With
the following code:</p>

<pre><code>&lt;!&minus;-&lbrack;if lt IE 9&rbrack;<b>&gt;</b>
<b>&lt;script</b>
  src=&quot;respond.min.js&quot;<b>&gt;</b>
<b>&lt;/script&gt;</b>
&lt;!&lbrack;endif&rbrack;&minus;-<b>&gt;</b></code></pre>

<p><a href="https://code.google.com/p/css3-mediaqueries-js/">CSS Mediaqueries</a>
is another library that does the same thing. The code for adding that
library to your HTML would be identical:</p>

<pre><code>&lt;!&minus;-&lbrack;if lt IE 9&rbrack;<b>&gt;</b>
<b>&lt;script</b>
  src=&quot;css3-mediaqueries.js&quot;<b>&gt;</b>
<b>&lt;/script&gt;</b>
&lt;!&lbrack;endif&rbrack;&minus;-<b>&gt;</b></code></pre>

<h4>The alternative</h4>

<p>If you don&apos;t like a JS based solution, you should also consider
adding an IE&lt;9 only stylesheet where you adjust your styling specific
to IE&lt;9. For that, you should add the following HTML to your code:</p>

<pre><code>&lt;!&minus;-&lbrack;if lt IE 9&rbrack;<b>&gt;</b>
<b>&lt;link</b> rel=&quot;stylesheet&quot; type=&quot;text/css&quot; media=&quot;all&quot; href=&quot;style-ielt9.css&quot;<b>/&gt;</b>
&lt;!&lbrack;endif&rbrack;&minus;-<b>&gt;</b></code></pre>

<h4>Note:</h4>

<p>Technically it&apos;s one more alternative: using <a href="http://browserhacks.com/">
CSS hacks</a> to target IE&lt;9. It has the same impact as an IE&lt;9 only stylesheet, 
but you don&apos;t need a separate stylesheet for that. I do not recommend this option, 
though, as they produce invalid CSS code (which is but one of several reasons why the 
use of CSS hacks is generally frowned upon today).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch14">Chapter 14: Floats</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-1">Section 14.1: Float an Image Within Text</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The most basic use of a float is having text wrap around an image. The
below code will produce two paragraphs and an image, with the second
paragraph flowing around the image. Notice that it is always content
<i>after</i> the floated element that flows around the floated element.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed
nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum.
Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris
massa. Vestibulum lacinia arcu eget nulla. <b>&lt;/p&gt;</b>
<b>&lt;img</b> src=<span style="color:blue">&quot;http://lorempixel.com/200/100/&quot;</span> <b>/&gt;</b>

<b>&lt;p&gt;</b>Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. 
Curabitur sodales ligula in libero. Sed dignissim lacinia nunc. Curabitur tortor. Pellentesque 
nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis tristique sem. Proin 
ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel, suscipit quis, luctus non, 
massa. Fusce ac turpis quis ligula lacinia aliquet. <b>&lt;/p&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>img {
  <b>float</b>: left;
  <b>margin-right</b>: 1rem;
}</code></pre>

<h4>This will be the output;<h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~ 36. output from img float: left; margin-right: 1rem; (82) ~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image036.jpg"
  style="width:75%"
  title="Output from img float: left; margin-right: 1rem;"
  alt="Output from img float: left; margin-right: 1rem;" />
</p>
<!-- [image036.jpg 7.48 x 7.05](./images/image036.jpg) -->

<p><a href="http://codepen.io/vishak-kavalur/pen/pbxvLx">Demo (CodePen Link)</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-2">Section 14.2: clear property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The clear property is directly related to floats.</p>

| Property Value | Description |
|----------|---------------------------------------------|
| none | Default. Allows floating elements on both sides. |
| left | No floating elements allowed on the left side. |
| right | No floating elements allowed on the right side. |
| both | No floating elements allowed on either the left or the right side. |
| initial | Sets this property to its default value. Read about initial. |
| inherit | Inherits this property from its parent element. Read about inherit. |

<h4>HTML:</h4>

<pre><code><b>&lt;html&gt;</b>
<b>&lt;head&gt;</b>
<b>&lt;style&gt;</b>
img {
  float: left;
}
p.clear {
  clear: both;
}
<b>&lt;/style&gt;</b>
<b>&lt;/head&gt;</b>
<b>&lt;body&gt;</b>

<b>&lt;img</b> src=&quot;https://static.pexels.com/photos/69372/pexels-photo-69372-medium.jpeg&quot; width=&quot;100&quot;<b>&gt;</b>
<b>&lt;p&gt;</b>Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem
ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum <b>&lt;/p&gt;</b>
<b>&lt;p</b>class=&quot;clear&quot;<b>&gt;</b>Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum
Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum <b>&lt;/p&gt;</b>

<b>&lt;/body&gt;</b>
<b>&lt;/html&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-3">Section 14.3: Clearfix</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<blockquote>The clearfix hack is a popular way to contain floats (N. Gallagher aka &commat;necolas)</blockquote>

<p>Not to be confused with the clear property, clearfix is a <i>concept</i>
(that is also related to floats, thus the possible confusion). To <i>contain 
floats</i>, you&apos;ve to add .cf or .clearfix class on the container (<b>the 
parent</b>) and style this class with a few rules described below.</p>

<p>3 versions with slightly different effects (sources: 
<a href="http://nicolasgallagher.com/micro-clearfix-hack/">A new micro clearfix hack</a> 
by N. Gallagher and <a href="http://yuiblog.com/blog/2010/09/27/clearfix-reloaded-overflowhidden-demystified/">
clearfix reloaded</a> by T.J. Koblentx);</p>

<h4>Clearfix (with top margin collapsing of contained floats still occurring)</h4>

<pre><code>.cf: after {
  <b>content</b>: &quot;&quot;;
  <b>display</b>: table;
}
.cf: after {
  <b>clear</b>: both;
}</code></pre>

<h4>Clearfix also preventing top margin collapsing of contained floats</h4>

<pre><code>/&ast;&ast;
 &ast; For modern browsers
 &ast; 1. The space content is one way to avoid an Opera bug when the
 &ast; contenteditable attribute is included anywhere else in the document.
 &ast; Otherwise it causes space to appear at the top and bottom of elements
 &ast; that are clearfixed.
 &ast; 2. The use of &apos;table&apos; rather than &apos;block&apos; is only necessary if using
 &ast; &apos;:before&apos; to contain the top-margins of child elements.
 &ast;&ast;/
.cf:before,
.cf:after {
  <b>content</b>: &quot; &quot;; /* 1 */
  <b>display</b>: table; /* 2 */
}
# .cf:after {
  <b>clear</b>: both;
}</code></pre>

<h4>Clearfix with support of outdated browsers IE6 and IE7</h4>

<pre><code>.cf:before,
.cf:after {
  <b>content</b>: &quot; &quot;;
  <b>display</b>: table;
}
.cf:after {
  <b>clear</b>: both;
}
/*&ast;
* For IE 6/7 only
* Include this rule to trigger hasLayout and contain floats.
*&ast;/
.cf {
  &ast;zoom: 1;
}</code></pre>

<p><a href="http://codepen.io/PhilippeVay/pen/OXEqgW?editors=0100">Codepen showing ClearFix effect</a></p>

<p>Other resource: <a href="http://www.cssmojo.com/clearfix_block-formatting-context_and_hasLayout/">
Everything you know about clearfix is wrong</a>(clearfix and BFC - Block Formatting Context while 
has Layout relates to outdated browsers IE6 maybe 7)</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-4">Section 14.4: In-line DIV using float</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The div is a block-level element, i.e it occupies the whole of the
page width and the siblings are place one below the other irrespective
of their width.</p>

<pre><code><b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>This is DIV 1<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>This is DIV 2<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>The output of the following code will be;</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~ 37. this is div 1 in blue and div 2 in red (85) ~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image037.jpg"
  style="width:75%"
  title="This is DIV 1 (in blue) and DIV 2 (in red)"
  alt="This is DIV 1 (in blue) and DIV 2 (in red)." />
</p>
<!--[image037.jpg 7.48 x 3.61](./images/image037.jpg) -->

<p>We can make them in-line by adding a float css property to the div.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;outer-div&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;inner-div1&quot;<b>&gt;</b>
    <b>&lt;p&gt;</b>This is DIV 1<b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;inner-div2&quot;<b>&gt;
    <p>&lt;p&gt;</b>This is DIV 2<b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.inner-div1 {
  <b>width</b>: 50&percnt;;
  <b>margin-right</b>: 0px;
  <b>float</b>: left;
  <b>background</b>: #337ab7;
  <b>padding</b>: 50px 0px;
}
.inner-div2 {
  <b>width</b>: 50&percnt;;
  <b>margin-right</b>: 0px;
  <b>float</b>: left;
  <b>background</b>: #dd2c00;
  <b>padding</b>: 50px 0px;
}
p {
  <b>text-align</b>: center;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~ 38. this is div 1 left blue and div 2 right red (86) ~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image038.jpg"
  style="width:75%"
  title="This is DIV 1 (left blue) and DIV 2 (right red)"
  alt="This is DIV 1 (left blue) and DIV 2 (right red)." />
</p>
<!-- [image038.jpg 7.48 x .97](./images/image038.jpg) -->

<p><a href="http://codepen.io/vishak-kavalur/pen/bZxbBy">Codepen Link</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-5">Section 14.5: Use of overflow property to clear floats</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Setting overflow value to hidden,auto or scroll to an element, will
clear all the floats within that element.</p>

<p><b>Note:</b> using <b>overflow</b>:scroll will always show the scrollbox</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-6">Section 14.6: Simple Two Fixed-Width Column Layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A simple two-column layout consists of two fixed-width, floated
elements. Note that the sidebar and content area are not the same
height in this example. This is one of the tricky parts with
multi-column layouts using floats, and requires workarounds to make
multiple columns appear to be the same height.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;wrapper&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;sidebar&quot;<b>&gt;</b>
    <b>&lt;h2&gt;</b>Sidebar<b>&lt;/h2&gt;</b>
	
    <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio.<b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b>
<b>&lt;h1&gt;</b>Content<b>&lt;/h1&gt;</b>

<b>&lt;p&gt;</b>Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
Curabitur sodales ligula in libero. Sed dignissim lacinia nunc. Curabitur tortor. Pellentesque 
nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis tristique sem. Proin 
ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel, suscipit quis, luctus non, 
massa. Fusce ac turpis quis ligula lacinia aliquet. <b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.wrapper {
  <b>width</b>: 600px;
  <b>padding</b>: 20px;
  <b>background-color</b>: pink;
  
  /* Floated elements don&apos;t use any height. Adding &quot;overflow:hidden;&quot; 
  forces the parent element to expand to contain its floated children. */
<b>overflow</b>: hidden;
}
.sidebar {
  <b>width</b>: 150px;
  <b>float</b>: left;
  <b>background-color</b>: blue;
}
.content {
  <b>width</b>: 450px;
  <b>float</b>: right;
  <b>background-color</b>: yellow;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-7">Section 14.7: Simple Three Fixed-Width Column Layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;wrapper&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;left-sidebar&quot;<b>&gt;</b>
    <b>&lt;h1&gt;</b>Left Sidebar<b>&lt;/h1&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetur adipiscing elit. <b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b>
    <b>&lt;h1&gt;</b>Content<b>&lt;/h1&gt;</b>
    <b>&lt;p&gt;</b>Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. 
	Curabitur sodales ligula in libero. Sed dignissim lacinia nunc. Curabitur tortor. Pellentesque 
	nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis tristique sem. Proin 
	ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel, suscipit quis, luctus non, 
	massa. <b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;right-sidebar&quot;<b>&gt;</b>
    <b>&lt;h1&gt;</b>Right Sidebar<b>&lt;/h1</b>
    <b>&lt;p&gt;</b>Fusce ac turpis quis ligula lacinia aliquet.<b>&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>.wrapper {
  <b>width</b>: 600px;
  <b>background-color</b>: pink;
  <b>padding</b>: 20px;
  /* Floated elements don&apos;t use any height. Adding &quot;overflow:hidden;&quot;
     forces the parent element to expand to contain its floated children. */
  <b>overflow</b>: hidden;
}
.left-sidebar {
  <b>width</b>: 150px;
  <b>background-color</b>: blue;
  <b>float</b>: left;
}
.content {
  <b>width</b>: 300px;
  <b>background-color</b>: yellow;
  <b>float</b>: left;
}
.right-sidebar
{
  <b>width</b>: 150px;
  <b>background-color</b>: green;
  <b>float</b>: right;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-8">Section 14.8: Two-Column Lazy/Greedy Layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This layout uses one floated column to create a two-column layout with
no defined widths. In this example the left sidebar is &quot;lazy,&quot; in
that it only takes up as much space as it needs. Another way to say
this is that the left sidebar is &quot;shrink-wrapped.&quot; The right content
column is &quot;greedy,&quot; in that it takes up all the remaining space.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;sidebar&quot;<b>&gt;</b>
<b>&lt;h1&gt;</b>Sidebar<b>&lt;/h1&gt;</b>
<b>&lt;img</b> src=&quot;http://lorempixel.com/150/200/&quot; <b>/&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b>
<b>&lt;h1&gt;</b>Content<b>&lt;/h1&gt;</b>
<b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed
cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis 
ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia 
arcu eget nulla. <b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. 
Curabitur sodales ligula in libero. Sed dignissim lacinia nunc. Curabitur tortor. Pellentesque 
nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis tristique sem. Proin 
ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel, suscipit quis, luctus non, 
massa. Fusce ac turpis quis ligula lacinia aliquet. Mauris ipsum. Nulla metus metus, ullamcorper 
vel, tincidunt sed, euismod in, nibh. <b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>
.sidebar {
  /* &apos;display:table;&apos; shrink-wraps the column */
  <b>display</b>: table;
  <b>float</b>: left;
  <b>background-color</b>: blue;
}
.content {
  /* &apos;overflow:hidden;&apos; prevents &apos;.content&apos; from flowing under &apos;.sidebar&apos; */
  <b>overflow</b>: hidden;
  <b>background-color</b>: yellow;
}</code></pre>

<p><a href="https://jsfiddle.net/ooprqsL0/">Demo Fiddle</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch15">Chapter 15: Typography</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b> | <b>Details</b> |
|------------------|----------------------------------------|
| <i>font-style</i>   | italics or oblique |
| <i>font-variant</i> | normal or small-caps |
| <i>font-weight</i>  | normal, bold or numeric from 100 to 900. |
| <i>font-size</i>    | The font size given in %, px, em, or any other valid CSS measurement. |
| <i>line-height</i>  | The line height given in %, px, em, or any other valid CSS measurement. |
| <i>font-family</i>  | This is for defining the family&apos;s name. |
| <i>color</i>        | Any valid CSS color representation, like red, #00FF00,hsl(240, 100%, 50%) etc. |
| <i>font-stretch</i> | Whether or not to use a confenced or expanded face from font. Valid values are normal, ultra- |
|                     | condensed, extra-condensed, condensed, semi-condensed, semi-expanded, expanded, extra- |
|                     | expanded or ultra-expanded. |
| <i>text-align</i>   | start, end, left, right, center, justify, match-parent |
| <i>text-decoration</i> | none, underline, overline, line-through, initial, inherit; |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-1">Section 15.1: The Font Shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>With the syntax:</p>

<pre><code>element {
  <b>font</b>: &lbrack;font-style&rbrack; &lbrack;font-variant&rbrack; &lbrack;font-weight&rbrack; &lbrack;font-size/line-height&rbrack; &lbrack;font-family&rbrack;;
}</code></pre>

<p>You can have all your font-related styles in one declaration with the
font shorthand. Simply use the font property, and put your values in
the correct order.</p>

<p>For example, to make all p elements bold with a font size of 20px and
using Arial as the font family typically you would code it as follows:</p>

<pre><code>p {
  <b>font-weight</b>: bold;
  <b>font-size</b>: 20px;
  <b>font-family</b>: Arial, sans-serif;
}</code></pre>

<p>However with the font shorthand it can be condensed as follows:</p>

<pre><code>p {
  <b>font</b>: bold 20px Arial, sans-serif;
}</code></pre>

<p><b>Note</b>: that since font-style, font-variant, font-weight and
line-height are optional, the three of them are skipped in this
example. It is important to note that using the shortcut <b>resets</b>
the other attributes not given. Another important point is that the
two necessary attributes for the font shortcut to work are font-size
and fontfamily. If they are not both included the shortcut is ignored.</p>

<p>Initial value for each of the properties:</p>

<ul>
  <li><b>font-style</b>: normal;</li>
  <li><b>font-variant</b>: normal;</li>
  <li><b>font-weight</b>: normal;</li>
  <li><b>font-stretch</b>: normal;</li>
  <li><b>font-size</b>: medium;</li>
  <li><b>line-height</b>: normal;</li>
  <li>font-famly - depends on user agent</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-2>Section 15.2: Quotes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The quotes property is used to customize the opening and closing quotation 
marks of the <b>&gt;</b> tag.</p>

<pre><code>q {
  <b>quotes</b>: &quot;«&quot; &quot;»&quot;;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-3">Section 15.3: Font Size</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;element-one&quot;<b>&gt;</b>Hello I am some text.<b>&lt;/div&gt;</b>
<b>&lt;div</b> id=&quot;element-two&quot;<b>&gt;</b>Hello I am some smaller text.<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>#element-one {
  <b>font-size</b>: 30px;
}
#element-two {
  <b>font-size</b>: 10px;
}</code></pre>

<p>The text inside #element-one will be 30px in size, while the text in #element-two will be 10px in size.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-4">Section 15.4: Text Direction</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>div {
  <b>direction</b>: ltr; /* Default, text read read from left-to-right */
}
.ex {
  <b>direction</b>: rtl; /* text read from right-to-left */
}
.horizontal-tb {
  <b>writing-mode</b>: horizontal-tb;  /* Default, text read from left-to-right and top-to-bottom. */
}
.vertical-rtl {
  <b>writing-mode</b>: vertical-rl;  /* text read from right-to-left and top-to-bottom */
}
.vertical-ltr {
  <b>writing-mode</b>: vertical-rl;  /* text read from left-to-right and top to bottom */
}</code></pre>

<p>The direction property is used to change the horizontal text direction of an 
element.</p>

<b>Syntax;direction</b>: ltr &vert; rtl &vert; initial &vert; inherit;

<p>The writing-mode property changes the alignment of text so it can be
read from top-to-bottom or from left-to-right, depending on the
language.</p>

<b>Syntax: direction</b>: horizontal-tb &vert; vertical-rl &vert; vertical-lr;
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-5">Section 15.5: Font Stacks</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b>font-family</b>: &apos;Segoe UI&apos;, Tahoma, sans-serif;</code></pre>

<p>The browser will attempt to apply the font face &quot;Segoe UI&quot; to the
characters within the elements targeted by the above property. If this
font is not available, or the font does not contain a glyph for the
required character, the browser will fall back to Tahoma, and, if
necessary, any sans-serif font on the user&apos;s computer. Note that any
font names with more than one word such as &quot;Segoe UI&quot; need to have
single or double quotes around them.</p>

<pre><code><b>font-family</b>: Consolas, &apos;Courier New&apos;, monospace;</code></pre>

<p>The browser will attempt to apply the font face &quot;Consolas&quot; to the
characters within the elements targeted by the above property. If this
font is not available, or the font does not contain a glyph for the
required character, the browser will fall back to &quot;Courier New,&quot;
and, if necessary, any monospace font on the user&apos;s computer.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-6">Section 15.6: Text Overflow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The text-overflow property deals with how overflowed content should be signaled 
to users. In this example, the ellipsis represents clipped text.</p>

<pre><code>.text {
  <b>overflow</b>: hidden;
  <b>text-overflow</b>: ellipsis;
}</code></pre>

<p>Unfortunately, only works on a single line of text. There is no way to
support ellipsis on the last line in standard CSS, but it can be
achieved with non-standard webkit-only implementation of flexboxes.</p>

<pre><code>.giveMeEllipsis {
  <b>overflow</b>: hidden;
  <b>text-overflow</b>: ellipsis;
  <b>display</b>: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: N;  /* number of lines to show */
  <b>line-height</b>: X;  /* fallback */
  <b>max-height</b>: X&ast;N; /* fallback */
}</code></pre>

<p>Example (open in Chrome or Safari):</p>
<p><a href="http://jsfiddle.net/csYjC/1131/">jsFiddle</a>.</p>

<h4>Resources:</h4>

<p><a href="https://www.w3.org/TR/2012/WD-css3-ui-20120117/#text-overflow0">Text Overflow (jsFiddle)</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-7">Section 15.7: Text Shadow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To add shadows to text, use the text-shadow property. The syntax is as follows:</p>

<pre><code><b>text-shadow</b>: horizontal-offset vertical-offset blur color;</code></pre>

<h4>Shadow without blur radius</h4>

<p>This creates a blue shadow effect around a heading</p>

<h4>Shadow with blur radius</h4>

<p>This creates a blue shadow effect around a heading</p>
To add a blur effect, add an option blur radius argument

<pre><code>h1 {
  <b>text-shadow</b>: 2px 2px 10px #0000FF;
}</code></pre>

<h4>Multiple Shadows</h4>

<p>To give an element multiple shadows, separate them with commas</p>

<pre><code>h1 {
  <b>text-shadow</b>: 0 0 3px #FF0000, 0 0 5px #0000FF;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-8">Section 15.8: Text Transform</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The text-transform property allows you to change the capitalization of text. 
Valid values are: uppercase, capitalize, lowercase, initial, inherit, and none.</p>

<h4>CSS:</h4>

<pre><code>.example1 {
  <b>text-transform</b>: uppercase;
}
.example2 {
  <b>text-transform</b>: capitalize;
}
.example3 {
  <b>text-transform</b>: lowercase;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;p</b> class=&quot;example1&quot;<b>&gt;</b>
  all letters in uppercase&lt;!&minus;-&quot;ALL LETTERS IN UPPERCASE&quot;&minus;-&gt;
<b>&lt;/p&gt;</b>
<b>&lt;p</b>class =&quot;example2&quot;<b>&gt;</b>
  all letters in capitalize&lt;!&minus;-&quot;All Letters In Capitalize (Sentence Case)&quot;&minus;-&gt;
<b>&lt;/p&gt;</b>
<b>&lt;p</b> class=&quot;example3&quot;<b>&gt;</b>
  all letters in lowercase&lt;!&minus;-&quot;all letters in lowercase&quot;&minus;-&gt;
<b>&lt;/p&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-9">Section 15.9: Letter Spacing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>h2 {
  /* adds a 1px space horizontally between each letter;
  also known as tracking */
  <b>letter-spacing</b>: 1px;
}</code></pre>

<p>The letter-spacing property is used to specify the space between the characters 
in a text.</p>

<p>!letter-spacing also supports negative values:</p>

<pre><code>p {
  <b>letter-spacing</b>: -1px;
}</code></pre>

<p>Resources: <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing">Letter Spacing</a></p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-10">Section 15.10: Text Indent</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>p {
  <b>text-indent</b>: 50px;
}</code></pre>

<p>The text-indent property specifies how much horizontal space text
should be moved before the beginning of the first line of the text
content of an element.</p>

<h4>Resources:</h4>
<ul>
  <li><a href="http://stackoverflow.com/questions/5856952/indenting-only-the-first-line-of-text-in-a-paragraph">
    Indenting only the first line of text in a paragraph?</a></li>
  <li><a href="https://www.w3.org/TR/CSS21/text.html#propdef-text-indent">Text Indent</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent">Mozilla Text Indent</a></li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-11">Section 15.11: Text Decoration</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The text-decoration property is used to set or remove decorations from text.</p>

<pre><code>h1 { <b>text-decoration</b>: none; }
h2 { <b>text-decoration</b>: overline; }
h3 { <b>text-decoration</b>: line-through; }
h4 { <b>text-decoration</b>: underline; }</code></pre>

<p>text-decoration can be used in combination with text-decoration-style
and text-decoration-color as a shorthand property:</p>

<pre><code>.title { <b>text-decoration</b>: underline dotted blue; }</code></pre>

<p>This is a shorthand version of</p>

<pre><code>.title
{
  <b>text-decoration-style</b>: dotted;
  <b>text-decoration-line</b>: underline;
  <b>text-decoration-color</b>: blue;
}</code></pre>

<p>It should be noted that the following properties are only supported in Firefox</p>

<ul>
  <li>text-decoration-color</li>
  <li>text-decoration-line</li>
  <li>text-decoration-style</li>
  <li>text-decoration-skip</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-12">Section 15.12: Word Spacing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The word-spacing property specifies the spacing behavior between tags and 
words.</p>

<h4>Possible values</h4>

<ul>
  <li>a positive or negative <i>length</i> (using em px vh cm etc.) or <i>percentage</i> (using %)</li>
  <li>the keyword normal uses the font&apos;s default word spacing</li>
  <li>the keyword inherit takes the value from the parent element</li>
</ul>

<h4>CSS</h4>

<pre><code>.normal    { <b>word-spacing</b>: normal; }
.narrow    { <b>word-spacing</b>: -3px; }
.extensive {<b>word-spacing</b>: 10px; }</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;p&gt;</b>
  <b>&lt;span</b> class=&quot;normal&quot;<b>&gt;</b>This is an example, showing the effect of &quot;word-spacing&quot;.<b>&lt;/span&gt;&lt;br&gt;</b>
  <b>&lt;span</b> class=&quot;narrow&quot;<b>&gt;</b>This is an example, showing the effect of &quot;word-spacing&quot;.<b>&lt;/span&gt;&lt;br&gt;</b> 
  <b>&lt;span</b> class=&quot;extensive&quot;<b>&gt;</b>This is an example, showing the effect of &quot;word-spacing&quot;.<b>&lt;/span&gt;&lt;br&gt;</b>
<b>&lt;/p&gt;</b></code></pre>

<h4>Online-Demo</h4>

<a href="https://jsfiddle.net/91742Lxt/">Try it yourself</a>

<h4>Further reading:</h4>
<ul>
  <li><a href="https://developer.mozilla.org/de/docs/Web/CSS/word-spacing">
    word-spacing--&rbrack;MDN</a></li>
  <li><a href="https://www.w3.org/wiki/CSS/Properties/word-spacing">
    word-spacing-w3.org</a></li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch15-13">Section 15.13: Font Variant</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Attributes:</h4>

<b><i>normal</i></b>

<p>Default attribute of fonts.</p>

<b><i>small-caps</i></b>

<p>Sets every letter to uppercase, <b>but</b> makes the lowercase letters(from 
original text) smaller in size than the letters that originally uppercase.</p>

<h4>CSS:</h4>

<pre><code>.smallcaps {
  <b>font-variant</b>: small-caps;
}</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;p</b> class=&quot;smallcaps&quot;<b>&gt;</b>
  Documentation about CSS Fonts
  <b>&lt;br&gt;</b>
  aNd ExAmpLe
<b>&lt;/p&gt;</b></code></pre>

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~ 39. documentation about css fonts and example (95) ~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image039.jpg"
  style="width:25%"
  title="Documentation about CSS Fonts aNd ExAmpLe."
  alt="Documentation about CSS Fonts aNd ExAmpLe." />
</p>
<!-- [image039.jpg 2.34 x .375](./images/image039.jpg) -->

<p>Note: The font-variant property is a shorthand for the properties:
font-variant-caps, font-variant-numeric, fontvariant-alternates,
font-variant-ligatures, and font-variant-east-asian.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch16">Chapter 16: Flexible Box Layout (Flexbox)</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The Flexible Box module, or just &apos;flexbox&apos; for short, is a box model
designed for user interfaces, and it allows users to align and
distribute space among items in a container such that elements behave
predictably when the page layout must accommodate different, unknown
screen sizes. A flex container expands items to fill available space
and shrinks them to prevent overflow.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-1">Section 16.1: Dynamic Vertical and Horizontal Centering (alignitems, justify-content)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<b>Simple Example (centering a single element)</b>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;aligner&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;aligner-item&quot;<b>&gt;</b>...<b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code>.aligner {
  <b>display</b>: flex;
  <b>align-items</b>: center;
  <b>justify-content</b>: center;
}
.aligner-item {
  <b>max-width</b>: 50&percnt;; /* for demo. Use actual width instead. */
}</code></pre>

<p>Here is a <a href="http://codepen.io/asim-coder/pen/ZOobqz">demo (CodePen)</a>.</p>

<h4>Reasoning</h4>

| <b>Property</b> | <b>Value</b> | <b>Description</b>                                           |
|-----------------|--------------|--------------------------------------------------------------|
| align-items | center | This centers the elements along the axis other than the one specified by flex-direction, |
|             |        | i.e., vertical centering for a horizontal flexbox and horizontal centering for a vertical |
|             |        | flexbox. |
| justify-content | center | This centers the elements along the axis specified by flex-direction. I.e., for a |
|                 |        | horizontal (<b>flex-direction</b>: row) flexbox, this centers horizontally, and for a vertical |
|                 |        | flexbox (<b>flex-direction</b>: column) flexbox, this centers vertically. |

<h4>Individual Property Examples</h4>

<p>All of the below styles are applied onto this simple layout:</p>

<pre><code><b>&lt;div</b> id=&quot;container&quot;<b>&gt;</b>
  <b>&lt;div&gt;&lt;/div&gt;</b>
  <b>&lt;div&gt;&lt;/div&gt;</b>
  <b>&lt;div&gt;&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>where #container is the flex-box.</p>

<h4>Example: justify-content: center on a horizontal flexbox</h4>

<b>CSS:</b>

<pre><code>div#container {
  <b>display</b>: flex;
  <b>flex-direction</b>: row;
  <b>justify-content</b>: center;
}</code></pre>

<b>Outcome:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 40. 3 square in first row (97) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image040.jpg"
  style="width:50%"
  title="3 squares in row 1"
  alt="3 squares in row 1." />
</p>
<!-- [image040.jpg ](./images/image040.jpg) -->

Here is the <a href="https://jsfiddle.net/d6pc5bmd/">demo jsFiddle</a>.

<h4>Example: justify-content: center on a vertical flexbox</h4>

<b>CSS:</b>

<pre><code>div#container {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
  <b>justify-content</b>: center;
}</code></pre>

<h4>Outcome:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 41. 3 square in column 1 (98) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image041.jpg"
  style="width:50%"
  title="3 squares in column 1"
  alt="3 squares in column 1." />
</p>
<!-- [image041.jpg](./images/image041.jpg) -->

<p>Here is a <a href="https://jsfiddle.net/d6pc5bmd/1/">demo (jsFiddle)</a>.</p>

<h4>Example: align-content: center on a horizontal flexbox</h4>

<h4>CSS:</h4>

<pre><code>div#container {
  <b>display</b>: flex;
  <b>flex-direction</b>: row;
  <b>align-items</b>: center;
}</code></pre>

<h4>Outcome:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 42. 3 squares in center row (99) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image042.jpg"
  style="width:50%"
  title="3 square in center row"
  alt="3 square in center row." />
</p>
<!-- [image042.jpg](./images/image042.jpg) -->

<p>Here is a <a href="https://jsfiddle.net/d6pc5bmd/2/">demo jsFiddle</a>.</p>

<h4>align-content: center</h4>

<h4>Example: align-content: cener on a vertical flexbox</h4>

<h4>CSS:</h4>

<pre><code>div#container {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
  <b>align-items</b>: center;
}</code></pre>

<h4>Outcome:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~ 43. 3 square in center column (100) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image043.jpg"
  style="width:50%"
  title="3 squares in center column"
  alt="3 squares in center column." />
</p>
<!-- [image043.jpg 6.97 x 6.15](./images/image043.jpg) -->

<p>Here is a <a href="https://jsfiddle.net/d6pc5bmd/3/">demo (jsFiddle)</a>.</p>

<h4>Example: Combination for centering both on horizontal flexbox</h4>

<pre><code>div #container {
  <b>display</b>: flex;
  <b>flex-direction</b>: row;
  <b>justify-content</b>: center;
  <b>align-items</b>: center;
}</code></pre>

<h4>Outcome:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~ 44. 3 square across in center column & row (101) ~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image044.jpg"
  style="width:50%"
  title="3 squares across in center column &amp; row"
  alt="3 squares across in center column &amp; row." />
</p>
<!-- [image044.jpog 6.93 x 6.13](./images/image044.jpg) -->

<p>Here is a <a href="https://jsfiddle.net/d6pc5bmd/4/">Demo (jsFiddle)</a>.</p>

<h4>Example: Combination for centering both on vertical flexbox</h4>

<pre><code>div #container {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
  <b>justify-content</b>: center;
  <b>align-items</b>: center;
}</code></pre>

<h4>Outcome:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~ 45. 3 squares down center column & row  (102) ~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image045.jpg"
  style="width:50%"
  title="3 squares down center, column &amp; row"
  alt="3 squares down center, column &amp; row." />
</p>
<!-- [image045.jpg 6.93 x 6.11](./images/image045.jpg) -->

Here is a <a href="https://jsfiddle.net/d6pc5bmd/5/">demo (jsFiddle)</a>.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-2">Section 16.2: Sticky Variable-Height Footer</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This code creates a sticky footer. When the content doesn&apos;t reach the
end of the viewport, the footer sticks to the bottom of the viewport.
When the content extends past the bottom of the viewport, the footer
is also pushed out of the viewport.</p>

<h4><a href="https://jsfiddle.net/0t1f84tL/">View Result (jsFiddle)</a>.</h4>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;header&quot;<b>&gt;</b>
  <b>&lt;h2&gt;</b>Header<b>&lt;/h2&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b>
  <b>&lt;h1&gt;</b>Content<b>&lt;/1&gt;</b>
  <b>&lt;p&gt;</b>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. 
  Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis
  ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia
  arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos 
  himenaeos. Curabitur sodales ligula in libero. <b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div</b> class=&quot;footer&quot;<b>&gt;</b>
  <b>&lt;h4&gt;</b>Footer<b>&lt;/h4</b><b>&gt;</b>
<b>&lt;</b><b>/div</b><b>&gt;</b></code></pre>

</h4>CSS:</h4>

<pre><code>html, body {
  <b>height</b>: 100&percnt;;
}
body {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
}
.content {
/* Include &apos;0 auto&apos; for best browser compatibility. */
  <b>flex</b>: 10 auto;
}
.header, .footer {
  <b>background-color</b>: grey;
  <b>color</b>: white;
  <b>flex</b>: none;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-3">Section 16.3: Optimally fit elements to their container</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>One of the nicest features of flexbox is to allow optimally fitting
containers to their parent element.</p>

<p><a href="https://jsfiddle.net/6gfogoqk/">Live Demo (jsFiddle)</a>.</p>

<h4>HTML:</h4>

<pre><code>&lt;div class = &quot;flex-container&quot;&gt;
&lt;div class = &quot;flex-item&quot;&gt;1 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;2 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;3 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;4 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;5 &lt;/div&gt;
&lt;/div&gt;</code></pre>

<h4>CSS:</h4>

<pre><code>.flex-container {
  <b>background-color</b>:#000;
  <b>height</b>:100&percnt;; display: flex; flex-direction: row;
  <b>flex-wrap</b>: wrap; justify-content: flex-start; align-content: stretch;
  <b>align-items</b>: stretch;
}
.flex-item {
  <b>background-color</b>: #ccf;
  <b>margin</b>:0.1em; <b>flex-grow</b>: 1;
  <b>flex-shrink</b>:0;
  <b>flex-basis</b>:200px; /* or % could be used to ensure a specific layout */
}</code></pre>

<h4>Outcome:</h4>

<p>Columns adapt as screen is resized.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~ 46. Columns adapt as screen is resized (104) ~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image046.png"
  style="width:75%"
  title="Columns adapt as screen is resized"
  alt="Columns adapt as screen is resized." />
</p>
<!-- [image046.png 7.48 x 3.18](./images/image046.png) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-4">Section 16.4: Holy Grail Layout using Flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><a href="http://alistapart.com/article/holygrail">Holy Grail layout</a> is a layout 
with a fixed height header and footer, and a center with 3 columns. The 3 columns 
include a fixed width sidenav, a fluid center, and a column for other content like 
ads (the fluid center appears first in the markup). CSS Flexbox can be used to 
achieve this with a very simple markup:</p>

<h4>HTML Markup:</h4>

<pre><code><b>&lt;div</b> class=&quot;container&quot;<b>&gt;</b>
  <b>&lt;header</b> class=&quot;header&quot;<b>&gt;</b>Header<b>&lt;/header&gt;</b>
  <b>&lt;div</b> class=&quot;content-body&quot;<b>&gt;</b>
    <b>&lt;main</b> class=&quot;content&quot;<b>&gt;</b>Content<b>&lt;/main&gt;</b>
    <b>&lt;nav</b> class=&quot;sidenav&quot;<b>&gt;</b>Nav<b>&lt;/nav&gt;</b>
    <b>&lt;aside</b> class=&quot;ads&quot;<b>&gt;</b>Ads<b>&lt;/aside&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;footer</b> class=&quot;footer&quot;<b>&gt;</b>Footer<b>&lt;</b><b>/footer</b><b>&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>body {
  <b>margin</b>: 0; 
  <b>padding</b>: 0;
}
.container {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
  <b>height</b>: 100vh;
}
.header {
  <b>flex</b>: 0 0 50px;
}
.content-body {
  <b>flex</b>: 1 1 auto;
  <b>display</b>: flex;
  <b>flex-direction</b>: row;
}
.content-body
.content {
  <b>flex</b>: 1 1 auto;
  <b>overflow</b>: auto;
}
.content-body .sidenav {
  <b>order</b>: &minus; 1;
  <b>flex</b>: 0 0 100px;
  <b>overflow</b>: auto;
}
.content-body .ads {
  <b>flex</b>: 0 0 100px;
  <b>overflow</b>: auto;
}
.footer {
  <b>flex</b>: 0 0 50px;
}</code></pre>

<a href="https://jsfiddle.net/adityarb88/hek6ms0x/">Demo (jsFiddle)</a>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-5">Section 16.5: Perfectly aligned buttons inside cards with flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>It&apos;s a regular pattern in design these days to vertically align
<b>call to actions</b> inside its containing cards like this:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 47. vertically align call to actions (105) ~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image047.jpg"
  style="width:75%"
  title="Vertically align call to actions"
  alt="Vertically align call to actions." />
</p>
<!-- [image047.jpg 7.49 x 3.38](./images/image047.jpg) -->

<p>This can be achieved using a special trick with flexbox.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;cards&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;card&quot;<b>&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum Magna proident ex anim dolor ullamco pariatur reprehenderit culpa esse enim 
	  mollit labore dolore voluptate ullamco et ut sed qui minim.<b>&lt;/p&gt;</b>
    <b>&lt;p&gt;&lt;button&gt;</b>Action<b>&lt;/button&gt;&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;card&quot;<b>&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum Magna proident ex anim dolor ullamco pariatur reprehenderit culpa esse enim 
	  mollit labore dolore voluptate ullamco et ut sed qui minim.<b>&lt;/p&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum Magna proident ex anim dolor ullamco pariatur reprehenderit culpa esse enim 
	  mollit labore dolore voluptate ullamco et ut sed qui minim.<b>&lt;/p&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum Magna proident ex anim dolor ullamco pariatur reprehenderit culpa esse enim 
	  mollit labore dolore voluptate ullamco et ut sed qui minim.<b>&lt;/p&gt;</b>
    <b>&lt;p&gt;</b>Lorem ipsum Magna proident ex anim dolor ullamco pariatur reprehenderit culpa esse enim 
	  mollit labore dolore voluptate ullamco et ut sed qui minim.<b>&lt;/p&gt;</b>
    <b>&lt;p&gt;&lt;button&gt;</b>Action<b>&lt;/button&gt;&lt;/p&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>First of all, we use CSS to apply <b>display</b>: flex; to the container. This 
will create 2 columns equal in height with the content flowing naturally inside it.</p>

<h4>CSS:</h4>

<pre><code>.cards {
  <b>display</b>: flex;
}
.card {
  <b>border</b>: 1px solid #ccc;
  <b>margin</b>: 10px 10px;
  <b>padding</b>: 0 20px;
}
button {
  <b>height</b>: 40px;
  <b>background</b>: #fff;
  <b>padding</b>: 0 40px;
  <b>border</b>: 1px solid #000;
}
p: last-child {
  <b>text-align</b>: center;
}</code></pre>

<h4>The layout will change and become like this:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~ 48. display: flex; to container (107) ~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image048.jpg"
  style="width:75%"
  title="display: flex; to container"
  alt="display: flex; to container." />
</p>
<!-- [image048.jpg 7.48 x 3"](./images/image048.jpg) -->

<p>In order to move the buttons to the bottom of the block, we need to apply 
<b>display</b>: flex; to the card itself with the direction set to column. After
that, we should select the last element inside the card and set the margin-top 
to auto. This will push the last paragraph to the bottom of the card and achieve 
the required result.</p>

<h4>Final CSS:</h4>

<pre><code>.cards {
  <b>display</b>: flex;
}
.card {
  <b>border</b>: 1px solid #ccc;
  <b>margin</b>: 10px 10px;
  <b>padding</b>: 0 20px;
  <b>display</b>: flex;
  <b>flex-direction</b>: column; }
button {
  <b>height</b>: 40px;
  <b>background</b>: #fff;
  <b>padding</b>: 0 40px;
  <b>border</b>: 1px solid #000; 
}
p: last-child {
  <b>text-align</b>: center;
  <b>margin-top</b>: auto;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-6">Section 16.6: Same height on nested containers</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This code makes sure that all nested containers are always the same height. 
This is done by assuring that all nested elements are the same height as the 
containing parent div. <a href="https://jsfiddle.net/3wwh7ewp/">
See working example:</a></p>

<p>This effect is achieved due to the property align-items being set to stretch by default.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;container&quot;<b>&gt;</b>
  <b>&lt;div</b> style=&quot;background-color: red&quot;<b>&gt;</b>
    Some <b>&lt;br/&gt;</b>
    data <b>&lt;br /&gt;</b>
    to make <b>&lt;br /&gt;</b>
    a height <b>&lt;br /&gt;</b>
  <b>&lt;/div&gt;</b>
  <b>&lt;div</b> style=&quot;background-color: blue&quot;<b>&gt;</b>
    Fewer <b>&lt;br /&gt;</b>
    lines <b>&lt;br /&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code>.container {
  <b>display</b>: flex;
  <b>align-items</b>: stretch; // Default value
}
</code></pre>

<p>Note: <a href="http://caniuse.com/#search=flexbox">Does not work on IE versions under 10</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch17">Chapter 17: Cascading and Specificity</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-1">Section 17.1: Calculating Selector Specificity</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Each individual CSS Selector has its own specificity value. Every selector 
in a sequence increases the sequence&apos;s overall specificity. Selectors fall 
into one of three different specificity groups: <i>A</i>, <i>B</i> and <i>c</i>. 
When multiple selector sequences select a given element, the browser uses the 
styles applied by the sequence with the highest overall specificity.</p>

| <b>Group</b> | <b>Comprised of</b> | <b>Examples</b> |
|--------------|---------------------|----------------------|
| <i>A</i>            | id selectors        |  #foo |
| <i>B</i>            | class selectors     | .bar |
|              | attribute selectors | &lbrack;title&rbrack;, &lbrack;colspan=&quot;2&quot;&rbrack; |
|              | pseudo-classes      | :hover, :nth-child(2) |
| <i>C</i>     | type selectors      | div, li |
|              | pseudo-elements     | ::before, ::first-letter |

<p>Group <i>A</i> is the most specific, followed by Group <i>B</i>, then finally Group <i>C</i>.</p>

<p>The universal selector (&ast;) and combinators (like &gt; and &#126;) have no specificity.</p>

<h4>Example 1: Specificity of various selector sequences</h4>

<pre><code>#foo #baz {}             /* a=2, b=0, c=0 */<br/>
#foo .bar {}             /* a=1, b=1, c=0 */<br/>
#foo {}                  /* a=1, b=0, c=0 */<br/>
.bar: hover {}           /* a=0, b=2, c=0 */<br/>
div.bar {}               /* a=0, b=1, c=1 */<br/>
:hover {}                /* a=0, b=1, c=0 */<br/>
&lbrack;title&rbrack; {}              /* a=0, b=1, c=0 */<br/>
.bar {}                 /* a=0, b=1, c=0 */<br/>
div ul &plus; li {}           /* a=0, b=0, c=3 */<br/>
p::after {}              /* a=0, b=0, c=2 */<br/>
&ast;::before {}             /* a=0, b=0, c=1 */<br/>
::before {}              /* a=0, b=0, c=1 */<br/>
div {}                   /* a=0, b=0, c=1 */<br/>
&ast; {}                     /* a=0, b=0, c=0 */</code></pre>

<h4>Example 2: How specificity is used by the browser</h4>

<p>Imagine the following CSS implementation:</p>

<pre><code>#foo {
  <b>color</b>: blue;
}
.bar {
  <b>color</b>: red;
  <b>background</b>: black;
}</code></pre>

<p>Here we have an ID selector which declares color as <i>blue</i>, and a
class selector which declares color as <i>red</i> and background as
<i>black</i>.</p>

<p>An element with an ID of #foo and a class of .bar will be selected by
both declarations. ID selectors have a Group <i>A</i> specificity and class
selectors have a Group <i>B</i> specificity. An ID selector outweighs any
number of class selectors. Because of this, color: blue; from the #foo selector 
will be applied to the element. The higher specificity of the ID selector will
cause the browser to ignore the .bar selector&apos;s color declaration.</p>

<h4>Now imagine a different CSS implementation:</h4>

<pre><code>.bar {
  <b>color</b>: red;
  <b>background</b>: black;
}
.baz {
  <b>background</b>: white;
}</code></pre>

<p>Here we have two class selectors; one of which declares color as <i>red</i>
and background as <i>black</i>, and the other declares background as <i>white</i>.</p>

<p>An element with both the .bar and .baz classes will be affected by both of 
these declarations, however the problem we have now is that both .bar and .baz 
have an identical Group <i>B</i> specificity. The cascading nature of CSS resolves 
this for us: as .baz is defined <i>after</i> .bar, our element ends up with the 
<i>red</i> color from .bar but the <i>white</i> background from .baz.</p>

<h4>Example 3: How to manipulate specificity</h4>

<p>The last snippet from Example 2 above can be manipulated to ensure our
.bar class selector&apos;s color declaration is used instead of that of
the .baz class selector.</p>

<pre><code>.bar {}     /* a=0, b=1, c=0 */
.baz {}     /* a=0, b=1, c=0 */</code></pre>

<p>The most common way to achieve this would be to find out what other
selectors can be applied to the .bar selector sequence. For example,
if the .bar class was only ever applied to span elements, we could
modify the .bar selector to span.bar. This would give it a new Group
<i>C</i> specificity, which would override the .baz selector&apos;s lack
thereof:</p>

<pre><code>span .bar {}  /* a=0, b=1, c=1 */
.baz {}       /* a=0, b=1, c=0 */</code></pre>

<p>However it may not always possible to find another common selector
which is shared between any element which uses the .bar class. Because
of this, CSS allows us to duplicate selectors to increase specificity.
Instead of just .bar, we can use instead (See 
<a href="https://www.w3.org/TR/css3-selectors/#grammar">The grammar of
Selectors, W3C Recommendation</a>). This still selects any element with a 
class of .bar, but now has double the Group <i>B</i> specificity:</p>

<pre><code>.bar.bar {}  /* a=0, b=2, c=0 */
.baz {}      /* a=0, b=1, c=0 */</code></pre>

<h4>!important and inline style declarations</h4>

<p>The !important flag on a style declaration and styles declared by the
HTML style attribute are considered to have a greater specificity than
any selector. If these exist, the style declaration they affect will
overrule other declarations regardless of their specificity. That is,
unless you have more than one declaration that contains an !important
flag for the same property that apply to the same element. Then,
normal specificity rules will apply to those properties in reference
to each other.</p>

<p>Because they completely override specificity, the use of !important is
frowned upon in most use cases. One should use it as little as
possible. To keep CSS code efficient and maintainable in the long run,
it&apos;s almost always better to increase the specificity of the
surrounding selector than to use !important.</p>

<p>One of those rare exceptions where !important is not frowned upon, is
when implementing generic helper classes like a .hidden or
.background-yellow class that are supposed to always override one or
more properties wherever they are encountered. And even then, you need
> to know what you&apos;re doing. The last thing you want, when writing
maintainable CSS, is to have !important flags throughout your CSS.</p>

<h4>A final note</h4>

<p>A common misconception about CSS specificity is that the Group <i>A</i>,
<i>B</i> and <i>c</i> values should be combined with each other (a=1,=1 =&gt;
151). This is <b>not</b> the case. If this were the case, having 20 of a
Group <i>B</i> or <i>c</i> selector would be enough to override a single Group
<i>A</i> or <i>B</i> selector respectively. The three groups should be regarded
as individual levels of specificity. Specificity cannot be represented
by a single value.</p>

<p>When creating your CSS style sheet, you should maintain the lowest
specificity as possible. If you need to make the specificity a little
higher to overwrite another method, make it higher but as low as
possible to make it higher. You shouldn&apos;t need to have a selector
like this:</p>

<pre><code>body.page header.container nav div#main-nav li a {}</code></pre>

<p>This makes future changes harder and pollutes that css page.</p>

<p>You can calculate the specificity of your selector <a href="http://specificity.keegan.st/">here</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-2">Section 17.2: The !important declaration</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The !important declaration is used to override the usual specificity in a style 
sheet by giving a higher priority to a rule. Its usage is: property : value !important;</p>

<pre><code>#mydiv {
  <b>font-weight</b>: bold !important; /* This property won&apos;t be overridden
                                 by the rule below */
}
#outerdiv #mydiv {
  <b>font-weight</b>: normal;         /* #mydiv font-weight won&apos;t be set to normal
                                 even if it has a higher specificity because
                                 of the !important declaration above */
}</code></pre>

<p>Avoiding the usage of !important is strongly recommended (unless
absolutely necessary), because it will disturb the natural flow of css
rules which can bring uncertainty in your style sheet. Also it is
important to note that when multiple !important declarations are
applied to the same rule on a certain element, the one with the higher
specificity will be the ona applied.</p>

<p>Here are some examples where using !important declaration can be justified:</p>

<ul>
  <li>If your rules shouldn&apos;t be overridden by any inline style of the 
    element which is written inside style attribute of the html element.</li>
  <li>To give the user more control over the web accessibility, like increasing 
    or decreasing size of the font-size, by overriding the author style using !important.</li>
  <li>For testing and debugging using inspect element.</li>
</ul>

<h4>See also:</h4>

<a href="https://www.w3.org/TR/CSS22/cascade.html#important-rules">W3C - 
6 Assigning property values, Cascading, and Inheritance &minus;-6.4.2 !important rules</a>.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-3">Section 17.3: Cascading</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Cascading and specificity are used together to determine the final
value of a CSS styling property. They also define the mechanisms for
resolving conflicts in CSS rule sets.</p>

<h4>CSS Loading order</h4>

<p>Styles are read from the following sources, in this order:</p>

<ol>
  <li>User Agent stylesheet (The styles supplied by the browser vendor)
  <li>User stylesheet (The additional styling a user has set on his/her browser)</li>
  <li>Author stylesheet (Author here means the creator of the webpage/website)
    <ul>
	  <li>Maybe one or more .css files</li>
	  <li>In the <b>&lt;style&gt;</b> element of the HTML document</li>
	</ul>
  <li>Inline styles (In the style attribute on an HTML element)</li>
</ol>

<p>The browser will lookup the corresponding style(s) when rendering an element.</li>

<h4>How are conflicts resolved?</h4>

<p>When only one CSS rule set is trying to set a style for an element,
then there is no conflict, and that rule set is used.</p>

<p>When multiple rule sets are found with conflicting settings, first the
Specificty rules, and then the Cascading rules are used to determine
what style to use.</p>

<h4>Example 1 - Specificity rules</h4>

<pre><code>.mystyle { <b>color</b>: blue; } /* specificity: 0, 0, 1, 0 */
div { <b>color</b>: red; }       /* specificity: 0, 0, 0, 1 */
<b>&lt;div</b> class=&quot;mystyle&quot;<b>&gt;</b>Hello World<b>&lt;/div&gt;</b></code></pre>

<p>What color will the text be? (hover to see the answer)</p>

<blockquote>
  blue
</blockquote>

<p>First the specificity rules are applied, and the one with the highest
specificity &quot;wins&quot;.</p>

<h4>Example 2 - Cascade rules with identical selectors</h4>

<h4><i>External css file</i></h4>

<pre><code>.class {
  <b>background</b>: #FFF;
}</code></pre>

<h4><i>Internal css (in HTML file)</i></h4>

<pre><code><b>&lt;style&gt;</b>
.class {
  background: #000;
}
<b>&lt;style&gt;</b></code></pre>

<p>In this case, where you have identical selectors, the cascade kicks
in, and determines that the last one loaded &quot;wins&quot;.</p>

<h4>Example 3 - Cascade rules after Specificity rules</h4>

<pre><code>body &gt; .mystyle { <b>background-color</b>: blue; }  /* specificity: 0, 0, 1, 1 */
.otherstyle &gt; div { <b>background-color</b>: red; } /* specificity: 0, 0, 1, 1 */
<b>&lt;body</b> class=&quot;otherstyle&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;mystyle&quot;<b>&gt;</b>Hello World<b>&lt;/div&gt;</b>
<b>&lt;/body&gt;</b></code></pre>

<p>What color will the background be?</p>

<blockquote>
  red
</blockquote>

<p>After applying the specificity rules, there&apos;s still a conflict
between blue and red, so the cascading rules are applied on top of the
specificity rules. Cascading looks at the load order of the rules,
whether inside the same .css file or in the collection of style
sources. The last one loaded overrides any earlier ones. In this case,
the rule &quot;wins&quot;.</p>

<h4>A final note</h4>
<ul>
  <li>Selector specificity always take precedence.</li>
  <li>Stylesheet order break ties.</li>
  <li>Inline styles trump everything.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-4">Section 17.4: More complex specificity example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>div {
  <b>font-size</b>: 7px;
  <b>border</b>: 3px dotted pink;
  <b>background-color</b>: yellow;
  <b>color</b>: purple;
}
body.mystyle &gt; div.myotherstyle {
  <b>font-size</b>: 11px;
  <b>background-color</b>: green;
}
#elmnt1 {
  <b>font-size</b>: 24px;
  <b>border-color</b>: red;
}
.mystyle .myotherstyle {
  <b>font-size</b>: 16px;
  <b>background-color</b>: black;
  <b>color</b>: red;
}
<b>&lt;body</b> class=&quot;mystyle&quot;<b>&gt;</b>
  <b>&lt;div</b> id=&quot;elmnt1&quot; class=&quot;myotherstyle&quot;<b>&gt;</b>
    Hello, world!
  <b>&lt;/div&gt;</b>
<b>&lt;/body&gt;</b></code></pre>

<p>What borders, colors, and font-sizes will the text be? font-size:</p>

<h4>font-size</h4>
<blockquote>
  <b>font-size</b>: 24; Since #elmnt1 rule set has the highest specificity <b>&lt;div</b>
    in question, every property here is set.
</blockquote>

<h4>border</h4>
<blockquote>
  <b>border</b>: 3px dotted red; The border color red is take from #elmnt1 rule set,
    since it has the highest specificity. The other properties of the border, border-thickness,
    and border-style are from the div rule set.
</blockquote>

<h4>background-color:</h4>
<blockquote>
  <b>background-color</b>: green; The background-color is set in the div, 
    body.mystyle &gt; div.myotherstyle and .mystyle .myotherstyle rule sets. 
    The specificities are (0,0,1)vs.(0,2,2)vs.(0,2,0), so the middle one "wins".
</blockquote>

<h4>color:</h4>
<blockquote>
  <b>color</b>: red; The color is set in both the div and .mystyle .myotherstyle
    rule sets. The latter has the higher specificity of (0,2,0) and "wins".
</blockquote>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch18">Chapter 18: Colors</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-1">Section 18.1: currentColor</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>currentColor returns the computed color value of the current element.</p>

<h4>Use in same element</h4>

<p>Here currentColor evaluates to red since the color property is set to red:</p>

<pre><code>div {
  <b>color</b>: red;
  <b>border</b>: 5px solid currentColor;
  <b>box-shadow</b>: 0 0 5px currentColor;
}</code></pre>

<p>In this case, specifying currentColor for the border is most likely
redundant because omitting it should produce identical results. Only
use currentColor inside the border property within the same element if
it would be overwritten otherwise due to a more specific selector.</p>

<p>Since it&apos;s the computed color, the border will be green in the
following example due to the second rule overriding the first:</p>

<pre><code>div {
  <b>color</b>: blue;
  <b>border</b>: 3px solid currentColor;
  <b>color</b>: green;
}</code></pre>

<h4>Inherited from parent element</h4>

<p>The parent&apos;s color is inherited, here currentColor evaluates to
&apos;blue&apos;, making the child element&apos;s border-color blue.</p>

<pre><code>.parent-class {
  <b>color</b>: blue;
}
.parent-class .child-class {
  <b>border-color</b>: currentColor;
}</code></pre>

<p>currentColor can also be used by other rules which normally would not inherit 
from the color property, such as background-color. The example below shows the 
children using the color set in the parent as its background:</p>

<pre><code>.parent-class {
  <b>color</b>: blue;
}
.parent-class .child-class {
  <b>background-color</b>: currentColor;
}</code></pre>

<h4>Possible Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~ 49. parent element, child element * 2 (116) ~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image049.png"
  style="width:50%"
  title="parent element, child element rectangle * 2"
  alt="parent element, child element rectangle * 2." />
</p>
<!-- [image049.png 5.2 x 3.09](./images/image049.png) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-2">Section 18.2: Color Keywords</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Most browsers support using color keywords to specify a color. For
example, to set the color of an element to blue, use the blue keyword:</p>

<pre><code>.some-class {
  <b>color</b>: blue;
}</code></pre>

<p>CSS keywords are not case sensitive---blue, Blue and BLUE will all
result in #0000FF.</p>

<h4><b>Color Keywords</b></h4>

| <b>Color name</b>|<b>Hex value</b> | <b>RGB values</b>
|------------------|---------------|-------------------------|
| AliceBlue        | #F0F8FF | rgb(240,248,255) |
| AntiqueWhite     | #FAEBD7 | rgb(250,235,215) |
| Aqua             | #00FFFF  | rgb(0,255,255) |
| Aquamarine       | #7FFFD4 | rgb(127,255,212) |
| Azure            | #F0FFFF | rgb(240,255,255) |
| Beige            | #F5F5DC | rgb(245,245,220) |
| Bisque           | #FFE4C4 | rgb(255,228,196) |
| Black            | #000000 | rgb(0,0,0) |
| BlanchedAlmond   | #FFEBCD | rgb(255,235,205) |
| Blue             | #0000FF | rgb(0,0,255) |
| BlueViolet       | #8A2BE2 | rgb(138,43,226) |
| Brown            | #A52A2A | rgb(165,42,42) |
| BurlyWood        | #DEB887 | rgb(222,184,135) |
| CadetBlue        | #5F9EA0 | rgb(95,158,160) |
| Chartreuse       | #7FFF00 | rgb(127,255,0) |
| Chocolate        | #D2691E | rgb(210,105,30) |
| Coral            | #FF7F50 | rgb(255,127,80) |
| CornflowerBlue   | #6495ED | rgb(100,149,237) |
| Cornsilk         | #FFF8DC | rgb(255,248,220) |
| Crimson          | #DC143C | rgb(220,20,60) |
| Cyan             | #00FFFF | rgb(0,255,255) |
| DarkBlue         | #00008B | rgb(0,0,139) |
| DarkCyan         | #008B8B | rgb(0,139,139)  |
| DarkGoldenRod    | #B8860B | rgb(184,134,11)   |
| DarkGray         | #A9A9A9 | rgb(169,169,169)  |
| DarkGrey         | #A9A9A9 | rgb(169,169,169)  |
| DarkGreen        | #006400 | rgb(0,100,0)      |
| DarkKhaki        | #BDB76B | rgb(189,183,107)  |
| DarkMagenta      | #8B008B |   rgb(139,0,139) |
| DarkOliveGreen   | #556B2F |   rgb(85,107,47) |
| DarkOrange       | #FF8C00 |   rgb(255,140,0) |
| DarkOrchid       | #9932CC |   rgb(153,50,204) |
| DarkRed          | #8B0000 |   rgb(139,0,0)   |
| DarkSalmon        | #E9967A  |  rgb(233,150,122) |
| DarkSeaGreen      | #8FBC8F  |  rgb(143,188,143) |
| DarkSlateBlue     | #483D8B  |  rgb(72,61,139) |
| DarkSlateGray     | #2F4F4F  |  rgb(47,79,79)  |
| DarkSlateGrey     | #2F4F4F  |  rgb(47,79,79)  |
| DarkTurquoise     | #00CED1  |  rgb(0,206,209) |
| DarkViolet        | #9400D3  |  rgb(148,0,211) |
| DeepPink          | #FF1493 | rgb(255,20,147)   |
| DeepSkyBlue       | #00BFFF | rgb(0,191,255)    |
| DimGray           | #696969 | rgb(105,105,105)  |
| DimGrey           | #696969 | rgb(105,105,105)  |
| DodgerBlue        | #1E90FF | rgb(30,144,255)   |
| FireBrick         | #B22222 | rgb(178,34,34)    |
| FloralWhite       | #FFFAF0 | rgb(255,250,240)  |
| ForestGreen  |      #228B22 | rgb(34,139,34)            |
| Fuchsia     | #FF00FF | rgb(255,0,255)            |
| Gainsboro    | #DCDCDC | rgb(220,220,220) |
| GhostWhite | #F8F8FF | rgb(248,248,255)          |
| Gold       | #FFD700 | rgb(255,215,0)            |
| GoldenRod  | #DAA520 | rgb(218,165,32)           |
| Gray           | #808080 | rgb(128,128,128)          |
| Grey                   | #808080 | rgb(128,128,128)          |
| Green                  | #008000 | rgb(0,128,0)              |
| GreenYellow            | #ADFF2F  | rgb(173,255,47)           |
| HoneyDew              | #F0FFF0  | rgb(240,255,240)          |
| HotPink               | #FF69B4  | rgb(255,105,180)          |
| IndianRed             | #CD5C5C  | rgb(205,92,92)            |
| Indigo                | #4B0082  | rgb(75,0,130)             |
| Ivory                 | #FFFFF0  | rgb(255,255,240)          |
| Khaki                 | #F0E68C  | rgb(240,230,140)          |
| Lavender              | #E6E6FA  | rgb(230,230,250)          |
| LavenderBlush         | #FFF0F5  | rgb(255,240,245)          |
| LawnGreen             | #7CFC00  | rgb(124,252,0)            |
| LemonChiffon          | #FFFACD | rgb(255,250,205)       |
| LightBlue             | #ADD8E6 | rgb(173,216,230)       |
| LightCoral            | #F08080 | rgb(240,128,128)         |
| LightCyan             | #E0FFFF | rgb(224,255,255)         |
| LightGoldenRodYellow  | #FAFAD2 | rgb(250,250,210) |
| LightGray                | #D3D3D3  | rgb(211,211,211)      |
| LightGrey                | #D3D3D3  | rgb(211,211,211)      |
| LightGreen               | #90EE90  | rgb(144,238,144)      |
| LightPink                | #FFB6C1  | rgb(255,182,193)      |
| LightSalmon              | #FFA07A  | rgb(255,160,122)      |
| LightSeaGreen            | #20B2AA  | rgb(32,178,170)       |
| LightSkyBlue             | #87CEFA  | rgb(135,206,250)      |
| LightSlateGray           | #778899  | rgb(119,136,153)      |
| LightSlateGrey           | #778899  | rgb(119,136,153)      |
| LightSteelBlue           | #B0C4DE  | rgb(176,196,222)      |
| LightYellow              | #FFFFE0  | rgb(255,255,224)      |
| Lime                     | #00FF00  | rgb(0,255,0)          |
| LimeGreen                | #32CD32  | rgb(50,205,50)        |
| Linen                    | #FAF0E6  | rgb(250,240,230)      |
| Magenta                  | #FF00FF  | rgb(255,0,255)        |
| Maroon                   | #800000  | rgb(128,0,0)          |
| MediumAquaMarine         | #66CDAA  | rgb(102,205,170)      |
| MediumBlue               | #0000CD  | rgb(0,0,205)          |
| MediumOrchid             | #BA55D3  | rgb(186,85,211)       |
| MediumPurple             | #9370DB  | rgb(147,112,219)      |
| MediumSeaGreen           | #3CB371  | rgb(60,179,113)       |
| MediumSlateBlue          | #7B68EE  | rgb(123,104,238)      |
| MediumSpringGreen        | #00FA9A  | rgb(0,250,154)        |
| MediumTurquoise          | #48D1CC  | rgb(72,209,204)       |
| MediumVioletRed          | #C71585  | rgb(199,21,133)       |
| MidnightBlue             | #191970  | rgb(25,25,112) |
| MintCream                | #F5FFFA  | rgb(245,255,250) |
| MistyRose         | #FFE4E1     | rgb(255,228,225) |
| Moccasin          | #FFE4B5     | rgb(255,228,181) |
| NavajoWhite       | #FFDEAD     | rgb(255,222,173) |
| Navy            | #000080     | rgb(0,0,128)   |
| OldLace           | #FDF5E6     | rgb(253,245,230) |
| Olive           | #808000     | rgb(128,128,0) |
| OliveDrab      | #6B8E23   | rgb(107,142,35) |
| Orange        | #FFA500     | rgb(255,165,0) |
| OrangeRed     | #FF4500     | rgb(255,69,0)  |
| Orchid        |  #DA70D6   | rgb(218,112,214)  |
| PaleGoldenRod |  #EEE8AA  | rgb(238,232,170)  |
| PaleGreen     |  #98FB98  | rgb(152,251,152)  |
| PaleTurquoise | #AFEEEE   | rgb(175,238,238)  |
| PaleVioletRed | #DB7093   | rgb(219,112,147)  |
| PapayaWhip    | #FFEFD5   | rgb(255,239,213)  |
| PeachPuff     | #FFDAB9   | rgb(255,218,185) |
| Peru          | #CD853F   | rgb(205,133,63)   |
| Pink          | #FFC0CB   | rgb(255,192,203)  |
| Plum          | #DDA0DD   | rgb(221,160,221)  |
| PowderBlue    | #B0E0E6 | rgb(176,224,230) |
| Purple        | #800080 | rgb(128,0,128)   |
| RebeccaPurple | #663399 | rgb(102,51,153)  |
| Red           | #FF0000 | rgb(255,0,0)     |
| RosyBrown     | #BC8F8F | rgb(188,143,143) |
| RoyalBlue     | #4169E1 | rgb(65,105,225)  |
| SaddleBrown   | #8B4513 | rgb(139,69,19)   |
| Salmon        | #FA8072  | rgb(250,128,114) |
| SandyBrown | #F4A460 | rgb(244,164,96) |
| SeaGreen        | #2E8B57  | rgb(46,139,87) |
| SeaShell        | #FFF5EE  | rgb(255,245,238) |
| Sienna        | #A0522D  | rgb(160,82,45) |
| Silver        | #C0C0C0  | rgb(192,192,192) |
| SkyBlue        | #87CEEB  | rgb(135,206,235) |
| SlateBlue        | #6A5ACD  | rgb(106,90,205) |
| SlateGray        | #708090  | rgb(112,128,144) |
| SlateGrey        | #708090  | rgb(112,128,144) |
| Snow        | #FFFAFA  | rgb(255,250,250) |
| SpringGreen        | #00FF7F  | rgb(0,255,127) |
| SteelBlue        | #4682B4  | rgb(70,130,180) |
| Tan        | #D2B48C  | rgb(210,180,140) |
| Teal        | #008080  | rgb(0,128,128) |
| Thistle        | #D8BFD8  | rgb(216,191,216) |
| Tomato        | #FF6347  | rgb(255,99,71) |
| Turquoise        | #40E0D0  | rgb(64,224,208) |
| Violet        | #EE82EE  | rgb(238,130,238) |
| Wheat        | #F5DEB3  | rgb(245,222,179) |
| White       | #FFFFFF  | rgb(255,255,255) |
| WhiteSmoke  | #F5F5F5  | rgb(245,245,245) |
| Yellow      | #FFFF00 | rgb(255,255,0) |
| YellowGreen | #9ACD32 | rgb(154,205,50) |

<p>In addition to the named colors, there is also the keyword
transparent, which represents a fully-transparent black: rgba(0,0,0,0).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-3">Section 18.3: Hexadecimal Value</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Background</h4>

<p>CSS colors may also be represented as a hex triplet, where the members
represent the red, green and blue components of a color. Each of these
values represents a number in the range of 00 to FF, or 0 to 255 in
decimal notation. Uppercase and/or lowercase Hexadecimal values may be
used (i.e. #3fc = #3FC = #33ffCC). The browser interprets #369 as
#336699. If that is not what you intended but rather wanted #306090,
you need to specify that explicitly.</p>

<p>The total number of colors that can be represented with hex notation
is 256 &Hat; 3 or 16,777,216.</p>

<h4>Syntax</h4>

<blockquote>
  <b>color</b>: #rrggbb;<br>
  <b>color</b>: #rgb;
</blockquote>

| <b>Value</b> |  <b>Description</b> |
|--------------|---------------------|
| rr           | 00-FF for the amount of red. |
| gg           | 00-FF for the amount of green. |
| bb           | 00-FF for the amount of blue. |

<pre><code>.some-class {
  /* This is equivalent to using the color keyword &apos;blue&apos; */
  <b>color</b>: #0000FF;
}
.also-blue {
  /* If you want to specify each range value with a single number, you can!
     This is equivalent to &apos;#0000FF&apos; (and &apos;blue&apos;) */
  <b>color</b>: #00F;
}</code></pre>

<p><a href="https://en.wikipedia.org/wiki/Hexadecimal">Hexadecimal notation</a> is 
used to specify color values in the RGB color format, per the 
<a href="https://www.w3.org/TR/css3-color/#numerical">W3C&apos;s &apos;Numerical 
color values&apos;.</a></p>

<p>There are a lot of tools available on the Internet for looking up
hexadecimal (or simply hex) color values.</p>

<p>Search for &quot;<b>hex color palette</b>&quot; or &quot;</b>hex color picker&quot; with
your favorite web browser to find a bunch of options!</p>

<p>Hex values always start with a pound sign (#), are up to six
&quot;digits&quot; long, and are case-insensitive: that is, they don&apos;t care
about capitalization. #FFC125 and #ffc125 are the same color.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-4">Section 18.4: rgb() Notation</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>RGB is an additive color model which represents colors as mixtures of
red, green, and blue light. In essence, the RGB representation is the
decimal equivalent of the Hexadecimal Notation. In Hexadecimal each
number ranges from 00-FF which is equivalent to 0-255 in decimal and
0%-100% in percentages.</p>

<pre><code>.some-class {
  /* Scalar RGB, equivalent to &apos;blue&apos; */
  <b>color</b>: rgb (0,0,255);
}
.also-blue {
  /* Percentile RGB values */
  <b>color</b>: rgb(0&percnt;, 0&percnt;, 100&percnt;);
}</code></pre>

<h4><b>Syntax</b></h4>

<pre><code>rgb(&lt;red&gt;, &lt;green&gt;, &lt;blue&gt;)</code></pre>


|<b>Value</b> | <b>Description</b> |
|-------------|--------------------|
| <b>&lt;red&gt;</b> | an integer from 0 - 255 or percentage from 0 - 100%. |
| <b>&lt;green&gt;</b>   | an integer from 0 - 255 or percentage from 0 - 100%. |
| <b>&lt;blue&gt;</b>    | an integer from 0 - 255 or percentage from 0 - 100%. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-5">Section 18.5: rgba() Notation</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Similar to rgb() notation, but with an additional alpha (opacity) value.</p>

<pre><code>.red {
  /* Opaque red */
  <b>color</b>: rgba (255, 0, 0, 1);
}
.red-50p {
  /* Half-translucent red. */
  <b>color</b>: rgba(255, 0, 0, .5);
}</code></pre>

<h4>Syntax</h4>

<pre><code>rgba(&lt;red&gt;, &lt;green&gt;, &lt;blue&gt;, &lt;alpha&gt;);</code></pre>

| <b>Value</b> | <b>Description</b>
|--------------|--------------------------------|
| <b>&lt;red&gt;</b> | an integer from 0 - 255 or percentage from 0 - 100%. |
| <b>&lt;green&gt;</b> | an integer from 0 - 255 or percentage from 0 - 100%. |
| <b>&lt;blue&gt;</b> | an integer from 0 - 255 or percentage from 0 - 100%. |
| <b>&lt;alpha&gt;</b> | a number from 0 - 1, where 0.0 is fully transparent and 1.0 is fully opaque. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-6">Section 18.6: hsl() Notation</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>HSL stands for <b>hue</b> (&quot;which color&quot;), <b>saturation</b> (&quot;how much
color&quot;) and <b>lightness</b> (&quot;how much white&quot;).</p>

<p>Hue is represented as an angle from 0° to 360° (without units), while
saturation and lightness are represented as percentages.</p>

<pre><code>p {
  <b>color</b>: hsl(240, 100&percnt;, 50&percnt;); /* Blue */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 189. saturation and hue (124) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image189.jpg"
  style="width:75%"
  title="Saturation and Hue"
  alt="Saturation and Hue." />
</p>
<!-- [image189.jpg 7.48 x 5.61](img src="./images/image189.jpg") -->
<!-- {width="7.48037510936133in" height="5.610277777777778in"} -->

<h4>Syntax</h4>

<pre><code><b>color</b>: hsl(&lt;hue&gt;, &lt;saturation&gt;&percnt;, &lt;lightness&gt;&percnt;);</code></pre>

| <b>Value</b> | <b>Description</b> |
|----------------|-------------------------------------------|
| <b>&lt;hue</b> | specified in degrees around the color wheel (without units), where 0° is red, 60° is yellow, 120° is |
|                | green, 180° is cyan, 240° is blue, 300° is magenta, and 360° is red. |
| <b>&lt;saturation</b> | specified in percentage where 0% is fully desaturated (grayscale) and 100% is fully saturated (vividly |
|               | colored).
| <b>&lt;lightness&gt; | specified in percentage where 0% is fully blakc and 100% is fully white. |

<h4>Notes</h4>

<ul>
  <li>A saturation of 0% always produces a grayscale color; changing the hue has no effect.</li>
  <li>A lightness of 0% always produces black, and 100% always produces white; changing the hue or saturation
    has no effect.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch18-7">Section 18.7: hsla() Notation</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Similar to hsl() notation, but with an added alpha (opacity) value.</p>

<pre><code>hsla(240, 100%, 50%, 0) /* transparent */
hsla(240, 100%, 50%, 0.5) /* half-translucent blue */
hsla(240, 100%, 50%, 1) /* fully opaque blue */</code></pre>

<h4>Syntax</h4>

<pre><code>hsla(&lt;hue&gt;, &lt;saturation&gt;&percnt;, &lt;lightness&gt;&percnt;, &lt;alpha&gt;);</code></pre>

| <b>Value</b> | <b>Description</b> |
|--------------|-------------------------------------------------|
| <b>&lt;hue&gt;</b> | specified in degrees around the color wheel (without units), where 0° is red, 60° is yellow, 120° is |
|                | green, 180° is cyan, 240° is blue, 300° is magenta, and 360° is red. |
| <b>&lt;saturation&gt;</b> | percentage where 0% is fully desaturated (grayscale) and 100% is fully saturated (vividly colored) |
| <b>&lt;lightness&gt;</b> | percentage where 0% is fully black and 100% is fully white. |
| <b>&lt;alpha&gt;</b> | a number from 0 - 1 where 0 is fully transparent and 1 is fully opaque. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch19">Chapter 19: Opacity</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch19-1">Section 19.1: Opacity Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>An element&apos;s opacity can be set using the opacity property. Values
can be anywhere from 0.0 (transparent) to 1.0 (opaque).

<h4>Example Usage</h4>

<pre><code>
<b>&lt;</b><b>div</b> style=&quot;opacity:0.8;&quot;<b>&gt;</b>
  This is a partially transparent element
<b>&lt;</b><b>/div</b><b>&gt;</b>
</code></pre>

| <b>Property Value</b> | <b>Transparency</b> |
|-----------------------|----------------------|
| <b>opacity</b>: 1.0; | Opaque. |
| <b>opacity</b>: 0.75; | 25% transparent (75% Opaque). |
| <b>opacity</b>: 0.5; | 50% transparent (50% Opaque) |
| <b>opacity</b>: 0.25; | 75% transparent (25% Opaque) |
| <b>opacity</b>: 0.0; | Transparent |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch19-2">Section 19.2: IE Compatibility for &apos;opacity&apos;</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To use opacity in all versions of IE, the order is:</p>

<pre><code>.transparent-element {
  /* for IE 8 & 9 */
  -ms-filter: &quot;progid:DXImageTransform.Microsoft.Alpha(Opacity=60)&quot;; // IE8
  /* works in IE 8 & 9 too, but also 5, 6, 7 */
  <b>filter</b>: alpha(opacity=60);  // IE 5&minus;7
  /* Modern Browsers */
  <b>opacity</b>: 0.6;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch20">Chapter 20: Length Units</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>Unit</b> | <b>Description</b>
|-----------|-------------------------------------------------|
| &percnt; | Define sizes in terms of parent objects or current object dependent on property |
| em | Relative to the font-size of the element (2em means 2 times the size of the current font) |
| rem | Relative to font-size of the root element |
| vw | Relative to 1% of the width of the viewport&ast; |
| vh | Relative to 1% of the height of the viewport&ast; |
| vmin | Relative to 1% of > viewport&apos;s&ast; smaller dimension |
| vmax | Relative to 1% of viewport&apos;s&ast; larger dimension |
| cm | centimeters | 
| mm | millimeters |
| in | inches (1in = 96px = 2.54cm) |
| px | pixels (1px = 1/96th of 1in) | 
| pt | points (1pt = 1/72 of 1in) |
| pc | picas (1pc = 12 pt) |
| s | seconds (used for animations and transitions) |
| ms | milliseconds (used for animations and transitions) |
| ex | Relative to the x-height of the current font |
| ch | Based on the width of the zero (0) character |
| fr | fractional unit (used for CSS Grid Layout) |

<p>A CSS distance measurement is a number immediately followed by a
length unit (px, em, pc, in, ...)</p>

<p>CSS supports a number of length measurements units. They are absolute
or relative.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch20-1">Section 20.1: Creating scalable elements using rems and ems</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Version ≥ 3</h4>

<p>You can use rem defined by the font-size of your html tag to style
elements by setting their font-size to a value of rem and use em
inside the element to create elements that scale with your global
font-size.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;input</b> type=&quot;button&quot; value=&quot;Button&quot;<b>&gt;</b>
<b>&lt;input</b> type=&quot;range&quot;<b>&gt;</b>
<b>&lt;input</b> type=&quot;text&quot; value=&quot;Text&quot;<b>&gt;</b></code></pre>

<h4>Relevant CSS:</h4>

<pre><code>html {
  <b>font-size</b>: 16px;
}
input&lbrack;type=&quot;button&quot;&rbrack; {
  <b>font-size</b>: 1rem;
  <b>padding</b>: 0.5em 2em;
}

input&lbrack;type=&quot;range&quot;&rbrack; {
  <b>font-size</b>: 1rem;
  <b>width</b>: 10em;
}
input&lbrack;type=text&rbrack; {
  <b>font-size</b>: 1rem;
  <b>padding</b>: 0.5em;
}</code></pre>

<h4>Possible Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 190.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image190.jpg"
  style="width:65%"
  title=""
  alt="." />
</p>
<!-- [image190.jpg 6.34 x 2.95](./images/image190.jpg) -->
<!-- {width="6.34375in" height="2.9583333333333335in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch20-2">Section 20.2: Font size with rem</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS3 introduces a few new units, including the 
<a href="https://www.w3.org/TR/css-values/#font-relative-lengths">rem</a> unit, 
which stands for &quot;root em&quot;. Let&apos;s look at how rem works.</p>

<p>First, let&apos;s look at the differences between em and rem.</p>

<ul>
  <li><b>em</b>: Relative to the font size of the parent. This causes the 
    compounding issue.</li>
  <li><b>rem</b>: Relative to the font size of the root or <b>&gt;</b> element. 
    This means it&apos;s possible to declare a single font size for the html 
	element and define all rem units to be a percentage of that.</li>
</ul>

<p>The main issue with using rem for font sizing is that the values are
somewhat difficult to use. Here is an example of some common font
sizes expressed in rem units, assuming that the base size is 16px:</p>

<ul>
  <li>10px = 0.625rem</li>
  <li>12px = 0.75rem</li>
  <li>14px = 0.875rem</li>
  <li>16px = 1rem (base)</li>
  <li>18px = 1.125rem</li>
  <li>20px = 1.25rem</li>
  <li>24px = 1.5rem</li>
  <li>30px = 1.875rem</li>
  <li>32px = 2rem</li>
</ul>

<h4>CODE:</h4>

<p>Version ≥ 3</p>

<pre><code>html {
  <b>font-size</b>: 16px;
}
h1 {
  <b>font-size</b>: 2rem;  /* 32px */
}
p {
  <b>font-size</b>: 1rem;  /* 16px */
}
li {
  <b>font-size</b>: 1.5em; /* 24px */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch20-3">Section 20.3: vmin and vmax</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li><b>vmin</b>: Relative to 1 percent of the viewport&apos;s smaller dimension.</li>
  <li><b>vmax</b>: Relative to 1 percent of the viewport&apos;s larger dimension.</li>
</ul>

<p>In other words, 1 vmin is equal to the smaller of <i>1 vh</i> and <i>1 vw</i></p>

<p>1 vmax is equal to the larger of <i>1 vh</i> and <i>1 vw</i></p>

<p><b>Note</b>: vmax is <a href="http://caniuse.com/#feat=viewport-units">not supported in:</p>

<ul>
  <li>any version of Internet Explorer</li>
  <li>Safari before version 6.1</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch20-4">Section 20.4: vh and vw</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS3 introduced two units for representing size.</p>

<ul>
  <li>vh, which stands for viewport height is relative to 1% of the viewport height.</li>
  <li>vw, which stands for viewport width is relative to 1% of the viewport width.</li>
</ul>

<h4>Version ≥ 3</h4>

<pre><code>div {
  <b>width</b>: 20vw;
  <b>height</b>: 20vh;
}</code></pre>

<p>Above, the size for the div takes up 20% of the width and height of
the viewport.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch20-5">Section 20.5: using percent %</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>One of the useful unit when creating a responsive application.</p>

<p>Its size depends on its parent container.</p>

<b>Equation:</b>

<blockquote>
  ( Parent Container&apos;s width ) &ast; ( Percentage(%) ) = Output
</blockquote>

<h4>For Example:</h4>

<p><i>Parent</i> has <b>100px</b> width while the <i>Child</i> has <b>50%</b>.</p>

<p><b>On the output</b>, the *Child*&apos;s width will be half(50%) of the
<i>Parent</i>&apos;s, which is <b>50px</b>.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> class=&quot;parent&quot;<b>&gt;</b>
  PARENT
  <b>&lt;div</b> class=&quot;child&quot;<b>&gt;</b>
    CHILD
  <b>&lt;/div</b><b>&gt;</b>
<b>&lt;/div</b><b>&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code><b>&lt;style&gt;</b>
&ast;{
  color: #CCC;
}
.parent {
  background-color: blue;
  width: 100px;
}
.child {
  background-color: green;
  width: 50%;
}
<b>&lt;/style&gt;</b></code></pre>

<b>OUTPUT</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 191.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image191.jpg"
  style="width:15%"
  title=""
  alt="." />
</p>
<!-- [image191.jpg 1.4 x .875](./images/image191.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch21">Chapter 21: Pseudo-Elements</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>pseudo-element</b> |  <b>Description</b> |
|-----------------------|---------------------|
| ::after | Insert content after the content of an element. |
| ::before | Insert content before the content of an element. |
| ::first-letter | Selects the first letter of each element. |
| ::first-line | Selects the first line of each element. |
| ::selection | Matches the portion of an element that is selected by a user. |
| ::backdrop | Used to create a backdrop that hides the underlying document for an |
|            | element in the top layer&apos;s |
| ::placeholder | Allows you to style the placeholder text of a form element |
|               | (Experimental)
| ::marker | For applying list-style attributes on a given element (Experimental) |
| ::spelling-error | Represents a text segment which the browser has flagged as incorrectly |
|                  | spelled (Experimental) |
| ::grammar-error | Represents a text segment which the browser has flagged as |
|                 | grammatically incorrect (Experimental) |

<p>Pseudo-elements, just like pseudo-classes, are added to a CSS
selectors but instead of describing a special state, they allow you to
scope and style certain parts of an html element.</p>

<p>For example, the ::first-letter pseudo-element targets only the first
letter of a block element specified by the selector.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch21-1">Section 21.1: Pseudo-Elements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Pseudo-elements are added to selectors but instead of describing a
special state, they allow you to style certain parts of a document.</p>

<p>The content attribute is required for pseudo-elements to render;
however, the attribute can have an empty value (e.g.content: &quot;&quot;).</p>

<pre><code>div::after {
  <b>content</b>: &apos;after&apos;;
  <b>color</b>: red;
  <b>border</b>: 1px solid red;
}
div  {
  <b>color</b>: black;
  <b>border</b>: 1px solid black;
  <b>padding</b>: 1px;
}
div::before {
  <b>content</b>: &apos;before&apos;;
  <b>color</b>: green;
  <b>border</b>: 1px solid green;
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~ section 21-1. before, div element, after (131) ~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-21-1.png"
  style="width:15%"
  title="Section 21-1. Before, div element, after"
  alt="Section 21-1. Before, div element, after." />
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch21-2">Section 21.2: Pseudo-Elements in Lists</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Pseudo-elements are often used to change the look of lists (mostly for
unordered lists, ul).</p>

<p>The first step is to remove the default list bullets:</p>

<pre><code>ul {
  <b>list-style-type</b>: none;
}</code></pre>

<p>Then you add the custom styling. In this example, we will create
gradient boxes for bullets.</p>

<pre><code>li:before {
  <b>content</b>: &quot;&quot;;
  <b>display</b>: inline-block;
  <b>margin-right</b>: 10px;
  <b>height</b>: 10px;
  <b>width</b>: 10px;
  <b>background</b>: linear-gradient (red, blue);
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;ul&gt;</b>
  <b>&lt;li&gt;</b>Test I<b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Test II<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b></code></pre>

<h4>Result</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~ 193. red/blue linear-gradient background (132) ~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image193.jpg"
  style="width:25%"
  title="Example; linear-gradient; Test I, Test II"
  alt="Example; linear-gradient; Test I, Test II." />
</p>
<!-- (./images/image193.jpg){width="2.4479166666666665in" height="1.3125in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch22">Chapter 22: Positioning</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b> | <b>Details</b> |
|------------------|-------------------|
| static | Default value. Elements render in order, as they appear in the document flow. |
|        | The top, right, bottom, left and z-index properties do not apply. |
| relative | The element is positioned relative to its normal position, so <b>left</b>:20px adds |
|          | 20 pixels to the element&aposs LEFT position. |
| fixed    | The element is positioned relative to the browser window. |
| absolute | The element is positioned relative to its first positioned (not static) ancestor element. |
| initial  | Sets this property to its default value. |
| inherit  | Inherits this property from its parent element. |
| sticky   | Experimental feature. It behaves like <b>position</b>: static within its parent until a given offset threshold }
|          | is reached, then it acts as <b>position</b>: fixed. |
| unset    | Combination of initial and inherit. More info <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/unset">here</a>. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch22-1">Section 22.1: Overlapping Elements with z-index</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To change the default <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context">stack order</a>
positioned elements (position property set to relative, absolute or fixed), use the z-index property.</p>

<p>The higher the z-index, the higher up in the stacking context (on the z-axis) it is placed.</p>

<b>Example</b>

In the example below, a z-index value of 3 puts green on top, a
z-index of 2 puts red just under it, and a z-index of 1 puts blue
under that.

<h4>HTML:</h4>

<pre><code><b>&lt;div</b> id=&quot;div1&quot;<b>&gt;</b><b>&lt;/div&gt;</b>
<b>&lt;div</b> id=&quot;div2&quot;<b>&gt;</b><b>&lt;/div&gt;</b>
<b>&lt;div</b> id=&quot;div3&quot;<b>&gt;</b><b>&lt;/div&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code>div {
  <b>position</b>: absolute;
  <b>height</b>: 200px;
  <b>width</b>: 200px;
}
div #div1 {
  <b>z-index</b>: 1;
  <b>left</b>: 0px;
  <b>top</b>: 0px;
  <b>background-color</b>: blue;
}
div #div2 {
  <b>z-index</b>: 3;
  <b>left</b>: 100px;
  <b>top</b>: 100px;
  <b>background-color</b>: green;
}
div #div3 {
  <b>z-index</b>: 2;
  <b>left</b>: 50px;
  <b>top</b>: 150px;
  <b>background-color</b>: red;
}</code></pre>

<h4>This creates the following effect:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 194.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image194.jpg"
  style="width:35%"
  title=""
  alt="." />
</p>
<!-- (./images/image194.jpg){width="3.6458333333333335in" height="3.8645833333333335in"} -->

<p>See a working example at <a href="https://jsfiddle.net/esnc10tq/">Demo (jsFiddle)</a>.</p>

<b>Syntax</b>

<pre><code><b>z-index</b>: &lbrack; number &rbrack; &vert; auto;</code></pre>

| <b>Parameter</b> | <b>Details</b> |
|--------------|---------------------------------------------|
| number       | An integer value. A higher number is higher on the z-index stack. 0 is the default value. Negative |
|              | values are allowed. |
| auto         | Gives the element the same stacking context as its parent. (<b>Default</b>) |

<h4><b>Remarks</b></h4>

<p>All elements are laid out in a 3D axis in CSS, including a depth axis,
measured by the z-index property. z-index only works on positioned
elements: (see: <a href="https://www.sitepoint.com/community/t/why-does-z-index-need-a-defined-position-to-work/46115">
Why does z-index need a defined position to work?</a>). The only value where it is 
ignored is the default value, static.</p>

<p>Read about the z-index property and Stacking Contexts in the 
<a href="https://drafts.csswg.org/css-position/#layered-presentation">CSS Specification</a> 
on layered presentation and at the <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/z-index">
Mozilla Developer Network</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch22-2">Section 22.2: Absolute Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When absolute positioning is used the box of the desired element is taken out 
of the <i>Normal Flow</i> and it no longer affects the position of the other elements 
on the page. Offset properties:</p>

1.  top
2.  left
3.  right
4.  bottom

<p>specify the element should appear in relation to its next non-static containing element.</p>

<pre><code>.abspos {
  <b>position</b>: absolute;
  <b>top</b>: 0px;
  <b>left</b>: 500px;
}</code></pre>

<p>This code will move the box containing element with attribute down 0px
and right 500px relative to its containing element.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch22-3">Section 22.3: Fixed position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Defining position as fixed we can remove an element from the document
flow and set its position relatively to the browser window. One
obvious use is when we want something to be visible when we scroll to
the bottom of a long page.</p>

<pre><code>
#stickyDiv {
  <b>position</b>: fixed;
  <b>top</b>: 10px;
  <b>left</b>: 10px;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch22-4">Section 22.4: Relative Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Relative positioning moves the element in relation to where it would have been 
in <i>normal flow</i> .Offset properties:</p>

1.  top
2.  left
3.  right
4.  bottom

<p>are used to indicate how far to move the element from where it would have been in normal flow.</p>

<pre><code>.relpos {
  <b>position</b>: relative;
  <b>top</b>: 20px;
  <b>left</b>: 30px;
}</code></pre>

<p>This code will move the box containing element with attribute class=&quot;relpos&quot; 
20px down and 30px to the right from where it would have been in normal flow.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch22-5">Section 22.5: Static positioning</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The default position of an element is static. To quote 
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/position#values">
MDN</a>:</p>

<blockquote>
  This keyword lets the element use the normal behavior, that is it is laid out in its current position in the 
  flow. The top, right, bottom, left and z-index properties do not apply.
</blockquote>

<pre><code>.element {
  <b>position</b>: static;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch23">Chapter 23: Layout Control</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

|<b>Value</b> | <b>Effect</b> |
|------------:|------------------------------------------|
| none | Hide the element and prevent it from occupying space. |
| block | Block element, occupy 100% of the available width, break after element. |
| inline | Inline element, occupy no width, no break after element. |
| inline-block | Taking special properties from both inline and block elements, no break, but can have width. |
| inline-flex | Displays an element as an inline-level flex container. |
| inline-table | The element is displayed as an inline-level table. |
| grid | Behaves like a block element and lays out its content according to the grid model. |
| flex | Behaves like a block element and lays out its content according to the flexbox model. |
| inherit | Inherit the value from the parent element. |
| initial | Reset the value to the default value taken from behaviors described in the HTML specifications or |
|         | from the browser/user default stylesheet. |
| table | Behaves like the HTML table element. |
| table-cell | Let the element behave like a <b>&lt;td&gt;</b> element. |
| table-column | Let the element behave like a <b>&lt;col&gt;</b> element. |
| table-row | Let the element behave like a <b>&lt;tr&gt;</b> element. |
| list-item | Let the element behave like a <b>&lt;li&gt;</b> element. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch23-1">Section 23.1: The display property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The display CSS property is fundamental for controlling the layout and flow of 
an HTML document. Most elements have a default display value of either block or 
inline (though some elements have other default values).</p>

<h4>Inline</h4>

<p>An inline element occupies only as much width as necessary. It stacks
horizontally with other elements of the same type and may not contain
other non-inline elements.</p>

<b>&lt;</b><b>span</b><b>&gt;</b>This is some <b>&lt;</b><b>b</b><b>&gt;</b>bolded<b>&lt;</b><b>/b</b><b>&gt;</b> text!<b>&lt;</b><b>/span</b><b>&gt;</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ section 23-1.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-23-1.png"
  style="width:25%"
  title="This is some bolded text"
  alt="This is some bolded text." />
</p>

<p>As demonstrated above, two inline elements, <b>&gt;</b>, are in-line (hence
the name) and do not break the flow of the text.</p>

<h4>Block</h4>

<p>A block element occupies the maximum available width of its&apos; parent
element. It starts with a new line and, in contrast to inline
elements, it does not restrict the type of elements it may contain.</p>

<pre><code><b>&lt;</b><b>div</b><b>&gt;</b>Hello world!<b>&lt;</b><b>/div</b><b>&gt;</b><b>&lt;</b><b>div</b><b>&gt;</b>This is an example!<b>&lt;</b><b>/div</b><b>&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ section 23-1-b.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-23-1-b.png"
  style="width:15%"
  title="Hello world! This is an example!"
  alt="Hello world! This is an example!" />
</p>

<p>The div element is block-level by default, and as shown above, the two
block elements are vertically stacked and, unlike the inline elements,
the flow of the text breaks.</p>

<b>Inline Block</b>

<p>The inline-block value gives us the best of both worlds: it blends the
element in with the flow of the text while allowing us to use padding,
margin, height and similar properties which have no visible effect on
inline elements.</p>

<p>Elements with this display value act as if they were regular text and
as a result are affected by rules controlling the flow of text such as
text-align. By default they are also shrunk to the the smallest size
possible to accommodate their content.</p>

<pre><code>&lt;!&minus;-Inline: unordered list&minus;-&gt;
<b>&lt;style&gt;</b>
li {
  display : inline;
  background : lightblue;
  padding:10px;
  border-width:2px;
  border-color:black;
  border-style:solid;
}
<b>&lt;/style&gt;</b>

<b>&lt;ul&gt;</b>
  <b>&lt;li&gt;</b>First Element <b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Second Element <b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Third Element <b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ section 23-1-c.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-23-1-c.png"
  style="width:40%"
  title="3 horizontal rectangles; First Element, Second Element, Third Element"
  alt="3 horizontal rectangles; First Element, Second Element, Third Element." />
</p>

<pre><code>&lt;!&minus;-block: unordered list&minus;-&gt;
<b>&gt;&lt;style&gt;</b>
li {
  display : block;
  background : lightblue;
  padding:10px;
  border-width:2px;
  border-color:black;
  border-style:solid;
}
<b>&lt;/style&gt;</b>

<b>ul&lt;&gt;</b>
  <b>&lt;li&gt;</b>First Element<b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Second Element<b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Third Element<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ section 23-1-d.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-23-1-d.png"
  style="width:60%"
  title="3 vertical rectangles; First Element, Second Element, Third Element"
  alt="3 vertical rectangles; First Element, Second Element, Third Element." />
</p>

<pre><code>&lt;!&minus;-Inline-block: unordered list&minus;-&gt;
<b>&lt;style&gt;</b>
li {
  display : inline-block;
  background : lightblue;
  padding:10px;
  border-width:2px;
  border-color:black;
  border-style:solid;
}
<b>&lt;/style&gt;</b>
<b>&lt;ul&gt;</b>
  <b>&lt;li&gt;</b>First Element <b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Second Element <b>&lt;/li&gt;</b>
  <b>&lt;li&gt;</b>Third Element <b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ section 23-1-e.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/section-23-1-e.png"
  style="width:40%"
  title="3 horizontal rectangles; First Element, Second Element, Third Element"
  alt="3 horizontal rectangles; First Element, Second Element, Third Element." />
</p>

<h4><b>none</b></h4>

<p>An element that is given the none value to its display property will
not be displayed at all.</p>

<p>For example let&apos;s create a div-element that has an id of myDiv:</p>

<pre><code><b>&lt;div</b> id=&quot;myDiv&quot;<b>&gt;&lt;/div&gt;</b></code></pre>

<p>This can now be marked as not being displayed by the following CSS rule:</p>

<pre><code>#myDiv {
  <b>display</b>: none;
}</code></pre>

<p>When an element has been set to be <b>display</b>:none; the browser ignores every other
layout property for that specific element (both position and float). No box will 
be rendered for that element and its existence in html does not affect the position 
of following elements.</p>

<p>Note that this is different from setting the visibility property to
hidden. Setting <b>visibility</b>: hidden; for an element would not display the element on the
page but the element would still take up the space in the rendering
process as if it would be visible. This will therefore affect how
following elements are displayed on the page.</p>

<p>The none value for the display property is commonly used along with
JavaScript to show or hide elements at will, eliminating the need to
actually delete and re-create them.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch23-2">Section 23.2: To get old table structure using div</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>This is the normal HTML table structure</h4>

<pre><code><b>&lt;style&gt;</b>
  table {
    width: 100%;
  }
<b>&lt;/style&gt;</b>
  <b>&lt;table&gt;</b>
    <b>&lt;tr&gt;</b>
      <b>&lt;td&gt;</b>
        I&apos;m a table
      <b>&lt;/td&gt;</b>
    <b>&lt;/tr&gt;</b>
  <b>&lt;/table&gt;</b></code></pre>

<p>You can do same implementation like this;</p>

<pre><code>
<b>&lt;style&gt;</b>
  .table-div {
    display: table;
  }
  .table-row-div {
    display: table-row;
  }
  .table-cell-div {
    display: table-cell; 
  }
<b>&lt;/style&gt;</b>

<b>&lt;div</b> class=&quot;table-div&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;table-row-div&quot;<b>&gt;</b>
    <b>&lt;div</b> class=&quot;table-cell-div&quot;<b>&gt;</b>
      I behave like a table now
    <b>&lt;/div&gt;</b>
  <b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b></code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch24">Chapter 24: Grid</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Grid layout is a new and powerful CSS layout system that allows to
divide a web page content into rows and columns in an easy way.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch24-1">Section 24.1: Basic Example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Property Possible Values</h4>
<p>display grid / inline-grid</p>

<p>The CSS Grid is defined as a display property. It applies to a parent element and its immediate children only.</p>

<p>Consider the following markup:</p>

<pre><code><b>&lt;</b><b>section</b> class=&quot;container&quot;<b>&gt;</b>
  <b>&lt;div</b> class=&quot;item1&quot;<b>&gt;</b>item1<b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;item2&quot;<b>&gt;</b>item2<b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;item3&quot;<b>&gt;</b>item3<b>&lt;/div&gt;</b>
  <b>&lt;div</b> class=&quot;item4&quot;<b>&gt;</b>item4<b>&lt;/div&gt;</b>
<b>&lt;/section&gt;</b></code></pre>

<p>The easiest way to define the markup structure above as a grid is to
simply set its display property to grid:</p>

<pre><code>.container {
  <b>display</b>: grid;
}</code></pre>

<p>However, doing this will invariably cause all the child elements to
collapse on top of one another. This is because the children do not
currently know how to position themselves within the grid. But we can
explicitly tell them.</p>

<p>First we need to tell the grid element .container how many rows and
columns will make up its structure and we can do this using the
grid-columns and grid-rows properties (note the pluralisation):</p>

<pre><code>.container {
  <b>display</b>: grid;
  <b>grid-columns</b>: 50px 50px 50px;
  <b>grid-rows</b>: 50px 50px;
}</code></pre>

<p>However, that still doesn&apos;t help us much because we need to give an
order to each child element. We can do this by specifying the grid-row
and grid-column values which will tell it where it sits in the grid:</p>

<pre><code>.container .item1 {
  <b>grid-column</b>: 1;
  <b>grid-row</b>: 1;
}
.container .item2 {
  <b>grid-column</b>: 2;
<b>grid-row</b>: 1;
}
.container .item3 {
  <b>grid-column</b>: 1;
  <b>grid-row</b>: 2;
}
.container .item4 {
  <b>grid-column</b>: 2;
  <b>grid-row</b>: 2;
}</code></pre>

<p>By giving each item a column and row value it identifies the items
order within the container.</p>

<p>View a working example on <a href="https://jsfiddle.net/fexfwkkv/3/">Demo (JS Fiddle)</a>.
You&apos;ll need to view this in IE10, IE11 or Edge for it to work as these are
currently the only browsers supporting Grid Layout (with vendor prefix
-ms-) or enable a flag in Chrome, Opera and Firefox according to
<a href="http://caniuse.com/#feat=css-grid">canIuse</a> in order to test with them.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch25">Chapter 25: Tables</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch25-1">Section 25.1: table-layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The table-layout property changes the algorithm that is used for the
layout of a table.</p>

<p>Below an example of two tables both set to: <b>width</b> 150px:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 200.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image200.jpg"
  style="width:45%"
  title=""
  alt="." />
</p>
<!-- (./images/image200.jpg){width="4.625in" height="1.125in"} -->

<p>The table on the left has <b>table-layout</b>: auto while the one on the right has 
<b>table-layout</b>: fixed. The former is wider than the specified width (210px 
instead of 150px) but the contents fit. The latter takes the defined width of 150px, 
regardless if the contents overflow or not.</p>

| <b>Value</b> | <b>Description</b> |
|--------------|--------------------|
| <i>auto</i>  | This is the default value. It defines the layout of the table to |
|              | be determined by the contents of its&apos; cells. |
| fixed        | This value sets the table layout to be determined by the width |
|              | property provided to the table. If the content fixed of a cell exceeds |
|              | this width, the cell will not resize but instead, let the content overflow. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch25-2">Section 25.2: empty-cells</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The empty-cells property determines if cells with no content should be
displayed or not. This has no effect unless border-collapse is set to
separate.

Below an example with two tables with different values set to the
empty-cells property:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 201.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image201.jpg"
  style="width:57%"
  title=""
  alt="." />
</p>
<!-- [imag201.jpg](./images/image201.jpg){width="5.708333333333333in" height="0.8854166666666666in"} -->

<p>The table on the left has <b>empty-cells</b>: show while the one on the right has 
<b>empty-cells</b>: hide. The former does display the empty cells whereas the latter does not.</p>

| <b>Value</b> | <b>Description</b>
|--------------|--------------------------|
| <i>show</i>  | This is the default value. It shows cells even if they are empty. |
| hide         | This value hides a cell altogether if there are no contents in the cell. |

<h4>More Information:</h4>
<ul>
  <li><a href="https://www.w3.org/TR/CSS21/tables.html#empty-cells">w3.org empty cells</a>.</li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells">Mozilla empty cells</a>.</li>
  <li><a href="http://codepen.io/SitePoint/pen/yfhtq">CodePen SitePoint</a>.</li>
  <li><a href="https://css-tricks.com/almanac/properties/e/empty-cells/">CSS Tricks empty cells.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch25-3">Section 25.3: border-collapse</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-collapse property determines if a tables&apos; borders should
be separated or merged.</p>

<p>Below an example of two tables with different values to the
border-collapse property:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 202.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image202.jpg"
  style="width:57%"
  title=""
  alt="." />
</p>
<!-- (./images/image202.jpg){width="5.666666666666667in" height="0.9270833333333334in"} -->

<p>The table on the left has <b>border-collapse</b>: separate while the one on the right has 

<b>border-collapse</b>: collapse.</p>

| <b>Value</b> | <b>Description</b> |
|--------------|-----------------------------------------------------|
| separate | This is the default value. It makes the borders of the table separate from each other. |
| collapse | This value sets the borders of the table to merge together, rather than being distinct. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch25-4">Section 25.4: border-spacing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The border-spacing property determines the spacing between cells. This
has no effect unless border-collapse is set to separate.</p>

<p>Below an example of two tables with different values to the
border-spacing property:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 203.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image203.jpg"
  style="width:60%"
  title=""
  alt="." />
</p>
<!-- (./images/image203.jpg){width="6.03125in" height="1.15625in"} -->

The table on the left has <b>border-spacing</b>: 2px (default) while the one on 
the right has <b>border-spacing</b>: 8px.

| <b>Value</b> | <b>Description</b> |
|--------------|--------------------------------------------|
| <i>&lt;length&gt;</i> | This is the default behavior, though the exact value can vary between browsers. |
| &lt;length&gt; &lt;length&gt; | This syntax allows specifying separate horizontal and vertical values respectively. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch25-5">Section 25.5: caption-side</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The caption-side property determines the vertical positioning of the <b>&lt;caption&gt;</b> 
element within a table. This has no effect if such element does not exist.</p>

<p>Below an example with two tables with different values set to the
caption-side property:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 204.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image204.jpg"
  style="width:57%"
  title=""
  alt="." />
</p>
<!-- (./images/image204.jpg){width="5.729166666666667in" height="1.1458333333333333in"} -->

<p>The table on the left has <b>caption-side</b>: top while the one on the right has 
<b>caption-side</b>: bottom.</p>

| <b>Value</b> | <b>Description</b> |
|--------------|-----------------------------------|
| <i>top</i>   | This is the default value. It places the caption above the table. |
| bottom       | This value places the caption below the table. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch26">Chapter 26: Transitions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b> | <b>Details</b> |
|-----------------|---------------------------------------|
| transition-property | The specific CSS property whose value change needs to be transitioned (or) all, if all the |
|                     | <a href="https://www.w3.org/TR/css3-transitions/">transitionable properties</a> need to be transitioned. |
| transition-duration | The duration (or period) in secdons (s) or milliseconds (ms) over which the transition |
|                     | must take place. |
| transition-timing-function | A function that describes how the intermediate values during the transition are |
|                    | calculated. Commonly used values are ease, ease-in, ease-out, ease-in-out, linear, |
|                    | cubic-bezier(), steps(). More information about the various timing functions can be |
|                    | found in the <a href="https://www.w3.org/TR/css3-transitions/#transition-timing-function">W3C specs</a>. |
| transition-delary  | The amount of time that must have elapsed before the transition can start. Can be |
|                    | specified in seconds (s) or milliseconds (ms). |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch26-1">Section 26.1: Transition shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>CSS</h4>

<pre><code>div {
  <b>width</b>: 150px;
  <b>height</b>: 150px;
  <b>background-color</b>: red;
  <b>transition</b>: background-color 1s;
}
div:hover {
  <b>background-color</b>: green;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div&gt;&lt;/div&gt;</b></code></pre>

<p>This example will change the background color when the div is hovered
the background-color change will last 1 second.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch26-2">Section 26.2: cubic-bezier</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The cubic-bezier function is a transition timing function which is
often used for custom and smooth transitions.</p>

<p><b>transition-timing-function</b>: cubic-bezier(0.1, 0.7, 1.0, 0.1);</p>

<p>The function takes four parameters:</p>

<p>cubic-bezier(P1_x, P1_y, P2_x, P2_y)</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 205.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image205.jpg"
  style="width:44%"
  title=""
  alt="." />
</p>
<!-- (./images/image205.jpg){width="4.395833333333333in" height="2.2083333333333335in"} -->

These parameters will be mapped to points which are part of a 
<a href="https://en.wikipedia.org/wiki/B%C3%A9zier_curve#Cubic_B.C3.A9zier_curves">Bézier curve</a>:</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 206.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image206.jpg"
  style="width:50%"
  title=""
  alt="." />
</p>
<!-- (./images/image206.jpg){width="4.96875in" height="4.958333333333333in"} -->

<p>For CSS Bézier Curves, P0 and P3 are always in the same spot. P0 is at
(0,0) and P3 is at (1,1), which menas that the parameters passed to
the cubic-bezier function can only be between 0 and 1.</p>

<p>If you pass parameters which aren&apos;t in this interval the function
will default to a linear transition.</p>

<p>Since cubic-bezier is the most flexible transition in CSS, you can
translate all other transition timing function to cubic-bezier functions:</p>

<pre><code>linear:cubic-bezier(0,0,1,1)

ease-in: cubic-bezier(0.42, 0.0, 1.0, 1.0)

ease-out: cubic-bezier(0.0, 0.0, 0.58, 1.0)

ease-in-out: cubic-bezier(0.42, 0.0, 0.58, 1.0)</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch26-3">Section 26.3: Transition (longhand)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>CSS</h4>

<pre><code>div {
  <b>height</b>: 100px;
  <b>width</b>: 100px;
  <b>border</b>: 1px solid;
  <b>transition-property</b>: height, width;
  <b>transition-duration</b>: 1s, 500ms;
  <b>transition-timing-function</b>: linear;
  <b>transition-delay</b>: 0s, 1s;
}
div: hover {
  <b>height</b>: 200px;
  <b>width</b>: 200px;
}</code></pre>

<h4>HTML:</h4>

<b>&lt;div&gt;&lt;/div&gt;</b>

<ul>
  <li><b>transition-property</b>: Specifies the CSS properties the transition
    effect is for. In this case, the div will expand both horizontally and
    vertically when hovered.</li>
  <li><b>transition-duration</b>: Specifies the length of time a transition
    takes to complete. In the above example, the height and width transitions 
	will take 1 second and 500 milliseconds respectively.</li>
  <li><b>transition-timing-function</b>: Specifies the speed curve of the transition 
    effect. A <i>linear</i> value indicates the transition will have the same speed from 
	start to finish.</li>
  <li><b>transition-delay</b>: Specifies the amount of time needed to wait before the 
    transition effect starts. In this case, the height will start transitioning 
	immediately, whereas the width will wait 1 second.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch27">Chapter 27: Animations</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>Transition</h4>

| Parameter     | Details                                            |
|---------------|------------------------------------------------------|
| property      | Either the CSS property to transition on, or all,  |
|               | which specifies all transition-able properties.    |
| duration      | Transition time, either in seconds or              |
|               | milliseconds.                                      |
| timing-function | Specifies a function to define how intermediate    |
|               | values for properties are computed. Common values  |
|               | are ease, linear, and step-end. Check out the      |
|               | <a href="http://easings.net/">easing function cheatsheet</a> for more. |
| delay         | Amount of time, in seconds or milliseconds, to     |
|               | wait before playing the animation.                 |

<h4>@keyframes</h4>

| &lbrack; from | to | <b>&lt;percentage&gt;</b> &rbrack; | You can either specify a set time with a percentage value, or two percentage values, IE |
|                                                       | 10%, 20%, for a period of time where the keyframe's set attributes are set. |
| block 												| Any amount of CSS attributes for the keyframe. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch27-1">Section 27.1: Animations with keyframes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
For multi-stage CSS animations, you can create CSS <span style="color:blue">&commat;keyframes</span>.
Keyframes allow you to define multiple animation points, called a
keyframe, to define more complex animations.

<h4>Basic Example</h4>

<p>In this example, we&apos;ll make a basic background animation that cycles
between all colors.</p>

<pre><code><span style="color:blue">&commat;keyframes</span> rainbow-background {</code></pre>

|--------:|------------------------------|
| 0&percnt; | { <b>background-color</b>: #ff0000; } |
| 8.333&percnt; | { <b>background-color</b>: #ff8000; } |
| 16.667&percnt; | { <b>background-color</b>: #ffff00; } |
| 25.000&percnt; | { <b>background-color</b>: #80ff00; } |
| 33.333&percnt; | { <b>background-color</b>: #00ff00; } |
| 41.667&percnt; | { <b>background-color</b>: #00ff80; } |
| 50.000&percnt; | { <b>background-color</b>: #00ffff; } |
| 58.333&percnt; | { <b>background-color</b>: #0080ff; } |
| 66.667&percnt; | { <b>background-color</b>: #0000ff; } |
| 75.000&percnt; | { <b>background-color</b>: #8000ff; } |
| 83.333&percnt; | { <b>background-color</b>: #ff00ff; } |
| 91.667&percnt; | { <b>background-color</b>: #ff0080; } |
| 100.00&percnt; | { <b>background-color</b>: #ff0000; } |
}

<pre><code>.RainbowBackground {
  <b>animation</b>: rainbow-background 5s infinite;
}</code></pre>

<p><a href="https://jsfiddle.net/s9m3od3p/6/">View Result</a>.</p>

There&apos;s a few different things to note here. First, the actual
<span style="color:blue">&commat;</span>keyframes syntax.

<pre><code><span style="color:blue">&commat;</span>keyframes rainbow-background{</code></pre>

This sets the name of the animation to rainbow-background.

<pre><code>0&percent;  { <b>background-color</b>: #ff0000; }</code>></pre> 

This is the definition for a keyframe within the animation. The first
part, the 0% in the case, defines where the keyframe is during the
animation. The 0% implies it is 0% of the total animation time from
the beginning.

The animation will automatically transition between keyframes. So, by
setting the next background color at 8.333%, the animation will
smoothly take 8.333% of the time to transition between those
keyframes.

<pre><code>.RainbowBackground {
  <b>animation</b>: rainbow-background 5s infinite;
}</code></pre>

This code attaches our animation to all elements which have the .RainbowBackground class.

<p>The actual animation property takes the following arguments;</p>

<ul>
  <li><b>animation-name</b>: The name of our animation. In this case, rainbow-background.</li>
  <li><b>animation-duration</b>: How long the animation will take, in this case 5 seconds.</li>
  <li><b>animation-iteration-count (Optional)</b>: The number of times the animation will loop. In this case, 
    the animation will go on indefinitely. By default, the animation will play once.</li>
  <li><b>animation-delay (Optional)</b>: Specifies how long to wait before the animation starts. It defaults to 0 seconds, 
    and can take negative values. For example, -2s would start the animation 2 seconds into its loop.</li>
  <li><b>animation-timing-function (Optional)</b>: Specifies the speed curve of the animation. It defaults to ease, 
    where the animation starts slow, gets faster and ends slow.</li>
</ul>

<p>In this particular example, both the 0% and 100% keyframes specify {;
}. Wherever two or more keyframes share a state, one may specify them in a single
statement. In this case, the two 0% and 100% lines could be replaced
with this single line:</p>

<pre><code>0&percnt;, 100&percnt; {
  <b>background-color</b>: #ff0000;
}</code></pre>

<h4>Cross-browser compatibility</h4>

<p>For older WebKit-based browsers, you&apos;ll need to use the vendor prefix
on both the &commat;keyframes declaration and the animation property, like
so:</p>

<pre><code><b>@-webkit-keyframes</b>{}
&minus;webkit-animation: &period;..</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch27-2">Section 27.2: Animations with the transition property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Useful for simple animations, the CSS transition property allows
number-based CSS properties to animate between states.

<b>Example</b>

.Example {
  <b>height</b>: 100px;
  <b>background</b>: #fff;
}
.Example: hover {
  <b>height</b>: 120px;
  <b>background</b>: #ff0000;
}

&lbrack;*&lbrack;View Result&rbrack;*&rbrack;(https://jsfiddle.net/0kcm6rwo/)

By default, hovering over an element with the .Example class would
immediately cause the element&apos;s height to jump to 120px and its
background color to red (#ff0000).

By adding the transition property, we can cause these changes to occur
over time:


.Example {
&period;..

<b>transition</b>: all 400ms ease;
}

&lbrack;*&lbrack;View Result&rbrack;*&rbrack;(https://jsfiddle.net/v2j4ggue/1/)

The all value applies the transition to all compatible (numbers-based)
properties. Any compatible property name (such as height or top) can
be substituted for this keyword.

400ms specifies the amount of time the transition takes. In this case,
the element&apos;s change in height will take 400 milliseconds to
complete.

Finally, the value ease is the animation function, which determines
how the animation is played. ease means start slow, speed up, then end
slow again. Other values are linear, ease-out, and ease-in.

<b>Cross-Browser Compatibility</b>

The transition property is generally well-supported across all major
browsers, excepting IE 9. For earlier versions of Firefox and
Webkit-based browsers, use vendor prefixes like so:

.Example {
  <b>transition</b>: all 400ms ease;
-moz-transition: all 400ms ease;
-webkit-transition: all 400ms ease;
}

*Note:* The transition property can animate changes between any two
numerical values, regardless of unit. It can also transition between
units, such as 100px to 50vh. However, it cannot transition between a
number and a default or automatic value, such as transitioning an
element&apos;s height from 100px to auto.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch27-3">Section 27.3: Syntax Examples</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Our first syntax example shows the animation shorthand property using
all of the available properties/parameters:

<b>animation</b>: 3s ease-in 1s 2 reverse both paused slidein;

/* duration &vert; timing-function &vert; delay &vert; iteration-count &vert;
direction &vert; fill-mode &vert; playstate &vert; name */

Our second example is a little more simple, and shows that some
properties can be omitted:

<b>animation</b>: 3s linear 1s slidein; /* duration &vert; timing-function
&vert; delay &vert; name */

Our third example shows the most minimal declaration. Note that the
animation-name and animation-duration must be declared:

<b>animation</b>: 3s slidein;

/* duration &vert; name */

It&apos;s also worth mentioning that when using the animation shorthand
the order of the properties makes a difference. Obviously the browser
may confuse your duration with your delay.

If brevity isn&apos;t your thing, you can also skip the shorthand property
and write out each property individually:

  <b>animation-duration</b>: 3s;
  <b>animation-timing-function</b>: ease-in;
  <b>animation-delay</b>: 1s;
  <b>animation-iteration-count</b>: 2;
  <b>animation-direction</b>: reverse;
  <b>animation-fill-mode</b>: both;
  <b>animation-play-state</b>: paused;
  <b>animation-name</b>: slidein;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch27-4">Section 27.4: Increasing Animation Performance Using the &apos;will-change&apos; Attribute</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

When creating animations and other GPU-heavy actions, it&apos;s important
to understand the will-change attribute.

Both CSS keyframes and the transition property use GPU acceleration.
Performance is increased by offloading calculations to the device&apos;s
GPU. This is done by creating paint layers (parts of the page that are
individually rendered) that are offloaded to the GPU to be calculated.
The will-change property tells the browser what will animate, allowing
the browser to create smaller paint areas, thus increasing
performance.

The will-change property accepts a comma-separated list of properties
to be animated. For example, if you plan on transforming an object and
changing its opacity, you would specify:

.Example {
&period;..

<b>will-change<b>: transform, opacity;
}

<b>Note:<b> Use will-change sparingly. Setting will-change for every
element on a page can cause performance problems, as the browser may
attempt to create paint layers for every element, significantly
increasing the amount of processing done by the GPU.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch28">Chapter 28: 2D Transforms</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>Function/Parameter Details<b>

  rotate

&lpar;x&rpar; Defines a transformation that moves the element around a fixed
point on the Z axis

  translate

(x,y) Moves the position of the element on the X and Y axis

  translateX

(x) Moves the position of the element on the X axis

  translateY

(y) Moves the position of the element on the Y axis

  scale

(x,y) Modifies the size of the element on the X and Y axis

  scaleX

  scaleY

&lpar;x&rpar; Modifies the size of the element on the X axis (y) Modifies the
size of the element on the Y axis

  skew

Shear mapping, or transvection, distorting each point of an element by
a certain angle in

(x,y) each direction

  skewX

Horizontal shear mapping distorting each point of an element by a
certain angle in the

(x) horizontal direction

  skewY

Vertical shear mapping distorting each point of an element by a
certain angle in the vertical

(y) direction

  matrix

() Defines a 2D transformation in the form of a transformation matrix.

  skew

The angle by which the element should be rotated or skewed (depending
on the function with which it is used). Angle can be provided in
degrees (deg), gradians (grad), radians (rad) angle or turns (turn).
In () function, the second angle is optional. If not provided, there
will be no (0) skew in Y-axis.

The distance expressed as a length or a percentage by which the
element should be

  translate

length-or-percentage translated. In () function, the second
length-or-percentage is optional. If not provided, then there would be
no (0) translation in Y-axis.

A number which defines how many times the element should be scaled in
the specified axis.

  scale

scale-factor In () function, the second scale-factor is optional. If
not provided, the first scale-factor will be applied for Y-axis also.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="28-1">Section 28.1: Rotate</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b><b>div</b> class=&quot;rotate&quot;<b>&gt;</b><b>&lt;</b><b>/div</b><b>&gt;</b>

<h4>CSS</h4>

.rotate {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>background</b>: teal;
  <b>transform</b>: rotate (45deg);
}

This example will rotate the div by 45 degrees clockwise. The center
of rotation is in the center of the div, 50% from left and 50% from
top. You can change the center of rotation by setting the
transform-origin property.

<b>transform-origin</b>: 100&percnt; 50&percnt;;

The above example will set the center of rotation to the middle of the
right side end.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 28.2: Scale
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b><b>div</b> class=&quot;scale&quot;<b>&gt;</b>
<b>&lt;</b><b>/div</b><b>&gt;</b>

<h4>CSS</h4>

.scale {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>background</b>: teal;
  <b>transform</b>: scale (0.5, 1.3);
}

  100px   &ast;   0.5    =   50px   on the X axis and to    100px   &ast;   1.3    =   130px

This example will scale the div to on the Y axis.

The center of the transform is in the center of the div, 50% from left
and 50% from top.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch28-3">Section 28.3: Skew</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<pre><code>
<b>&lt;</b><b>div</b> class=&quot;skew&quot;<b>&gt;</b>
<b>&lt;</b><b>/div</b><b>&gt;</b>
</code></pre>

<h4>CSS:</h4>

<pre><code>
.skew {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>background</b>: teal;
  <b>transform</b>: skew (20deg, -30deg);
}
</code></pre>

This example will skew the div by 20 degrees on the X axis and by - 30
degrees on the Y axis.

The center of the transform is in the center of the div, 50% from left
and 50% from top.

See the result
&lbrack;&lbrack;here&rbrack;&rbrack;(https://jsfiddle.net/MadalinaTn/gtt4osms/1/).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch28-4">Section 28.4: Multiple transforms</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Multiple transforms can be applied to an element in one property like this:

<b>transform</b>

:

rotate

(

15

deg

)

translateX

(

200

px

)

;

This will rotate the element 15 degrees clockwise and then translate
it 200px to the right.

In chained transforms, <b>the coordinate system moves with the
element</b>. This means that the translation won&apos;t be horizontal but on
an axis rotate 15 degrees clockwise as shown in the following image:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 207.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image207.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- (./images/image207.jpg){width="7.48037510936133in" height="2.7919728783902014in"} -->

Changing the order of the transforms will change the output. The first
example will be different to

<b>transform</b>

:

translateX

(

200

px

)

rotate

(

15

deg

)

;

<b>&lt;</b>

<b>div</b>

class

=

&quot;transform&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

.transform

{

<b>transform</b>

:

rotate

(

15

deg

)

translateX

(

200

px

)

;

}

As shown in this image:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 208.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image208.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- (./images/image208.jpg){width="7.48037510936133in" height="2.7919728783902014in"} -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch28-5">Section 28.5: Translate</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b><b>div</b> class=&quot;translate&quot;<b>&gt;</b><b>&lt;</b><b>/div</b><b>&gt;</b>

<h4>CSS</h4>

<pre><code>
.translate {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>background</b>: teal;
  <b>transform</b>: translate ( 200px, 50&percnt;);
}
</code></pre>

This example will move the div by 200px on the X axis and by on the Y
axis.

You can also specify translations on a single axis.

On the X axis:

<pre><code>
.translate {
  <b>transform</b>: translateX ( 200px );
}
</code></pre>

<p>On the Y axis:</p>

<pre><code>.translate {
  <b>transform</b>: translateY ( 50&percnt; );
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch28-6">Section 28.6: Transform Origin</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Transformations are done with respect to a point which is defined by
the transform-origin property.

  <b>transform-origin</b>                                   :   X Y

The property takes 2 values : ;

  <b>transform-origin</b>

  <b>transform-origin</b>                              :   100%


In the following example the first div (.tl) is rotate around the top
left corner with : 0 0; and the second (.tr)is transformed around
it&apos;s top right corner with 0. The rotation is applied <b>on hover</b> :

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
class
=
&quot;transform originl&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class
=
&quot;transform origin2&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

<h4>CSS:</h4>

<pre><code>
.transform
{
<b>display</b>
:
inline-block
;
<b>width</b>
:
200
px
;
<b>height</b>
:
100
px
;
<b>background</b>
:
teal
;
<b>transition</b>
:
transform
1
s
;
}
.origin1
{
<b>transform-origin</b>
:
0
0
;
}
.origin2
{
<b>transform-origin</b>
:
100
&percnt;
0
;
}
.transform
:
hover
{
<b>transform</b>
:
rotate
(
30
deg
)
;
}
</code></pre>

The default value for the transform-origin property is which is the
center of the element.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch29">Chapter 29: 3D Transforms</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch29-1">Section 29.1: Compass pointer or needle shape using 3D transforms</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

<pre><code>
div
.needle
{
<b>margin</b>
:
100
px
;
<b>height</b>
:
150
px
;
<b>width</b>
:
150
px
;
<b>transform</b>
:
rotateY
(
85
deg
)
rotateZ
(
45
deg
)
;
/* presentational */
<b>background-image</b>
:
linear-gradient
(
to
top
left
,
#555
0
&percnt;
,
#555
40
&percnt;
,
#444
50
&percnt;
,
#333
97
&percnt;
)
;
<b>box-shadow</b>
:
inset
6
px
6
px
22
px
8
px
#272727
;
}
</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
class
=
&apos;needle&apos;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

In the above example, a needle or compass pointer shape is created
using 3D transforms. Generally when we apply the rotate transform on
an element, the rotation happens only in the Z-axis and at best we
will end up with diamond shapes only. But when a rotateY transform is
added on top of it, the element gets squeezed in the Y-axis and thus
ends up looking like a needle. The more the rotation of the Y-axis the
more squeezed the element looks.

  rotateX           (   85deg        )   rotateZ              (   45deg
  ----------------- --- ------------ --- -------------------- --- ------------

The output of the above example would be a needle resting on its tip.
For creating a needle that is resting on its base, the rotation should
be along the X-axis instead of along Y-axis. So the transform
property&apos;s value would have to be something like );.

&lbrack;&lbrack;This pen&rbrack;&rbrack;(http://codepen.io/hari_shanx/pen/YXzoBo) uses
a similar approach to create something that resembles the Safari logo
or a compass dial.

<b>Screenshot of element with no transform:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 209.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image209.jpg"
  style="width:17%"
  title=""
  alt="." />
</p>
<!-- (./images/image209.jpg){width="1.6979166666666667in" height="1.6979166666666667in"} -->

<b>Screenshot of element with only 2D transform:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 210.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image210.jpg"
  style="width:25%"
  title=""
  alt="." />
</p>
<!-- (./images/image210.jpg){width="2.3541666666666665in" height="2.3645833333333335in"} -->

<b>Screenshot of element with 3D transform:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 211.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image211.jpg"
  style="width:7%"
  title=""
  alt="." />
</p>
<!-- [image211.jpg .739 x 2.47](./images/image211.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch29-2">Section 29.2: 3D text eect with shadow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
id
=
&quot;title&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
data-content
=
&quot;HOVER&quot;
<b>&gt;</b>
HOVER
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

<h4>CSS:</h4>

<pre><code>
&ast;
{
<b>margin</b>
:
0
;
<b>padding</b>
:
0
;
}
html
,
body
{
<b>height</b>
:
100
&percnt;
;
<b>width</b>
:
100
&percnt;
;
<b>overflow</b>
:
hidden
;
<b>background</b>
:
#0099CC
;
}
#title
{
<b>position</b>
:
absolute
;
<b>top</b>
:
50
&percnt;
;
<b>left</b>
:
50
&percnt;
;
<b>transform</b>
:
translate
(
-50
&percnt;
,
-50
&percnt;
)
;
<b>perspective-origin</b>
:
50
&percnt;
50
&percnt;
;
<b>perspective</b>
:
300
px
;
}
h1
{
<b>text-align</b>
:
center
;
<b>font-size</b>
:
12
vmin
;
<b>font-family</b>
:
&apos;Open Sans&apos;
,
sans-serif
;
<b>color</b>
:
rgba
(
0
,
0
,
0
,
0.8
)
;
<b>line-height</b>
:
1
em
;
<b>transform</b>
:
rotateY
(
50
deg
)
;
<b>perspective</b>
:
150
px
;
<b>perspective-origin</b>
:
0
&percnt;
50
&percnt;
;
}
h1
:
after
{
<b>content</b>
:
attr
(
data-content
)
;
<b>position</b>
:
absolute
;
<b>left</b>
:
0
;
<b>top</b>
:
0
;
<b>transform-origin</b>
:
50
&percnt;
100
&percnt;
;
<b>transform</b>
:
rotateX
(
-90
deg
)
;
<b>color</b>
:
#0099CC
;
}
#title
:
before
{
<b>content</b>
:
&apos;&apos;
;
<b>position</b>
:
absolute
;
<b>top</b>
:
-150
&percnt;
;
<b>left</b>
:
-25
&percnt;
;
<b>width</b>
:
180
&percnt;
;
<b>height</b>
:
328
&percnt;
;
<b>background</b>
:
rgba
(
255
,
255
,
255
,
0.7
)
;
<b>transform-origin</b>
:
0
100
&percnt;
;
<b>transform</b>
:
translatez
(
-200
px
)
rotate
(
40
deg
)
skewX
(
35
deg
)
;
<b>border-radius</b>
:
0
0
100
&percnt;
0
;
}
</code></pre>

&lbrack;&lbrack;View example with additional hover
effect&rbrack;&rbrack;(http://codepen.io/web-tiki/pen/azeKNy)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 212.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image212.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- (./images/image212.jpg){width="7.48037510936133in" height="3.642194881889764in"} -->

In this example, the text is transformed to make it look like it is
going into the screen away from the user.

The shadow is transformed accordingly so it follows the text. As it is
made with a pseudo element and the data attribute, it inherits the
transforms form it&apos;s parent (the H1 tag).

The white &quot;light&quot; is made with a pseudo element on the #title
element. It is skewed and uses border-radius for the rounded corner.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch29-3">Section 29.3: backface-visibility</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The backface-visibility property relates to 3D transforms.

With 3D transforms and the backface-visibility property, you&apos;re able
to rotate an element such that the original front of an element no
longer faces the screen.

For example, this would flip an element away from the screen:

&lbrack;&lbrack;JSFIDDLE&rbrack;&rbrack;(https://jsfiddle.net/3z3z843c/)

<b>&lt;</b>

<b>div</b>

class

=

&quot;flip&quot;

<b>&gt;</b>

Loren ipsum

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;flip back&quot;

<b>&gt;</b>

Lorem ipsum

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

.flip

{

-webkit-transform

:

rotateY

(

180

deg

)

;

-moz-transform

:

rotateY

(

180

deg

)

;

-ms-transform

:

rotateY

(

180

deg

)

;

-webkit-backface-visibility

:

visible

;

-moz-backface-visibility

:

visible

;

-ms-backface-visibility

:

visible

;

}

.flip

.back

{

-webkit-backface-visibility

:

hidden

;

-moz-backface-visibility

:

hidden

;

-ms-backface-visibility

:

hidden

;

}

Firefox 10+ and IE 10+ support backface-visibility without a prefix.
Opera, Chrome, Safari, iOS, and Android all need
-webkit-backface-visibility.

It has 4 values:

1.  <b>visible</b> (default) - the element will always be visible even when
    not facing the screen.

2.  <b>hidden</b> - the element is not visible when not facing the screen.

3.  <b>inherit</b> - the property will gets its value from the its parent
    element

4.  <b>initial</b> - sets the property to its default, which is visible

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch29-4">Section 29.4: 3D cube</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

3D transforms can be use to create many 3D shapes. Here is a simple 3D
CSS cube example:

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;cube&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;cubeFace&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;cubeFace face2&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

*CSS:*

body

{

<b>perspective-origin</b>

:

50

&percnt;

100

&percnt;

;

<b>perspective</b>

:

1500

px

;

<b>overflow</b>

:

hidden

;

}

.cube

{

<b>position</b>

:

relative

;

<b>padding-bottom</b>

:

20

&percnt;

;

<b>transform-style</b>

:

preserve-3d

;

<b>transform-origin</b>

:

50

&percnt;

100

&percnt;

;

<b>transform</b>

:

rotateY

(

45

deg

)

rotateX

(

0

)

;

}

.cubeFace

{
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 213.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image213.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- (./images/image213.png){width="7.486667760279965in" height="6.386666666666667in"} -->

<a href="http://codepen.io/web-tiki/pen/NNwqBa">View this example</a>

Additional styling is added in the demo and a transform is applied on
hover to view the 6 faces of the cube.

Should be noted that:

4 faces are made with pseudo elements chained transforms are applied

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch30">Chapter 30: Filter Property</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <b>Value Description</b> blur(x) Blurs the image by x pixels.
>
> Brightens the image at any value above 1.0 or 100%. Below that, the
> image will be brightness(x) darkened.
>
> Provides more contrast to the image at any value above 1.0 or 100%.
> Below that, the contrast(x) image will get less saturated.
>
> drop-shadow(h, v, x, y, z) Gives the image a drop-shadow. h and v can
> have negative values. x, y, and z are optional.
  | Value         | Description |
  |---------------|------------------------------------------------------|
  | greyscale(x)  | Shows the image in greyscale, with a maximum value of |
  |               | 1.0 or 100%. |
  | hue-rotate(x) | Applies a hue-rotation to the image. |
  | invert(x)     | Inverts the color of the image with a maximum value of |
  |               | 1.0 or 100%. |
  | opacity(x)    | Sets how opaque/transparent the image is with a |
  |               | maximum value of 1.0 or 100%. |
  | saturate(x)   | Saturates the image at any value above 1.0 or 100%. |
  |               | Below that, the image will start to de-saturate. |
  | sepia(x)      | Converts the image to sepia with a maximum value of |
  |               |  1.0 or 100%. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch30-1">Section 30.1: Blur</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

> <b>&lt;img</b> src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
> Duck&apos; <b>/&gt;</b>
>
> <h4>CSS</h4>

img

{

-webkit-filter

:

blur

(

1

px

)

;

<b>filter</b>

:

blur

(

1

px

)

;

}

> <b>Result</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 214.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image214.jpg"
  style="width:22%"
  title=""
  alt="." />
</p>
<!-- (./images/image214.jpg){width="2.2395833333333335in" height="2.8125in"} -->

> Makes you wanna rub your glasses.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch30-2">Section 30.2: Drop Shadow (use box-shadow instead if possible)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b>

<b>p</b>

<b>&gt;</b>

My shadow always follows me.

<b>&lt;</b>

<b>/p</b>

<b>&gt;</b>

> <h4>CSS</h4>

p

{

-webkit-filter

:

drop-shadow

(

10

px

10

px

1

px

green

)

;

<b>filter</b>

:

drop-shadow

(

10

px

10

px

1

px

green

)

;

}

> <b>Result</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 215.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image215.jpg"
  style="width:24%"
  title=""
  alt="." />
</p>
<!-- [image215 2.406 x .572](./images/image215.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch30-3">Section 30.3: Hue Rotate</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<p><b>&lt;img</b> src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
Duck&apos; <b>/&gt;</b></p>

<h4>CSS</h4>

img

{

-webkit-filter

:

hue-rotate

(

120

deg

)

;

<b>filter</b>

:

hue-rotate

(

120

deg

)

;

}

> <b>Result</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 216.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image216.jpg"
  style="width:22%"
  title=""
  alt="." />
</p>
<!-- (./images/image216.jpg){width="2.2604166666666665in" height="2.8125in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch30-4">Section 30.4: Multiple Filter Values</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To use multiple filters, separate each value with a space.</p>

<h4>HTML:</h4>

> <b>&lt;img</b> src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
> Duck&apos; <b>/&gt;</b>

<h4>CSS</h4>

img

{

-webkit-filter

:

brightness

(

200

&percnt;

)

grayscale

(

100

&percnt;

)

sepia

(

100

&percnt;

)

invert

(

100

&percnt;

)

;

<b>filter</b>

:

brightness

(

200

&percnt;

)

grayscale

(

100

&percnt;

)

sepia

(

100

&percnt;

)

invert

(

100

&percnt;

)

;

}

<h4>Result</h4>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 217.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image217.jpg"
  style="width:22%"
  title=""
  alt="." />
</p>
<!-- [image217 2.114 x 2.708](./images/image217.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch30-5">Section 30.5: Invert Color</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <h4>CSS</h4>

div

{

<b>width</b>

:

100

px

;

<b>height</b>

:

100

px

;

<b>background-color</b>

:

white

;

-webkit-filter

:

invert

(

100

&percnt;

)

;

<b>filter</b>

:

invert

(

100

&percnt;

)

;

}

> <b>Result</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 218.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image218.jpg"
  style="width:11%"
  title=""
  alt="." />
</p>
<!-- (./images/image218.jpg){width="1.1979166666666667in" height="1.1979166666666667in"} -->

> Turns from white to black.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch31">Chapter 31: Cursor Styling</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch31-1">Section 31.1: Changing cursor type</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>cursor</b>

:

value

;

> <b>Examples:</b>

<b>Value Description</b>

> none No cursor is rendered for the element auto Default. The browser
> sets a cursor help The cursor indicates that help is available wait
> The cursor indicates that the program is busy move The cursor
> indicates something is to be moved pointer The cursor is a pointer and
> indicates a link

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch31-2">Section 31.2: pointer-events</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The pointer-events property allows for control over how HTML elements
> respond to mouse/touch events.

.disabled

{

<b>pointer-events</b>

:

none

;

}

> In this example,

&apos;none&apos; prevents all click, state and cursor options on the specified
HTML element &lbrack;&lbrack;1&rbrack;&rbrack;

> Other valid values for HTMl elements are:
>
> auto; inherit.
>
> 1&period;
> &lbrack;&lbrack;https://css-tricks.com/almanac/properties/p/pointer-events/&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/p/pointer-events/)
>
> Other resources:
>
> &lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
> &lbrack;&lbrack;https://davidwalsh.name/pointer-events&rbrack;&rbrack;(https://davidwalsh.name/pointer-events)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch31-3">Section 31.3: caret-color</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The caret-color CSS property specifies the color of the caret, the
visible indicator of the insertion point in an element where text and
other content is inserted by the user&apos;s typing or editing.</p>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b><b>input</b> id=&quot;example&quot;<b>/&gt;</b>
</code></pre>

<h4>CSS</h4>

<pre><code>
#example {
  <b>caret-color</b>: red;
}
</code></pre>

<h4>Resources:</h4>

[!https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch32">Chapter 32: box-shadow</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>Parameters Details</b>

> by default, the shadow is treated as a drop shadow. the inset keyword
> draws the shadow inside the inset frame/border.
>
> offset-x the horizontal distance offset-y the vertical distance
>
> 0 by default. value cannot be negative. the bigger the value, the
> bigger and lighter the shadow blur-radius becomes.
>
> 0 by default. positive values will cause the shadow to expand.
> negative values will cause the shadow spread-radius to shrink.

  rgb()          ,   rgba()            ,   hsl()          ,   hsla()

color can be of various notations: a color keyword, hexadecimal,

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch32-1">Section 32.1: bottom-only drop shadow using a pseudoelement</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

JSFiddle:
&lbrack;&lbrack;https://jsfiddle.net/UnsungHero97/80qod7aL/2/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/2/)

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;box_shadow&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <h4>CSS</h4>

.box_shadow

{

<b>background-color</b>

:

#1C90F3

;

<b>width</b>

:

200

px

;

<b>height</b>

:

100

px

;

<b>margin</b>

:

50

px

;

}

.box_shadow

:

after

{

<b>content</b>

:

&quot;&quot;

;

<b>width</b>

:

190

px

;

<b>height</b>

:

1

px

;

<b>margin-top</b>

:

98

px

;

<b>margin-left</b>

:

5

px

;

<b>display</b>

:

block

;

<b>position</b>

:

absolute

;

<b>z-index</b>

:

&minus;

1

;

-webkit-box-shadow

:

0

px

0

px

8

px

2

px

#444444

;

-moz-box-shadow

:

0

px

0

px

8

px

2

px

#444444

;

<b>box-shadow</b>

:

0

px

0

px

8

px

2

px

#444444

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 220.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image220.jpg"
  style="width:62%"
  title=""
  alt="." />
</p>
<!-- [image220.jpg 6.25 x 3.75](./images/image220.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch32-2">Section 32.2: drop shadow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<a href="https://jsfiddle.net/UnsungHero97/80qod7aL/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/">Demo (JSFiddle):</a>

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;box_shadow&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<h4>CSS</h4>

<pre><code>
.box_shadow
{
-webkit-box-shadow
:
0
px
0
px
10
px
-1
px
#444444
;
-moz-box-shadow
:
0
px
0
px
10
px
-1
px
#444444
;
<b>box-shadow</b>
:
0
px
0
px
10
px
-1
px
#444444
;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch32-3">Section 32.3: inner drop shadow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b><b>div</b> class=&quot;box_shadow&quot;<b>&gt;</b><b>&lt;</b><b>/div</b><b>&gt;</b>
</code></pre>

<h4>CSS</h4>

<pre><code>
.box_shadow {
  <b>background-color</b>: #1C90F3;
  <b>width</b>: 200px;
  <b>height</b>: 100px;
  <b>margin</b>: 50px;
  -webkit-box-shadow: inset 0px 0px 10px 0px #444444;
  -moz-box-shadow: inset 0px 0px 10px 0px #444444;
  <b>box-shadow</b>: inset 0px 0px 10px 0px #444444;
}
</code></pre>

<h4>Result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 221.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image221.jpg"
  style="width:26%"
  title=""
  alt="." />
</p>
<!-- [image221.jpg 2.645 x 1.541](./images/image221.jpg) -->

<a href="https://jsfiddle.net/UnsungHero97/80qod7aL/1/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/1/">Demo (JSFiddle):</a>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch32-4">Section 32.4: multiple shadows</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<a href="https://jsfiddle.net/UnsungHero97/80qod7aL/5/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/5/">Demo (JSFiddle):</a>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b><b>div</b> class=&quot;box_shadow&quot;<b>&gt;</b><b>&lt;</b><b>/div</b><b>&gt;</b>
</code></pre>

> <h4>CSS</h4>

<pre><code>
.box_shadow {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>margin</b>: 100px;
  <b>box-shadow</b>: -52px -52px 0px 0px #f65314, 
                   52px -52px 0px 0px #7cbb00,
                  -52px 52px 0px 0px #00a1f1,
                   52px 52px 0px 0px #ffbb00;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 222.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image222.jpg"
  style="width:61%"
  title=""
  alt="." />
</p>
<!-- [image222 6.125 x 5.833](./images/image222.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch33">Chapter 33: Shapes for Floats</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<b>Parameter Details</b>

> A value of none means that the float area (the area that is used for
> wrapping content around a float none element) is unaffected. This is
> the default/initial value.

  inset     (),   circle      (),   ellipse       () or     polygon

> Refers to one among (). Using one of these functions and its
> basic-shape values the shape is defined.
>
> Refers to one among margin-box, border-box, padding-box, content-box.
> When only &lt;shape-box&gt; is
>
> shape-box provided (without &lt;basic-shape&gt;) this box *is the* shape.
> When it is used along with &lt;basic-shape&gt;, this acts as the reference
> box.
>
> When an image is provided as value, the shape is computed based on the
> alpha channel of the image image specified.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch33-1">Section 33.1: Shape Outside with Basic Shape -- circle()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> With the shape-outside CSS property one can define shape values for
> the float area so that the inline content wraps around the shape
> instead of the float&apos;s box.
>
> <h4>CSS</h4>

img: nth-of-type (1) {
<b>shape-outside</b>: circle (
80px at 50&percnt; 50&percnt;
);
  <b>float</b>: left;
  <b>width</b>: 200px;
}
img: nth-of-type (2) {
  <b>shape-outside</b>: circle (
80px at 50&percnt;
50&percnt;
);
<b>float</b>: right;
<b>width</b>: 200px;
}
p {
<b>text-align</b>: center;
<b>line-height</b>: 30px;
/* purely for demo */
}

<h4>HTML:</h4>

<b>&lt;img</b>
src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;<b>&gt;</b>

<b>&lt;img</b>
 src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;<b>&gt;</b>

<b>&lt;p&gt;</b>Some paragraph whose text content is required to be wrapped
such that it follows the curve of the circle on either side. And then
there is some filler text just to make the text long enough. Lorem
Ipsum Dolor Sit Amet&period;...<b>&lt;/p&gt;</b>

In the above example, both the images are actually square images and
when the text is placed without the shapeoutside property, it will not
flow around the circle on either side. It will flow around the
containing box of the image only. With shape-outside the float area is
re-defined as a *circle* and the content is made to flow around this
*imaginary circle* that is created using shape-outside.

The *imaginary circle* that is used to re-define the float area is a
circle with radius of 80px drawn from the center-mid point of the
image&apos;s reference box.

Below are a couple of screenshots to illustrate how the content would
be wrapped around when shape-outside is used and when it is not used.
<b>Output with shape-outside</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 223.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image223.jpg"
  style="width:33%"
  title=""
  alt="." />
</p>
<!-- (./images/image223.jpg){width="3.3333333333333335in" height="1.3229166666666667in"} -->

> <b>Output without shape-outside</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 224.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image224.jpg"
  style="width:33%"
  title=""
  alt="." />
</p>
<!-- (./images/image224.jpg){width="3.3333333333333335in" height="1.4895833333333333in"} -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch33-2">Section 33.2: Shape margin</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The shape-margin CSS property adds a *margin* to shape-outside.
>
> <h4>CSS</h4>

img

:

nth-of-type

(

1

)

{

<b>shape-outside</b>

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

<b>shape-margin</b>

:

10

px

;

<b>float</b>

:

left

;

<b>width</b>

:

200

px

;

}

img

:

nth-of-type

(

2

)

{

<b>shape-outside</b>

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

<b>shape-margin</b>

:

10

px

;

<b>float</b>

:

right

;

<b>width</b>

:

200

px

;

}

p

{

<b>text-align</b>

:

center

;

<b>line-height</b>

:

30

px

;

/* purely for demo */

}

<h4>HTML:</h4>
>
> <b>&lt;img</b>
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;<b>&gt;</b>
>
> <b>&lt;img</b>
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;<b>&gt;</b>
>
> <b>&lt;p&gt;</b>Some paragraph whose text content is required to be wrapped
> such that it follows the curve of the circle on either side. And then
> there is some filler text just to make the text long enough. Lorem
> Ipsum Dolor Sit Amet&period;...<b>&lt;/p&gt;</b>
>
> In this example, a 10px margin is added around the <b>shape</b> using
> shape-margin. This creates a bit more space between the *imaginary
> circle* that defines the float area and the actual content that is
> flowing around.


<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 225.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image225.jpg"
  style="width:33%"
  title=""
  alt="." />
</p>
<!-- (./images/image225.jpg){width="3.3333333333333335in" height="1.3958333333333333in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch34">Chapter 34: List Styles</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> <b>Value Description</b> list-style-type the type of list-item marker.
>
> list-style-position specifies where to place the marker
> list-style-image specifies the type of list-item marker initial sets
> this property to its default value inherit inherits this property from
> its parent element

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch34-1">Section 34.1: Bullet Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<pre><code>
<b>&lt;li</b>   <b>&gt;</b> elements inside a containing element (       <b>&lt;ul</b>   <b>&gt;</b>   <b>&lt;ol</b>
or       
</code></pre>

> A list consists of <b>&gt;</b>). Both the list items and the container can
>
> have margins and paddings which influence the exact position of the
> list item content in the document. The default values for the margin
> and padding may be different for each browser. In order to get the
> same layout crossbrowser, these need to be set specifically.
>
> Each list item gets a &apos;marker box&apos;, which contains the bullet
> marker. This box can either be placed inside or outside of the list
> item box.

<pre><code>
<b>list-style-position</b>
:
inside
;
<b>&lt;li</b>
</code></pre>

> places the bullet within the <b>&gt;</b> element, pushing the content to
> the right as needed.

<pre><code>
<b>list-style-position</b>: outside;
<b>&lt;li</b>
</code></pre>

> places the bullet left of the <b>&gt;</b> element. If there is not enough
> space in the padding of the containing element, the marker box will
> extend to the left even if it would fall off the page.
>
> Showing the result of inside and outside positioning:
> &lbrack;&lbrack;jsfiddle&rbrack;&rbrack;(https://jsfiddle.net/pqh3cxdp/)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch34-2">Section 34.2: Removing Bullets / Numbers</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Sometimes, a list should just not display any bullet points or
> numbers. In that case, remember to specify margin and padding.

<pre><code>
<b>&lt;</b>
<b>ul</b>
<b>&gt;</b>
<b>&lt;</b>
<b>li</b>
<b>&gt;</b>
first item
<b>&lt;</b>
<b>/li</b>
<b>&gt;</b>
<b>&lt;</b>
<b>li</b>
<b>&gt;</b>
second item
<b>&lt;</b>
<b>/li</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/ul</b>
<b>&gt;</b>
</code></pre>

> CSS

<pre><code>
ul
{
<b>list-style-type</b>
:
none
;
}
li
{
<b>margin</b>
:
0
;
<b>padding</b>
:
0
;
}
</code></pre>


<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch34-3">Section 34.3: Type of Bullet or Numbering</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>&lt;li</b>   <b>&gt;</b> tags within an unordered list (                     <b>&lt;ul</b>

> Specific for <b>&gt;</b>):
>
> <b>list-style</b>: disc; /* A filled circle (default) */
> <b>list-style</b>: circle; /* A hollow circle */ <b>list-style</b>:
> square; /* A filled square */ <b>list-style</b>: &apos;-&apos;; /* any
> string */

<b>&lt;li</b>   <b>&gt;</b> tags within an ordered list (                      <b>&lt;ol</b>

> Specific for <b>&gt;</b>):

<b>list-style</b>: decimal; /* Decimal numbers beginning with 1 (default)
*/ <b>list-style</b>: decimal-leading-zero;/* Decimal numbers padded by
initial zeros (01, 02, 03,* ... *10) */ <b>list-style</b>: lower-roman;
/* Lowercase roman numerals (i., ii., iii., iv., &period;..) */
<b>list-style</b>: upper-roman; /* Uppercase roman numerals (I., II.,
III., IV., &period;..) */ <b>list-style-type</b>: lower-greek; /* Lowercase
roman letters (*α*.,* β*.,* γ*.,* δ*., &period;..) */ <b>list-style-type</b>:
lower-alpha; /* Lowercase letters (a., b., c., d., &period;..) */
<b>list-style-type</b>: lower-latin; /* Lowercase letters (a., b., c.,
d., &period;..) */ <b>list-style-type</b>: upper-alpha; /* Uppercase letters
(A., B., C., D., &period;..) */ <b>list-style-type</b>: upper-latin; /*
Uppercase letters (A., B., C., D., &period;..) */ Non-specific:

> <b>list-style</b>: none; /* No visible list marker */ <b>list-style</b>:
> inherit; /* Inherits from parent */

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch35">Chapter 35: Counters</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| Parameter  | &gt; Details                                              |
|---------|------------------------------------------------------------|
| count   | This is the name of the counter that needs to be created   |
| er-name | or incremented or printed. It can be any custom name as    |
|         | the developer wishes.                                      |
| integer | This integer is an optional value that when provided next  |
|         | to the counter name will represent the initial value of    |
|         | the counter (in counter-set, counter-reset properties) or  |
|         | the value by which the counter should be incremented (in   |
|         | counter-increment).                                        |

<p>This is the initial value for all 3 &ast; properties. When this value is
used for counter-none increment, the value of none of the counters are affected. When
this is used for the other two, no counter is created.
This specifies the style in which the counter value needs to be
displayed. It supports all values counter-style supported by the list-style-type property. If none is used
then the counter value is not printed at all.</p>

<p>This represents the string that must be placed between the values of
two different counter levels connector-string (like the &quot;.&quot; in &quot;2.1.1&quot;).
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch35-1">Section 35.1: Applying roman numerals styling to the counter output</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

<pre><code>
body 
{
  <b>counter-reset</b>: item-counter;
}
.item {
  <b>counter-increment</b>: item-counter;
}
.item: before {
  <b>content</b>: counter (
item-counter, upper-roman 
)
&quot;. &quot;;
/* by specifying the upper-roman as style the
   output would be in roman numbers */
}
</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b><b>div</b> class=&apos;item&apos;<b>&gt;</b>Item No: 1<b>&lt;</b><b>/div</b><b>&gt;</b>
<b>&lt;</b><b>div</b> class=&apos;item&apos;<b>&gt;</b>Item No: 2<b>&lt;</b><b>/div</b><b>&gt;</b>
<b>&lt;</b><b>div</b> class=&apos;item&apos;<b>&gt;</b>Item No: 3<b>&lt;</b><b>/div</b><b>&gt;</b>
</code></pre>

<p>In the above example, the counter&apos;s output would be displayed as I,
II, III (roman numbers) instead of the usual 1, 2, 3 as the developer
has explicitly specified the counter&apos;s style.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch35-2">Section 35.2: Number each item using CSS Counter</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

<pre><code>
body {
  <b>counter-reset</b>: item-counter;
/* create the counter */
}
.item {
  <b>counter-increment</b>: item-counter;
/* increment the counter every time an element with class &quot;item&quot; is encountered */
}
.item-header: before {
  <b>content</b>: counter (item-counter)&quot;. &quot;;
/* print the value of the counter before the header and
  append a &quot;.&quot; to it */
}
/* just for demo */
.item {
  <b>border</b>: 1px solid;
  <b>height</b>: 100px;
  <b>margin-bottom</b>: 10px;
}
.item-header {
  <b>border-bottom</b>: 1px solid;
  <b>height</b>: 40px;
  <b>line-height</b>: 40px;
  <b>padding</b>: 5px;
}
.item-content {
  <b>padding</b>: 8px;
}
</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;div</b> class=&apos;item&apos;<b>&gt;</b>
<b>&lt;div</b> class=&apos;item-header&apos;<b>&gt;</b>
Item 1 Header<b>&lt;/div&gt;</b>
<b>&lt;div</b> class=&apos;item-content&apos;<b>&gt;</b>
Lorem Ipsum Dolor Sit Amet&period;...
<b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b>
<b>&lt;div</b> class=&apos;item&apos;<b>&gt;</b>
<b>&lt;div</b> class=&apos;item-header&apos;<b>&gt;</b>
Item 2 Header
<b>&lt;/div&gt;</b>
<b>&lt;div</b> class=&apos;item-content&apos;<b>&gt;</b>
Lorem Ipsum Dolor Sit Amet&period;...
<b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b>
<b>&lt;div</b> class=&apos;item&apos;<b>&gt;</b>
<b>&lt;div</b> class=&apos;item-header&apos;<b>&gt;</b>
Item 3 Header
<b>&lt;/div&gt;</b>
<b>&lt;div</b> class=&apos;item-content&apos;<b>&gt;</b>
Lorem Ipsum Dolor Sit Amet&period;...
<b>&lt;/div&gt;</b>
<b>&lt;/div&gt;</b>
</code></pre>

:before


<p>The above example numbers every &quot;item&quot; in the page and adds the
item&apos;s number before its header (using content property of
.item-header element&apos;s pseudo). A live demo of this code is available
&lbrack;&lbrack;here&rbrack;&rbrack;(https://jsfiddle.net/a7rmje3r/).</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch35-3">Section 35.3: Implementing multi-level numbering using CSS counters</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>CSS</h4>

<pre><code>
ul {
  <b>list-style</b>: none;
  <b>counter-reset</b>: list-item-number;
/* self nesting counter as name is same for all levels */
}
li {
<b>counter-increment</b>: list-item-number;
}
li: before {
  <b>content</b>: counters (list-item-number, &quot;.&quot;)&quot; &quot;;
/* usage of counters() function means value of
  counters at all higher levels are combined before printing */
}
</code></pre>

<h4>HTML:</h4>

<b>&lt;ul&gt;</b>
<b>&lt;li&gt;</b>

Level 1

<b>&lt;ul&gt;</b>
<b>&lt;li&gt;</b>

Level 1.1

<b>&lt;ul&gt;</b>
<b>&lt;li&gt;</b>

Level 1.1.1

<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b>
<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b>
<b>&lt;/li&gt;</b>
<b>&lt;li&gt;</b>

Level 2

<b>&lt;ul&gt;</b>
<b>&lt;li&gt;</b>

Level 2.1

<b>&lt;ul&gt;</b>
<b>&lt;li&gt;</b>

Level 2.1.1

<b>&lt;/li&gt;</b>
<b>&lt;li&gt;</b>

Level 2.1.2

<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b>
<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b>
<b>&lt;/li&gt;</b>
<b>&lt;li&gt;</b>

Level 3

<b>&lt;/li&gt;</b>
<b>&lt;/ul&gt;</b>

list-item-number   &lbrack;1&rbrack; (counter for second level) and     list-item-number
nests it under                           

> The above is an example of multi-level numbering using CSS counters.
> It makes use of the <i><b>self-nesting</b></i> concept of counters. Self
> nesting is a concept where if an element already has a counter with
> the given name but is having to create another then it creates it as a
> child of the existing counter. Here, the second level ul already
> inherits the list-item-number counter from its parent but then has to
> create its own list-item-number (for its children li) and so creates
> &lbrack;0&rbrack; (counter for first level). Thus it achieves the multi-level
> numbering.

counters   () function instead of  counter   () function because    counters

The output is printed using the () function is designed to prefix the
value of all higher level counters (parent) when printing the output.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch36">Chapter 36: Functions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch36-1">Section 36.1: calc() function</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Accepts a mathematical expression and returns a numerical value.

It is especially useful when working with different types of units
(e.g. subtracting a px value from a percentage) to calculate the value
of an attribute.

+, -, /, and &ast; operators can all be used, and parentheses can be
added to specify the order of operations if necessary.

Use

<pre><code>
calc (
)
to calculate the width of a div element:
#div1 {
  <b>position</b>: absolute;
  <b>left</b>: 50px;
  <b>width</b>: calc (100&percnt;
  &minus;
100px
);
  <b>border</b>: 1px solid black;
  <b>background-color</b>: yellow;
  <b>padding</b>: 5px;
  <b>text-align</b>: center;
}
</code></pre>

  calc

> Use () to determine the position of a background-image:

<pre><code>
<b>background-position</b>: calc (50&percnt;&plus; 17px)
calc (
50&percnt;&plus; 10px), 50&percnt; 50&percnt;;
</code></pre>

calc

> Use () to determine the height of an element:

<b>height</b>

:

calc

(

100&percnt;
&minus;
20px);

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch36-2">Section 36.2: attr() function</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> Returns the value of an attribute of the selected element.

  data-

  ::before                      and             ::after

> Below is a blockquote element which contains a character inside a &ast;
> attribute which CSS can use (e.g. inside the pseudo-element) using
> this function.

<pre><code>
<b>&lt;</b>
<b>blockquote</b>
data-mark
=
&apos;&quot;&apos;
<b>&gt;</b>
<b>&lt;</b>
<b>/blockquote</b>
<b>&gt;</b>
</code></pre>

> In the following CSS block, the character is appended before and after
> the text inside the element:

<pre><code>
blockquote
&lbrack;
data-mark
&rbrack;
::
before
,
blockquote
&lbrack;
data-mark
&rbrack;
::
after
{
<b>content</b>
:
attr
(
data-mark
)
;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch36-3">Section 36.3: var() function</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<p> The var() function allows CSS variables to be accessed.</p>

/* set a variable */

<pre><code>
:root{&minus;- primary-color: blue;}
/* access variable */
selector{
  <b>color</b>: var (
  &minus;-
  primary-color
  );
}
</code></pre>

<p> This feature is currently under development. Check 
<a href="http://caniuse.com/#feat=css-variables">CanIuse.com</a> 
for the latest browser support.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch36-4">Section 36.4: radial-gradient() function</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Creates an image representing a gradient of colors radiating from the
> center of the gradient
>
> radial-gradient(red, orange, yellow) /*A gradient coming out from
> the middle of the gradient, red at the center, then orange, until it
> is finally yellow at the edges*/

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch36-5">Section 36.5: linear-gradient() function</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Creates a image representing a linear gradient of colors.

<pre><code>
linear-gradient (
  0 deg, red, yellow 50&percnt;, blue
);
</code></pre>

<p>This creates a gradient going from bottom to top, with colors starting
at red, then yellow at 50%, and finishing in blue.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch37">Chapter 37: Custom Properties (Variables)</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS Variables allow authors to create reusable values which can be
used throughout a CSS document.</p>

<p>For example, it&apos;s common in CSS to reuse a single color throughout a
document. Prior to CSS Variables this would mean reusing the same
color value many times throughout a document. With CSS Variables the
color value can be assigned to a variable and referenced in multiple
places. This makes changing values easier and is more semantic than
using traditional CSS values.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch37-1">Section 37.1: Variable Color</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<pre><code>
:root {&minus;- red: #b00; &minus;-
blue: #4679bd; &minus;- grey: #ddd;
}
.Bx1
{
  <b>color</b>: var (&minus;- red);
  <b>background</b>: var(&minus;- grey);
  <b>border</b>: 1px solid var (
  &minus;- red);
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch37-2">Section 37.2: Variable Dimensions</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<pre><code>
:root {&minus;-W200: 200px;
&minus;- W 10: 10px;
}
.Bx2 {<b>width</b>: var (
  &minus;-W200
);
<b>height</b>: var (&minus;-W200);
<b>margin</b>: var (&minus;- W 10);
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch37-3">Section 37.3: Variable Cascading</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> CSS variables cascade in much the same way as other properties, and
> can be restated safely.
>
> You can define variables multiple times and only the definition with
> the highest specificity will apply to the element selected.
>
> Assuming this HTML:

<pre><code>
<b>&lt;</b>
<b>a</b>
class
=
&quot;button&quot;
<b>&gt;</b>
Button Green
<b>&lt;</b>
<b>/a</b>
<b>&gt;</b>
<b>&lt;</b>
<b>a</b>
class
=
&quot;button button_red&quot;
<b>&gt;</b>
Button Red
<b>&lt;</b>
<b>/a</b>
<b>&gt;</b>
<b>&lt;</b>
<b>a</b>
class
=
&quot;button&quot;
<b>&gt;</b>
Button Hovered On
<b>&lt;</b>
<b>/a</b>
<b>&gt;</b>
</code></pre>

> We can write this CSS:

<pre><code>
.button {&minus;- color: green;
  <b>padding</b>: .5rem;
  <b>border</b>: 1px solid var (&minus;- color);
  <b>color</b>: var (&minus;- color);
}
.button: hover {
  &minus;- color: blue;
}
.button_red {
  &minus;- color: red;
}
</code></pre>

<h4>And get this result:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 226.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image226.jpg"
  style="width:37%"
  title=""
  alt="." />
</p>
<!-- {width="3.71875in" height="0.6041666666666666in"} -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch37-4">Section 37.4: Valid/Invalids</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><b>Naming</b> When naming CSS variables, it contains only letters and
dashes just like other CSS properties (eg: lineheight,
-moz-box-sizing) but it should start with double dashes (&minus;-)</p>

//These are Invalids variable names

<pre><code>
&minus;-123
color
:
blue
;
&minus;-
&num;
<b>color</b>
:
red
;
&minus;-
bg
&lowbar;color
:
yellow
&minus;-
&dollar;
<b>width</b>
:
100
px
;
</code></pre>

//Valid variable names

<pre><code>
&minus;-
color
:
red
;
&minus;-
bg-color
:
yellow
&minus;-
width
:
100
px
;
</code></pre>

> <b>CSS Variables are case sensitive.</b>

/* The variable names below are all different variables */

<pre><code>
&minus;-
pcolor
:
;
&minus;-
Pcolor
:
;
&minus;-
pColor
:
;
</code></pre>

> <b>Empty Vs Space</b>

/* Invalid */
<pre><code>
&minus;-
color
:
;
</code></pre>

/* Valid */
<pre><code>
&minus;-
color
:
;
</code></pre>
/* space is assigned */

> <b>Concatenations</b>

/* Invalid - CSS doesn&apos;t support concatenation */
<pre><code>
.logo
{
&minus;-
logo-url
:
&apos;logo&apos;
;
<b>background</b>
:
url
(
&apos;assets/img/&apos;
var
(
&minus;-
logo-url
)
&apos;.png&apos;
)
;
}
</code></pre>

/* Invalid - CSS bug */

<pre><code>
.logo
{
&minus;-
logo-url
:
&apos;assets/img/logo.png&apos;
;
<b>background</b>
:
url
(
var
(
&minus;-
logo-url
)
)
;
}
</code></pre>

/* Valid */
<pre><code>
.logo
{
&minus;-
logo-url
:
url
(
&apos;assets/img/logo.png&apos;
)
;
<b>background</b>
:
var
(
&minus;-
logo-url
)
;
}
</code></pre>

> <b>Careful when using Units</b>

/* Invalid */
<pre><code>
&minus;-
width
:
10
;
<b>width</b>
:
var
(
&minus;-
width
)
px
;
/* Valid */
&minus;-
width
:
10
px
;
<b>width</b>
:
var
(
&minus;-
width
)
;
/* Valid */
&minus;-
width
:
10
;
<b>width</b>
:
calc
(
1
px
&ast;
var
(
&minus;-
width
)
)
;
/* multiply by 1 unit to convert */
<b>width</b>
:
calc
(
1
em
&ast;
var
(
&minus;-
width
)
)
;
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch37-5">Section 37.5: With media queries</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> You can re-set variables within media queries and have those new
> values cascade wherever they are used, something that isn&apos;t possible
> with pre-processor variables.
>
> Here, a media query changes the variables used to set up a very simple
> grid:
>
<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <h4>CSS</h4>

:

root

{

&minus;-

width

:

25

&percnt;

;

&minus;-

content

:

&apos;This is desktop&apos;

;

}

<b>&commat;media</b>

only screen and

(

<b>max-width</b>

:

767

px

)

{

:

root

{

&minus;-

width

:

50

&percnt;

;

&minus;-

content

:

&apos;This is mobile&apos;

;

}

}

<b>&commat;media</b>

only screen and

(

<b>max-width</b>

:

480

px

)

{

:

root

{

&minus;-

width

:

100

&percnt;

;

}

}

div

{

<b>width</b>

:

calc

(

var

(

&minus;-

width

)

&minus;

20

px

)

;

<b>height</b>

:

100

px

;

}

div

:

before

{

<b>content</b>

:

var

(

&minus;-

content

)

;

}

/* Other Styles */

body

{

<b>padding</b>

:

10

px

;

}

div

{

<b>display</b>

:

flex

;

<b>align-items</b>

:

center

;

<b>justify-content</b>

:

center

;

<b>font-weight</b>

:

bold

;

<b>float</b>

:

left

;

<b>margin</b>

:

10

px

;

<b>border</b>

:

4

px

solid

black

;

<b>background</b>

:

red

;

}

> You can try resizing the window in this &lbrack;&lbrack;CodePen
> Demo&rbrack;&rbrack;(https://codepen.io/mkumaran/pen/BZaXvz)
>
> Here&apos;s an animated screenshot of the resizing in action:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 227.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image227.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- (./images/image227.jpg){width="7.48037510936133in" height="4.327166447944007in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch38">Chapter 38: Single Element Shapes</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-1">Section 38.1: Trapezoid</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A trapezoid can be made by a block element with zero height (height of
0px), a width greater than zero and a border, that is transparent
except for one side:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 228.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image228.jpg"
  style="width:47%"
  title=""
  alt="." />
</p>
<!-- !&lbrack;&rbrack;(./images/image228.jpg){width="4.75in" height="1.96875in"} -->

> <b>HTML:</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;trapezoid&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.trapezoid

{

<b>width</b>

:

50

px

;

<b>height</b>

:

0

;

<b>border-left</b>

:

50

px

solid

transparent

;

<b>border-right</b>

:

50

px

solid

transparent

;

<b>border-bottom</b>

:

100

px

solid

black

;

}

> With changing the border sides, the orientation of the trapezoid can
> be adjusted.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-2">Section 38.2: Triangles</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> To create a CSS triangle define an element with a width and height of
> 0 pixels. The triangle shape will be formed using border properties.
> For an element with 0 height and width the 4 borders (top, right,
> bottom, left) each form a triangle. Here&apos;s an element with 0
> height/width and 4 different colored borders.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 229.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image229.jpg"
  style="width:16%"
  title=""
  alt="." />
</p>
< !-- (./images/image229.jpg){width="1.6666666666666667in" height="1.7083333333333333in"} -->

> By setting some borders to transparent, and others to a color we can
> create various triangles. For example, in the Up triangle, we set the
> bottom border to the desired color, then set the left and right
> borders to transparent. Here&apos;s an image with the left and right
> borders shaded slightly to show how the triangle is being formed.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 230.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image230.jpg"
  style="width:11%"
  title=""
  alt="." />
</p>
<!-- (./images/image230.jpg){width="1.1458333333333333in" height="1.1875in"} -->

> The dimensions of the triangle can be altered by changing the
> different border widths - taller, shorter, lopsided, etc. The examples
> below all show a 50x50 pixel triangle.
>
> <b>Triangle - Pointing Up</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;triangle-up&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

.triangle-up

{

<b>width</b>

:

0

;

<b>height</b>

:

0

;

<b>border-left</b>

:

25

px

solid

transparent

;

<b>border-right</b>

:

25

px

solid

transparent

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Down**

**&lt;**

**div**

class

=

&quot;triangle-down&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down

{

**width**

:

0

;

**height**

:

0

;

**border-left**

:

25

px

solid

transparent

;

**border-right**

:

25

px

solid

transparent

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Right**
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 233.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image233.jpg"
  style="width:14%"
  title=""
  alt="." />
</p>
<!-- (./images/image233.jpg){width="1.1458333333333333in" height="1.1875in"} -->

**&lt;**

**div**

class

=

&quot;triangle-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-right

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

25

px

solid

transparent

;

**border-bottom**

:

25

px

solid

transparent

;

**border-left**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Left**

**&lt;**

**div**

class

=

&quot;triangle-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-left

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

25

px

solid

transparent

;

**border-bottom**

:

25

px

solid

transparent

;

**border-right**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Up/Right**

**&lt;**

**div**

class

=

&quot;triangle-up-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-up-right

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-left**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Up/Left**

**&lt;**

**div**

class

=

&quot;triangle-up-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-up-left

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-right**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Down/Right**

**&lt;**

**div**

class

=

&quot;triangle-down-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down-right

{

**width**

:

0

;

**height**

:

0

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-left**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Down/Left**

**&lt;**

**div**

class

=

&quot;triangle-down-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down-left

{

**width**

:

0

;

**height**

:

0

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-right**

:

50

px

solid

transparent

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-3">Section 38.3: Circles and Ellipses</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **Circle**
>
> To create a **circle**, define an element with an equal width and
> height (a *square*) and then set the border-radius property of this
> element to 50%.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 239.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image239.jpg"
  style="width:11%"
  title=""
  alt="." />
</p>
<!-- (./images/image239.jpg){width="1.1458333333333333in" height="1.1875in"} -->

<h4>HTML:</h4>

**&lt;****div** class=&quot;circle&quot;**&gt;**
**&lt;****/div****&gt;**

> <h4>CSS</h4>

.circle

{

**width**

:

50

px

;

**height**

:

50

px

;

**background**

:

rgb

(

246

,

156

,

85

)

;

**border-radius**

:

50

&percnt;

;

}

> **Ellipse**
>
> An **ellipse** is similar to a circle, but with different values for
> width and height.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 240.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image240.jpg"
  style="width:10%"
  title=""
  alt="." />
</p>
<!-- {width="0.9375in" height="0.9375in"} -->

<h4>HTML:</h4>

<pre><code>
**&lt;**
**div**
class
=
&quot;oval&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
</code></pre>

> <h4>CSS</h4>

<pre><code>
.oval
{
**width**
:
50
px
;
**height**
:
80
px
;
**background**
:
rgb
(
246
,
156
,
85
)
;
**border-radius**
:
50
&percnt;
;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-4">Section 38.4: Bursts</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> A burst is similar to a star but with the points extending less
> distance from the body. Think of a burst shape as a square with
> additional, slightly rotated, squares layered on top.

  ::before                      and             ::after


> The additional squares are created using the psuedo-elements.
>
> **8 Point Burst**

  before


> An 8 point burst are 2 layered squares. The bottom square is the
> element itself, the additional square is created using the :
> pseudo-element. The bottom is rotated 20°, the top square is rotated
> 135°.

<pre><code>
**&lt;**
**div**
class
=
&quot;burst-8&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
.burst-8 {
background: rgb(246, 156, 85);
width: 40px;
height: 40px;
position: relative;
text-align: center;
-ms-transform: rotate(20deg);
transform: rotate(20eg);
}
.burst-8::before {
content: &quot;&quot;;
position: absolute;
top: 0;
left: 0;
height: 40px;
width: 40px;
background: rgb(246, 156, 85);
-ms-transform: rotate(135deg);
transform: rotate(135deg);
}
</code></pre>

> **12 Point Burst**

before
and:
after

> An 12 point burst are 3 layered squares. The bottom square is the
> element itself, the additional squares are created using the :
> pseudo-elements. The bottom is rotated 0°, the next square is rotated
> 30°, and the top is rotated 60°.

<pre><code>
**&lt;**
**div**
class
=
&quot;burst-12&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
.burst-12 {
width: 40px;
height: 40px;
position: relative;
text-align: center;
background: rgb(246, 156, 85);
}
.burst-12::before, .burst-12::after {
content: &quot;&quot;;
position: absolute;
top: 0;
left: 0;
height: 40px;
width: 40px;
background: rgb(246, 156, 85);
}
.burst-12::before {
-ms-transform: rotate(30deg);
transform: rotate(30deg);
}
.burst-12::after {
-ms-transform: rotate(60deg);
transform: rotate(60deg);
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-5">Section 38.5: Square</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> To create a square, define an element with both a width and height. In
> the example below, we have an element with a width and height of 100
> pixels each.

<pre><code>
**&lt;**
**div**
class
=
&quot;square&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
.square
{
**width**
:
100
px
;
**height**
:
100
px
;
**background**
:
rgb
(
246
,
156
,
85
)
;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-6">Section 38.6: Cube</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

skewX () 
and skewY

> This example shows how to create a cube using 2D transformation
> methods () on pseudo elements.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 244.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image244.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- {width="2.40625in" height="1.9479166666666667in"} -->

<h4>HTML:</h4>

<pre><code>
**&lt;**
**div**
class
=
&quot;cube&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
> **CSS:**
.cube
{
**background**
:
#dc2e2e
;
**width**
:
100
px
;
**height**
:
100
px
;
**position**
:
relative
;
**margin**
:
50
px
;
}
.cube
::
before
{
**content**
:
&apos;&apos;
;
**display**
:
inline-block
;
**background**
:
#f15757
;
**width**
:
100
px
;
**height**
:
20
px
;
**transform**
:
skewX
(
-40
deg
)
;
**position**
:
absolute
;
**top**
:
-20
px
;
**left**
:
8
px
;
}
.cube
::
after
{
**content**
:
&apos;&apos;
;
**display**
:
inline-block
;
**background**
:
#9e1515
;
**width**
:
16
px
;
**height**
:
100
px
;
**transform**
:
skewY
(
-50
deg
)
;
**position**
:
absolute
;
**top**
:
-10
px
;
**left**
:
100
&percnt;
;
}
&lbrack;**&lbrack;See demo&rbrack;**&rbrack;(https://jsfiddle.net/codename0/9po0r1L1/)
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch38-7">Section 38.7: Pyramid</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  skewY()

This example shows how to create a **pyramid** using borders and 2D
transformation methods and rotate() on pseudo elements.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 245.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image245.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- {width="2.1041666666666665in" height="1.8541666666666667in"} -->

<h4>HTML:</h4>

<pre><code>
**&lt;**
**div**
class
=
&quot;pyramid&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
</code></pre>

<h4>CSS:</h4>

<pre><code>
.pyramid
{
**width**
:
100
px
;
**height**
:
200
px
;
**position**
:
relative
;
**margin**
:
50
px
;
}
.pyramid
::
before
,
.pyramid
::
after
{
**content**
:
&apos;&apos;
;
**display**
:
inline-block
;
**width**
:
0
;
**height**
:
0
;
**border**
:
50
px
solid
;
**position**
:
absolute
;
}
.pyramid
::
before
{
**border-color**
:
transparent
transparent
#ff5656
transparent
;
**transform**
:
scaleY
(
2
)
skewY
(
-40
deg
)
rotate
(
45
deg
)
;
}
.pyramid
::
after
{
**border-color**
:
transparent
transparent
#d64444
transparent
;
**transform**
:
scaleY
(
2
)
skewY
(
40
deg
)
rotate
(
-45
deg
)
;
}
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch39">Chapter 39: Columns</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch39-1">Section 39.1: Simple Example (column-count)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The CSS multi-column layout makes it easy to create multiple columns
of text.

**Code**

**&lt;div** id=&quot;multi-columns&quot;**&gt;**Lorem ipsum dolor sit amet,
consectetur adipisicing elit, sed do eiusmod tempor incididunt ut
labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum
dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est
laborum**&lt;/div&gt;**

.multi-columns {

-moz-column-count: 2; -webkit-column-count: 2; **column-count**: 2; }

**Result**
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 246.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image246.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- {width="7.48037510936133in" height="3.572153324584427in"} -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch39-2">Section 39.2: Column Width</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The column-width property sets the minimum column width. If
column-count is not defined the browser will make as many columns as
fit in the available width.

**Code:**

**&lt;div** id=&quot;multi-columns&quot;**&gt;**

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
minim veniam, quis nostrud exercitation ullamco laboris nisi ut
aliquip ex ea commodo consequat. Duis aute irure dolor in
reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
culpa qui officia deserunt mollit anim id est laborum

**&lt;**

**/div**

**&gt;**

.multi-columns

{

-moz-column-width

:

100

px

;

-webkit-column-width

:

100

px

;

<b>column-width</b>

:

100

px

;

}

<h4>Result</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 247.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image247.jpg"
  style="width:60%"
  title=""
  alt="." />
</p>
<!-- {width="6.125in" height="3.7083333333333335in"} -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch40">Chapter 40: Multiple columns</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> CSS allows to define that element contents wrap into multiple columns
> with gaps and rules between them.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch40-1">Section 40.1: Create Multiple Columns</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <b>&lt;div</b> class=&quot;content&quot;<b>&gt;</b> Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt
> ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim
> veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl
> ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in
> hendrerit in vulputate velit esse molestie consequat, vel illum dolore
> eu feugiat nulla facilisis at vero eros et accumsan et iusto odio
> dignissim qui blandit praesent luptatum zzril delenit augue duis
> dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis
> eleifend option congue nihil imperdiet doming id quod mazim placerat
> facer possim assum. <b>&lt;/div&gt;</b>
>
> CSS

.content

{

&minus;

webkit-column-count

:

3

;

/* Chrome, Safari, Opera */

&minus;

moz-column-count

:

3

;

/* Firefox */

<b>column-count</b>

:

3

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch40-2">Section 40.2: Basic example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Consider the following HTML markup:
>
> <b>&lt;section&gt;</b> <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet, consetetur
> sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et
> dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam
> et justo duo dolores et ea rebum.<b>&lt;/p&gt;</b> <b>&lt;p&gt;</b> Stet clita kasd
> gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
> Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
> nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
> sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
> rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
> ipsum dolor sit amet.<b>&lt;/p&gt;</b> <b>&lt;p&gt;</b>Lorem ipsum dolor sit amet,
> consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut
> labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos
> et accusam et justo duo dolores et ea rebum. Stet clita kasd
> gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
> amet.<b>&lt;/p&gt; &lt;/section&gt;</b>
>
> With the following CSS applied the content is split into three columns
> separated by a gray column rule of two pixels.

section

{

<b>columns</b>

:

3

;

<b>column-gap</b>

:

40

px

;

<b>column-rule</b>

:

2

px

solid

gray

;

}

See a &lbrack;&lbrack;live sample of this on
JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/vjL9ewmb/).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch41">Chapter 41: Inline-Block Layout</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="41-1">Section 41.1: Justified navigation bar</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The horizontally justified navigation (menu) bar has some number of
> items that should be justified. The first (left) item has no left
> margin within the container, the last (right) item has no right margin
> within the container. The distance between items is equal, independent
> on the individual item width.

<h4>HTML:</h4>

<b>&lt;</b>

<b>nav</b>

<b>&gt;</b>

<b>&lt;</b>

<b>ul</b>

<b>&gt;</b>

<b>&lt;</b>

<b>li</b>

<b>&gt;</b>

abc

<b>&lt;</b>

<b>/li</b>

<b>&gt;</b>

<b>&lt;</b>

<b>li</b>

<b>&gt;</b>

abcdefghijkl

<b>&lt;</b>

<b>/li</b>

<b>&gt;</b>

<b>&lt;</b>

<b>li</b>

<b>&gt;</b>

abcdef

<b>&lt;</b>

<b>/li</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/ul</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/nav</b>

<b>&gt;</b>

<h4>CSS</h4>

nav

{

<b>width</b>

:

100

&percnt;

;

<b>line-height</b>

:

1.4

em

;

}

ul

{

<b>list-style</b>

:

none

;

<b>display</b>

:

block

;

<b>width</b>

:

100

&percnt;

;

<b>margin</b>

:

0

;

<b>padding</b>

:

0

;

<b>text-align</b>

:

justify

;

<b>margin-bottom</b>

:

-1.4

em

;

}

ul

:

after

{

<b>content</b>

:

&quot;&quot;

;

<b>display</b>

:

inline-block

;

<b>width</b>

:

100

&percnt;

;

}

li

{

<b>display</b>

:

inline-block

;

}

> <b>Notes</b>

  after


The nav, ul and li tags were chosen for their semantic meaning of &apos;a
list of navigation (menu) items&apos;. Other tags may also be used of
course.

The : pseudo-element causes an extra &apos;line&apos; in the ul and thus an
extra, empty height of this block, pushing other content down. This is
solved by the negative margin-bottom, which has to have the same
magnitude as the line-height (but negative).

If the page becomes too narrow for all the items to fit, the items
will break to a new line (starting from the right) and be justified on
this line. The total height of the menu will grow as needed.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch42">Chapter 42: Inheritance</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch42-1">Section 42.1: Automatic inheritance</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Inheritance the a fundamental mechanism of CSS by which the computed
> values of some properties of an element are applied to its&apos; children.
> This is particularly useful when you want to set a global style to
> your elements rather than having to set said properties to each and
> every element in your markup.
>
> Common properties that are automatically inherited are: font, color,
> text-align, line-height.
>
> Assume the following stylesheet:

#myContainer

{

<b>color</b>

:

red

;

<b>padding</b>

:

5

px

;

}

  <b>color</b>   :   red   not only to the  <b>&lt;div</b>   <b>&gt;</b> element but also to <b>&lt;h3</b>   <b>&gt;</b>   <b>&lt;p</b>

> This will apply <b>&gt;</b> elements. However, due to the nature of padding
> its value will <b>*not*</b> be inherited to those elements.

<b>&lt;</b>

<b>div</b>

id

=

&quot;myContainer&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>h</b>

<b>3</b>

<b>&gt;</b>

Some header

<b>&lt;</b>

<b>/h</b>

<b>3</b>

<b>&gt;</b>

<b>&lt;</b>

<b>p</b>

<b>&gt;</b>

Some paragraph

<b>&lt;</b>

<b>/p</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch42-2">Section 42.2: Enforced inheritance</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Some properties are not automatically inherited from an element down
> to its&apos; children. This is because those properties are typically
> desired to be unique to the element (or selection of elements) to
> which the property is applied to. Common such properties are margin,
> padding, background, display, etc.
>
> However, sometimes inheritance is desired anyway. To achieve this, we
> can apply the inherit value to the property that should be inherited.
> The inherit value can be appied to *any* CSS property and *any* HTML
> element.
>
> Assume the following stylesheet:

#myContainer

{

<b>color</b>

:

red

;

<b>padding</b>

:

5

px

;

}

#myContainer

p

{

<b>padding</b>

:

inherit

;

}

  <b>color</b>   :   red       to both the              <b>&lt;h3</b>   <b>&gt;</b> and   <b>&lt;p</b>


> This will apply <b>&gt;</b> elements due to the inheritance nature of the
> color property.

  <b>&lt;p</b>


> However, the <b>&gt;</b> element will also inherit the padding value from
> its&apos; parent because this was specified.

<b>&lt;</b>

<b>div</b>

id

=

&quot;myContainer&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>h</b>

<b>3</b>

<b>&gt;</b>

Some header

<b>&lt;</b>

<b>/h</b>

<b>3</b>

<b>&gt;</b>

<b>&lt;</b>

<b>p</b>

<b>&gt;</b>

Some paragraph

<b>&lt;</b>

<b>/p</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch43">Chapter 43: CSS Image Sprites</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch43-1">Section 43.1: A Basic Implementation</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <b>What&apos;s an image sprite?</b>
>
> An image sprite is a single asset located within an image sprite
> sheet. An image sprite sheet is an image file that contains more than
> one asset that can be extracted from it.
>
> For example:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 248.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image248.jpg"
  style="width:17%"
  title=""
  alt="." />
</p>
<!-- (./images/image248.jpg){width="1.75in" height="1.875in"} -->

> The image above is an image sprite sheet, and each one of those stars
> is a sprite within the sprite sheet. These sprite sheets are useful
> because they improve performance by reducing the number of HTTP
> requests a browser might have to make.
>
> So how do you implement one? Here&apos;s some example code.
>
<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;icon icon1&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;icon icon2&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;icon icon3&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<h4>CSS:</h4>

.icon

{

<b>background</b>

:

url

(

"

icons-sprite.png

"

)

;

<b>display</b>

:

inline-block

;

<b>height</b>

:

20

px

;

<b>width</b>

:

20

px

;

}

.icon1

{

<b>background-position</b>

:

0

px

0

px

;

}

.icon2

{

<b>background-position</b>

:

-20

px

0

px

;

}

.icon3

{

<b>background-position</b>

:

-40

px

0

px

;

}

By using setting the sprite&apos;s width and height and by using the
background-position property in CSS (with an x and y value) you can
easily extract sprites from a sprite sheet using CSS.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch44">Chapter 44: Clipping and Masking</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Parameter</b>          | <b>Details</b>                                          |
|-------------|--------------------------------------------------------|
| clip-source | A URL which can point to an inline SVG element (or) an |
|             | SVG element in an external file that contains the clip |
|             | path&apos;s definition.                                    |
| basic-shape | Refers to one among inset(), circle(), ellipse() or polygon. Using one of these |
|             | functions the clipping path is defined. These shape functions work exactly the same way as |
|             | they do in Shapes for Floats. |
|  clip-geometry-box | This can have one among content-box, padding-box, border-box, margin-box, fill-box, |
|                    | stroke-box, view-box as values. When this is provided without any value for &lt;basic-shape&gt;, |
|                    | the edges of the corresponding box is used as the path for clipping. When used with a |
|                    | &lt;basic-shape&gt;, this acts as the reference box for the shape. |
| mask-reference     | This can be none or an image or a reference URL to a mask image source. |
| repeat-style       | This specifies how the mask should be repeated or tiled in the X and Y axes. The supported |
|                    | values are repeat-x, repeat-y, repeat, space, round, no-repeat. |
| mask-mode          | Can be alpha or luminance or auto and indicates whether the mask should be treated as a |
|                    | alpha mask or a luminance mask. If no value is provided and the mask-reference is a direct |
|                    | image then it would be considered as alpha mask (or) if the mask-reference is a URL then it |
|                    | would be considered as luminance mask. |
| position           | This specifies the position of each mask layer and is similar in behavior to the background- |
|                    | position property. The value can be provided in 1 value syntax (like top, 10%) or in 2 value |
|                    | syntx (like top right, 50% 50%). |
| geometry-box       | This specifies the box to which the mask should be clipped (<i>mask painting area</i>) or the box |
|                    | which should be used as reference for the mask&apos;s origin (<i>mask positioning area</i>) depending |
|                    | on the property. The list of possible values are content-box, padding-box, border-box, |
|                    | margin-box, fill-box, stroke-box, view-box. Detailed explanation of how each of those |
|                    | values work is available in the <a href="https://www.w3.org/TR/css-masking/#the-mask-clip">W3C Spec</a>. |
| bg-size            | This represents the size of each mask-image layer and has the same syntax as background- |
|                    | size. The value can be length or percentage or auto or cover or contain. Length, percentage |
|                    | and auto can either be provided as a single value or as one for each axis. |
| compositing-operator | This can be any one among add, subtract, exclude, multiply per layer and defines the type |
|                      | compositing operation that should be used for this layer with those below it. Detailed |
|                      | explanation about each value is available in the <a href="https://www.w3.org/TR/css-masking/#the-mask-composite">W3C Specs</a>. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-1">Section 44.1: Clipping and Masking: Overview and Dierence</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

With <b>Clipping</b> and <b>Masking</b> you can make some specified parts of
elements transparent or opaque. Both can be applied to any HTML
element.

<b>Clipping</b>

  circle          (),     polygon           () or        ellipse


Clips are vector paths. Outside of this path the element will be
transparent, inside it&apos;s opaque. Therefore you can define a clip-path
property on elements. Every graphical element that also exists in SVG
you can use here as a function to define the path. Examples are ().
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 249.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image249.jpg"
  style="width:33%"
  title=""
  alt="." />
</p>
<!-- (./images/image249.jpg){width="3.3333333333333335in" height="2.71875in"} -->

Example

<b>clip-path</b>

:

circle

(

100

px

at

center

)

;

The element will be only visible inside of this circle, which is
positioned at the center of the element and has a radius of 100px.

<b>Masking</b>

Masks are similar to Clips, but instead of defining a path you define
a mask what layers over the element. You can imagine this mask as an
image what consist of mainly two colors: black and white.

<b>Luminance Mask</b>: Black means the region is opaque, and white that
it&apos;s transparent, but there is also a grey area which is
semi-transparent, so you are able to make smooth transitions.

<b>Alpha Mask</b>: Only on the transparent areas of the mask the element
will be opaque.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 250.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image250.jpg"
  style="width:33%"
  title=""
  alt="." />
</p>
<!-- (./images/image250.jpg){width="3.3333333333333335in" height="2.0625in"} -->

This image for example can be used as a luminance mask to make for an
element a very smooth transition from right to left and from opaque to
transparent.

The mask property let you specify the the mask type and an image to be
used as layer.

Example

<b>mask</b>

:

url

(

masks

.svg

#rectangle

)

luminance

;

An element called rectangle defined in masks.svg will be used as an
<b>luminance mask</b> on the element.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-2">Section 44.2: Simple mask that fades an image from solid to transparent</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS:</h4>

div

{

<b>height</b>

:

200

px

;

<b>width</b>

:

200

px

;

<b>background</b>

:

url

(

http

:

//lorempixel.com/

200

/

200

/nature/

1

)

;

<b>mask-image</b>

:

linear-gradient

(

to

right

,

white

,

transparent

)

;

}

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

> In the above example there is an element with an image as its
> background. The mask that is applied on the image (using CSS) makes it
> look as though it is fading out from left to right.
>
> The masking is achieved by using a linear-gradient that goes from
> white (on the left) to transparent (on the right) as the mask. As it
> is an alpha mask, image becomes transparent where the mask is
> transparent.
>
> <b>Output without the mask:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 251.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image251.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image251.jpg 2.18 x 2.18](./images/image251.jpg) -->

> <b>Output with the mask:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 252.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image252.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image252.jpg 2.18 x 2.18](./images/image252.jpg) -->

<p><b>Note:</b> As mentioned in remarks, the above example would work in
Chrome, Safari and Opera only when used with the -webkit prefix. This
example (with a linear-gradient as mask image) is not yet supported in
Firefox.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-3">Section 44.3: Clipping (Circle)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS:</h4>

<pre><code>
div
{
<b>width</b>
:
200
px
;
<b>height</b>
:
200
px
;
<b>background</b>
:
teal
;
<b>clip-path</b>
:
circle
(
30
&percnt;
at
50
&percnt;
50
&percnt;
)
;
/* refer remarks before usage */
}
</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

> This example shows how to clip a div to a circle. The element is
> clipped into a circle whose radius is 30% based on the dimensions of
> the reference box with its center point at the center of the reference
> box. Here since no &lt;clipgeometry-box&gt; (in other words, reference
> box) is provided, the border-box of the element will be used as the
> reference box.
>
> The circle shape needs to have a radius and a center with (x,y)
> coordinates:

circle

<pre><code>
(
radius at x y
)
</code></pre>

&lbrack;<b>&lbrack;View Example&rbrack;</b>&rbrack;(https://jsfiddle.net/webtiki/qp69n494/)
<b>Output:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 253.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image253.jpg"
  style="width:25%"
  title=""
  alt="." />
</p>
<!-- [image253.jpg 2.468 x 2.229](./images/image253.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-4">Section 44.4: Clipping (Polygon)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS:</h4>

<pre><code>
div
{
<b>width</b>
:
200
px
;
<b>height</b>
:
200
px
;
<b>background</b>
:
teal
;
<b>clip-path</b>
:
polygon
(
0
0
,
0
100
&percnt;
,
100
&percnt;
50
&percnt;
)
;
/* refer remarks before usage */
}
</code></pre>

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

In the above example, a <b>polygonal</b> clipping path is used to clip
the square (200 x 200) element into a triangle shape. The output shape
is a triangle because the path starts at (that is, first coordinates
are at) 0 0 - which is the top-left

  100%   &minus; which is bottom-left corner of the box and then       100% 50%
         finally to                                               


corner of the box, then goes to 0 which is

nothing but the right-middle point of the box. These paths are self
closing (that is, the starting point will be the ending point) and so
the final shape is that of a triangle.

This can also be used on an element with an image or a gradient as
background.

&lbrack;<b>&lbrack;View Example&rbrack;</b>&rbrack;(https://jsfiddle.net/eoa4a94k/)

<b>Output:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 254.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image254.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image254.jpg 2.16 x 2.16](./images/image254.jpg) -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-5">Section 44.5: Using masks to cut a hole in the middle of an image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS:</h4>

<pre><code>
div {
  <b>width</b>: 200px;
  <b>height</b>: 200px;
  <b>background</b>: url (http://lorempixel.com/ 200/200/abstract/6);
  <b>mask-image</b>: radial-gradient (
    circle
    farthest-side at
    center,
    transparent
    49&percnt;,
    white 50&percnt;
    );
/* check remarks before using */
  }
</code></pre>

<h4>HTML:</h4>

In the above example, a transparent circle is created at the center
using radial-gradient and this is then used as a mask to produce the
effect of a circle being cut out from the center of an image.

<b>Image without mask:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 255.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image255.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image255.jpg 2.16 x 2.16](./images/image255.jpg) -->

<b>Image with mask:</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 256.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image256.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image256.jpg 2.16 x 2.16](./images/image256.jpg) -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch44-6">Section 44.6: Using masks to create images with irregular shapes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS:</h4>

div

{

/* check remarks before usage */

<b>height</b>

:

200

px

;

<b>width</b>

:

400

px

;

<b>background-image</b>

:

url

(

http

:

//lorempixel.com/

400

/

200

/nature/

4

)

;

<b>mask-image</b>

:

linear-gradient

(

to

top

right

,

transparent

49.5

&percnt;

,

white

50.5

&percnt;

)

,

linear-gradient

(

to

top

left

,

transparent

49.5

&percnt;

,

white

50.5

&percnt;

)

,

linear-gradient

(

white

,

white

)

;

<b>mask-size</b>

:

75

&percnt;

25

&percnt;

,

25

&percnt;

25

&percnt;

,

100

&percnt;

75

&percnt;

;

<b>mask-position</b>

:

bottom

left

,

bottom

right

,

top

left

;

<b>mask-repeat</b>

:

no-repeat

;

}

<h4>HTML:</h4>

<pre><code>
<b>&lt;</b>
<b>div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
</code></pre>

<p>In the above example, three linear-gradient images (which when placed
in their appropriate positions would cover 100% x 100% of the
container&apos;s size) are used as masks to produce a transparent
triangular shaped cut at the bottom of the image.</p>

<h4>Image without the mask:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 257.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image257.jpg"
  style="width:40%"
  title=""
  alt="." />
</p>
<!-- [image257.jpg 4.25 x 2.167](./images/image257.jpg) -->

<h4>Image with the mask:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 258.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image258.jpg"
  style="width:40%"
  title=""
  alt="." />
</p>
<!-- [image258.jpg 4.26 x 2.21](./images/image258.jpg) -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch45">Chapter 45: Fragmentation</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>Value</b> | <b>Description</b> |
|---------|-----------------------------------------------------|
| auto    | Default. Automatic page breaks. |
| always  | Always insert a page break. |
| avoid   | Avoid page break (if possible). |
| left    | Insert page breaks so that the next page is formatted as a left page. |
| right   | Insert page breaks so that the next page is formatted as a right page. |
| initial | Sets this property to its default value. |
| inherit | Inherits this property from its parent element. |
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch45-1">Section 45.1: Media print page-break</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b>&commat;media</b> print {
  p {
    <b>page-break-inside</b>: avoid;
  }
  h1 {
    <b>page-break-before</b>: always;
  }
  h2 {
    <b>page-break-after</b>: avoid;
  }
}</code></pre>

<p>This code does 3 things:</p>

<ul>
  <li>it prevents a page break inside any p tags, meaning a paragraph will never 
    be broken in two pages, if possible.</li>
  <li>it forces a page-break-before in all h1 headings, meaning that before every 
    h1 occurrence, there will be a page break.</li>
  <li>it prevents page-breaks right after any h2.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch46">Chapter 46: CSS Object Model (CSSOM)</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch46-1">Section 46.1: Adding a background-image rule via the CSSOM</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To add a background-image rule via the CSSOM, first get a reference to the 
rules of the first stylesheet:</p>

<pre><code>var stylesheet = document.styleSheets&lbrack;0&rbrack;.cssRules;</code></pre>

<p>Then, get a reference to the end of the stylesheet:</p>

<pre><code>var end = stylesheet.length &minus; 1;</code></pre>

<p>Finally, insert a background-image rule for the body element at the end of 
the stylesheet:</p>

<pre><code>stylesheet.insertRule(&quot;body { background-image:
url(&apos;http://cdn.sstatic.net/Sites/stackoverflow/img/favicon.ico&apos;);}&quot;, end);</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch46-2">Section 46.2: Introduction</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The browser identifies tokens from stylesheet and coverts them into
> nodes which are linked into a tree structure. The entire map of all
> the nodes with their associated styles of a page would be the CSS
> Object Model.
>
> To display the webpage, a web browser takes following steps.

1.  The web browser examines your HTML and builds the DOM (Document
    Object Model).

2.  The web browser examines your CSS and builds the CSSOM (CSS Object
    Model).

3.  The web browser combines the DOM and the CSSOM to create a render
    tree. The web browser displays your webpage.

[image259.jpg 7.5 x 3](./images/image259.jpg)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch47">Chapter 47: Feature Queries</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>Parameter Details</b>

  property                              :    value

> Evaluates true if the browser can handle the CSS rule. The parenthesis
> around the rule are
>
> ()
>
> required.
>
> and Returns true only if both the previous and next conditions are
> true. not Negates the next condition or Returns true if either the
> previous or next condition is true.

  &period;..


() Groups conditions

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch47-1">Section 47.1: Basic &commat;supports usage</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>&commat;supports</b>

(

<b>display</b>

:

flex

)

{

/* Flexbox is available, so use it */

.my-container

{

<b>display</b>

:

flex

;

}

}

> In terms of syntax, &commat;supports is very similar to &commat;media, but instead
> of detecting screen size and orientation, &commat;supports will detect
> whether the browser can handle a given CSS rule.

  <b>&commat;supports</b>   (   flex   ), notice that the rule  <b>&commat;supports</b>   (   <b>display</b>   :   flex
                              is                                                              


Rather than doing something like ).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch47-2">Section 47.2: Chaining feature detections</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> To detect multiple features at once, use the and operator.

<b>&commat;supports</b>

(

<b>transform</b>

:

translateZ

(

1

px

)

)

and

(

<b>transform-style</b>

:

preserve-3d

)

and

(

<b>perspective</b>

:

1

px

)

{

/* Probably do some fancy 3d stuff here */

}

There is also an

or

operator and a

not

operator:

<b>&commat;supports</b>

(

<b>display</b>

:

flex

)

or

(

<b>display</b>

:

table-cell

)

{

/* Will be used if the browser supports flexbox or display: table-cell
*/

}

<b>&commat;supports</b>

not

(

webkit-transform

&minus;

:

translate

(

0

,

0

,

0

)

)

{

/* Will &ast;not&ast; be used if the browser supports -webkit-transform:
translate(&period;..) */

}

> For the ultimate &commat;supports experience, try grouping logical
> expressions with parenthesis:

<b>&commat;supports</b>

(

(

<b>display</b>

:

block

)

and

(

zoom

:

1

)

)

or

(

(

<b>display</b>

:

flex

)

and

(

not

(

<b>display</b>

:

table-cell

)

)

)

or

(

<b>transform</b>

:

translateX

(

1

px

)

)

{

/* &period;.. */

}

> This will work if the browser

  <b>display</b>           :   block              AND             zoom


1.  Supports : 1, or

  <b>display</b>   :   flex     AND NOT         <b>display</b>   :   table-cell


2.  Supports , or

  <b>transform</b>             :   translateX                      (   1px


3.  Supports ).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch48">Chapter 48: Stacking Context</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch48-1">Section 48.1: Stacking Context</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> In this example every positioned element creates its own stacking
> context, because of their positioning and z-index values. The
> hierarchy of stacking contexts is organized as follows:

Root

DIV #1

DIV #2

DIV #3

DIV #4

DIV #5

DIV #6

<p>It is important to note that DIV #4, DIV #5 and DIV #6 are children of
DIV #3, so stacking of those elements is completely resolved within
DIV#3. Once stacking and rendering within DIV #3 is completed, the
whole DIV #3 element is passed for stacking in the root element with
respect to its sibling&apos;s DIV.</p>

<h4>HTML:</h4>

<pre><code>
<b>&lt;div</b> id=&quot;div1&quot;<b>&gt;</b>
<b>&lt;h1&gt;</b>
Division Element #1
<b>&lt;/h1&gt;</b>
<b>&lt;code&gt;</b>
position: relative;
<b>&lt;</b><b>br</b><b>/&gt;</b>
z-index: 5;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;div2&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
<b>&gt;</b>
Division Element #2
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
position: relative;
<b>&lt;</b>
<b>br</b>
<b>/&gt;</b>
z-index: 2;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;div3&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;div4&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
<b>&gt;</b>
Division Element #4
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
position: relative;
<b>&lt;</b>
<b>br</b>
<b>/&gt;</b>
z-index: 6;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
<b>&gt;</b>
Division Element #3
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
position: absolute;
<b>&lt;</b>
<b>br</b>
<b>/&gt;</b>
z-index: 4;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;div5&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
<b>&gt;</b>
Division Element #5
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
position: relative;
<b>&lt;</b>
<b>br</b>
<b>/&gt;</b>
z-index: 1;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;div6&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>1</b>
<b>&gt;</b>
Division Element #6
<b>&lt;</b>
<b>/h</b>
<b>1</b>
<b>&gt;</b>
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
position: absolute;
<b>&lt;</b>
<b>br</b>
<b>/&gt;</b>
z-index: 3;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
> <b>CSS:</b>
#div5
{
<b>border</b>
:
1
px
dashed
#996
;
<b>background-color</b>
:
#ffc
;
}
#div4
{
<b>z-index</b>
:
6
;
<b>margin-bottom</b>
:
15
px
;
<b>padding</b>
:
25
px
10
px
5
px
;
}
#div5
{
<b>z-index</b>
:
1
;
<b>margin-top</b>
:
15
px
;
<b>padding</b>
:
5
px
10
px
;
}
#div6
{
<b>z-index</b>
:
3
;
<b>position</b>
:
absolute
;
<b>top</b>
:
20
px
;
<b>left</b>
:
180
px
;
<b>width</b>
:
150
px
;
<b>height</b>
:
125
px
;
<b>border</b>
:
1
px
dashed
#009
;
<b>padding-top</b>
:
125
px
;
<b>background-color</b>
:
#ddf
;
<b>text-align</b>
:
center
;
}
</code></pre>

<h4>Result:</h4>

[image260.jpg 6x3 inc](./images/image260.jpg)

> Source:

;;https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch49">Chapter 49: Block Formatting Contexts</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch49-1">Section 49.1: Using the overflow property with a value dierent to visible</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

img

{

<b>float</b>

:

left

;

<b>width</b>

:

100

px

;

<b>margin</b>

:

0

10

px

;

}

.div1

{

<b>background</b>

:

#f1f1f1

;

/* does not create block formatting context */

}

.div2

{

<b>background</b>

:

#f1f1f1

;

<b>overflow</b>

:

hidden

;

/* creates block formatting context */

}
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 261.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image261.jpg"
  style="width:60%"
  title=""
  alt="." />
</p>
<!-- [image261.jpg 6 x 3](./images/image261.jpg) -->

<a href="https://jsfiddle.net/MadalinaTn/qkwwmu6m/2/&rbrack;&rbrack;(https://jsfiddle.net/MadalinaTn/qkwwmu6m/2/">jsFiddle Demo</a>.

> Using the overflow property with a value different to visible (its
> default) will create a new block formatting&rbrack; &lbrack;context.
> This is technically necessary&rbrack; &lbrack;---&rbrack; &lbrack;if a
> float intersected with the scrolling element it would
> forcibly&rbrack; &lbrack;rewrap the
> content.&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/)
>
> This example that show how a number of paragraphs will interact with a
> floated image is similar to &lbrack;&lbrack;this
> example&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/),
> on css-tricks.com.

&lbrack;&lbrack;2&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/):
&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/overflow&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
MDN

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch50">Chapter 50: Vertical Centering</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-1">Section 50.1: Centering with display: table</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;wrapper&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;outer&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;inner&quot;

<b>&gt;</b>

centered

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.wrapper

{

<b>height</b>

:

600

px

;

<b>text-align</b>

:

center

;

}

.outer

{

<b>display</b>

:

table

;

<b>height</b>

:

100

&percnt;

;

<b>width</b>

:

100

&percnt;

;

}

.outer

.inner

{

<b>display</b>

:

table-cell

;

<b>text-align</b>

:

center

;

<b>vertical-align</b>

:

middle

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-2">Section 50.2: Centering with Flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;container&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;child&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.container

{

<b>height</b>

:

500

px

;

<b>width</b>

:

500

px

;

<b>display</b>

:

flex

;

// Use Flexbox

<b>align-items</b>

:

center

;

// This centers children vertically in the parent.

<b>justify-content</b>

:

center

;

// This centers children horizontally.

<b>background</b>

:

white

;

}

.child

{

<b>width</b>

:

100

px

;

<b>height</b>

:

100

px

;

<b>background</b>

:

blue

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-3">Section 50.3: Centering with Transform</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;wrapper&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;centered&quot;

<b>&gt;</b>

centered

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.wrapper

{

<b>position</b>

:

relative

;

<b>height</b>

:

600

px

;

}

.centered

{

<b>position</b>

:

absolute

;

<b>z-index</b>

:

999

;

<b>transform</b>

:

translate

(

-50

&percnt;

,

-50

&percnt;

)

;

<b>top</b>

:

50

&percnt;

;

<b>left</b>

:

50

&percnt;

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-4">Section 50.4: Centering Text with Line Height</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;container&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>span</b>

<b>&gt;</b>

vertically centered

<b>&lt;</b>

<b>/span</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.container

{

<b>height</b>

:

50

px

;

/* set height */

<b>line-height</b>

:

50

px

;

/* set line-height equal to the height */

<b>vertical-align</b>

:

middle

;

/* works without this rule, but it is good having it explicitly set
*/

}

> <b>Note:</b> This method will only vertically center a *single line of
> text*. It will not center block elements correctly and if the text
> breaks onto a new line, you will have two very tall lines of text.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-5">Section 50.5: Centering with Position: absolute</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <b>HTML:</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;wrapper&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>img</b>

src

=

&quot;http://cdn.sstatic.net/Sites/stackoverflow/company/img/logos/so/so-icon.png?v=c78bd457575a&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.wrapper

{

<b>position</b>

:

relative

;

<b>height</b>

:

600

px

;

}

.wrapper

img

{

<b>position</b>

:

absolute

;

<b>top</b>

:

0

;

<b>left</b>

:

0

;

<b>right</b>

:

0

;

<b>bottom</b>

:

0

;

<b>margin</b>

:

auto

;

}

> If you want to center other then images, then you must give height and
> width to that element.
>
> <b>HTML:</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;wrapper&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;child&quot;

<b>&gt;</b>

make me center

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.wrapper

{

<b>position</b>

:

relative

;

<b>height</b>

:

600

px

;

}

.wrapper

.child

{

<b>position</b>

:

absolute

;

<b>top</b>

:

0

;

<b>left</b>

:

0

;

<b>right</b>

:

0

;

<b>bottom</b>

:

0

;

<b>margin</b>

:

auto

;

<b>width</b>

:

200

px

;

<b>height</b>

:

30

px

;

<b>border</b>

:

1

px

solid

#f00

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch50-6">Section 50.6: Centering with pseudo element</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;wrapper&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;content&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <b>CSS:</b>

.wrapper

{

<b>min-height</b>

:

600

px

;

}

.wrapper

:

before

{

<b>content</b>

:

&quot;&quot;

;

<b>display</b>

:

inline-block

;

<b>height</b>

:

100

&percnt;

;

<b>vertical-align</b>

:

middle

;

}

.content

{

<b>display</b>

:

inline-block

;

<b>height</b>

:

80

px

;

<b>vertical-align</b>

:

middle

;

}

> This method is best used in cases where you have a varied-height
> .content centered inside .wrapper; and you want .wrapper&apos;s height to
> expand when .content&apos;s height exceed .wrapper&apos;s min-height.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch51">Chapter 51: Object Fit and Placement</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch51-1">Section 51.1: object-fit</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <b>object-fit</b> property will defines how an element will fit into
a box with an established height and width. Usually applied to an
image or video, Object-fit accepts the following five values:</p>

<b>FILL</b>

<pre><code><b>object-fit</b>: fill;</code></pre>

<p>Fill stretches the image to fit the content box without regard to the
image&apos;s original aspect ratio.</p>

<pre><code><b>CONTAIN object-fit</b>:contain;</code></pre>

<p>Contain fits the image in the box&apos;s height or width while maintaining
the image&apos;s aspect ratio.</p>

<pre><code><b>COVER object-fit</b>:cover;</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 264.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image264.jpg"
  style="width:60%"
  title=""
  alt="." />
</p>
<!-- [image264.jpg 6.2 x 2.8](./images/image264.jpg) -->

> Cover fills the entire box with the image. The image aspect ratio is
> preserved, but the image is cropped to the dimensions of the box.
>
> <b>NONE</b>

<b>object-fit</b>

:

none

;

> None ignores the size of the box and is not resized.
>
> <b>SCALE-DOWN</b>

<b>object-fit</b>

:

scale-down

;

> Scale-down either sizes the object as none or as contain. It displays
> whichever option results in a smaller image size.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 266.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image266.jpg"
  style="width:70%"
  title=""
  alt="." />
</p>
<!-- [image266.jpg 7.2 x 3.65](./images/image266.jpg) -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch52">Chapter 52: CSS design patterns</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> These examples are for documenting CSS-specific design patterns like
> &lbrack;&lbrack;BEM&rbrack;&rbrack;(http://getbem.com/),
> &lbrack;&lbrack;OOCSS&rbrack;&rbrack;(https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)
> and &lbrack;&lbrack;SMACSS&rbrack;&rbrack;(https://smacss.com/).
>
> These examples are NOT for documenting CSS frameworks like
> &lbrack;&lbrack;Bootstrap&rbrack;&rbrack;(http://getbootstrap.com/) or
> &lbrack;&lbrack;Foundation&rbrack;&rbrack;(http://foundation.zurb.com/).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch52-1">Section 52.1: BEM</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  Blocks         ,   Elements and Modifiers

> &lbrack;&lbrack;BEM&rbrack;&rbrack;(http://getbem.com/introduction/) stands for .
> It&apos;s a methodology initially conceived by Russian tech company
>
> &lbrack;&lbrack;Yandex&rbrack;&rbrack;(https://en.wikipedia.org/wiki/Yandex), but
> which gained quite some traction among American & Western-European web
> developers as well.
>
> As the same implies, BEM metholology is all about componentization of
> your HTML and CSS code into three types of components:
>
> <b>Blocks:</b> standalone entities that are meaningful on their own
>
> Examples are header, container, menu, checkbox & textbox
>
> <b>Elements:</b> Part of blocks that have no standalone meaning and are
> semantically tied to their blocks.

  menu item         , list item,          checkbox caption

> Examples are & header title
>
> <b>Modifiers:</b> Flags on a block or element, used to change appearance
> or behavior

  color yellow

> Examples are disabled, highlighted, checked, fixed, size big &
>
> The goal of BEM is to keep optimize the readability, maintainability
> and flexibility of your CSS code. The way to achieve this, is to apply
> the following rules.

  blockname&minus;-modifiername        and   blockname&lowbar;&lowbar;elementname&minus;-

> Block styles are never dependent on other elements on a page
>
> Blocks should have a simple, short name and avoid &lowbar; or - characters
>
> When styling elements, use selectors of format
> blockname&lowbar;&lowbar;elementname When styling modifiers, use selectors of
> format modifiername
>
> Elements or blocks that have modifiers should inherit everything from
> the block or element it is modifying except the properties the
> modifier is supposed to modify
>
> <b>Code example</b>
>
> If you apply BEM to your form elements, your CSS selectors should look
> something like this:
>
> .form { } // Block
>
> .form&minus;-theme-xmas { } // Block + modifier .form&minus;-simple { } //
> Block + modifier
>
> .form&lowbar;&lowbar;input { } // Block &gt; element
>
> .form&lowbar;&lowbar;submit { } // Block &gt; element
>
> .form&lowbar;&lowbar;submit&minus;-disabled { } // Block &gt; element + modifier
>
> The corresponding HTML should look something like this:

<b>&lt;</b>

<b>form</b>

class

=

&quot;form form&minus;-theme-xmas form&minus;-simple&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>input</b>

class

=

&quot;form&lowbar;&lowbar;input&quot;

type

=

&quot;text&quot;

<b>/&gt;</b>

<b>&lt;</b>

<b>input</b>

class

=

&quot;form&lowbar;&lowbar;submit form&lowbar;&lowbar;submit&minus;-disabled&quot;

type

=

&quot;submit&quot;

<b>/&gt;</b>

<b>&lt;</b>

<b>/form</b>

<b>&gt;</b>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch53">Chapter 53: Browser Support & Prefixes</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<b>Prefix Browser(s)</b>

> -webkit- Google Chrome, Safari, newer versions of Opera 12 and up,
> Android, Blackberry and UC browsers -moz- Mozilla Firefox

-ms- Internet Explorer, Edge

> Opera until version 12
>
> -khtml- Konquerer
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch53-1">Section 53.1: Transitions</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

div

{

-webkit-transition

:

all

4

s

ease

;

-moz-transition

:

all

4

s

ease

;

-o-transition

:

all

4

s

ease

;

<b>transition</b>

:

all

4

s

ease

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch53-2">Section 53.2: Transform</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

div

{

-webkit-transform

:

rotate

(

45

deg

)

;

-moz-transform

:

rotate

(

45

deg

)

;

-ms-transform

:

rotate

(

45

deg

)

;

-o-transform

:

rotate

(

45

deg

)

;

<b>transform</b>

:

rotate

(

45

deg

)

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch54">Chapter 54: Normalizing Browser Styles</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Every browser has a default set of CSS styles that it uses for
> rendering elements. These default styles may not be consistent across
> browsers because: the language specifications are unclear so base
> styles are up for interpretation, browsers may not follow
> specifications that are given, or browsers may not have default styles
> for newer HTML elements. As a result, people may want to normalize
> default styles across as many browsers as possible.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch54-1">Section 54.1: normalize.css</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Browsers have a default set of CSS styles they use for rendering
> elements. Some of these styles can even be customised using the
> browser&apos;s settings to change default font face and size definitions,
> for example. The styles contain the definition of which elements are
> supposed to be block-level or inline, among other things.
>
> Because these default styles are given some leeway by the language
> specifications and because browsers may not follow the specs properly
> they can differ from browser to browser.
>
> This is where
> &lbrack;&lbrack;normalize.css&rbrack;&rbrack;(http://necolas.github.io/normalize.css/)
> comes into play. It overrides the most common inconsistencies and
> fixes known bugs.
>
> <b>What does it do</b>
>
> Preserves useful defaults, unlike many CSS resets.
>
> Normalizes styles for a wide range of elements.
>
> Corrects bugs and common browser inconsistencies.
>
> Improves usability with subtle modifications.
>
> Explains what code does using detailed comments.
>
> So, by including normalize.css in your project your design will look
> more alike and consistent across different browsers.
>
> <b>Difference to reset.css</b>
>
> You may have heard of reset.css. What&apos;s the difference between the
> two?
>
> While normalize.css provides consistency by setting different
> properties to unified defaults, reset.css achieves consistency by
> <b>removing</b> all basic styling that a browser may apply. While this
> might sound like a good idea at first, this actually means you have to
> write <b>all</b> rules yourself, which goes against having a solid
> standard.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch54-2">Section 54.2: Approaches and Examples</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> CSS resets take separate approaches to browser defaults. Eric Meyer's
> Reset CSS has been around for a while. His approach nullifies many of
> the browser elements that have been known to cause problems right off
> the back. The following is from his version (v2.0 &vert; 20110126) CSS
> Reset.

html, body, div, span, applet, object, iframe,

h1, h2, h3, h4, h5, h6,

<b>p</b>

, blockquote, pre,

a, abbr, acronym, address, big, cite, code,

del, dfn, em, img, ins, kbd, q, s, samp,

small, strike, strong,

<b>sub</b>

, sup, tt, var,

b, u, i, center,

dl, dt, dd, ol, ul, li,

fieldset, form, label, legend,

table, caption, tbody, tfoot, thead, tr, th, td,

article, aside, canvas, details, embed,

figure, figcaption, footer, header, hgroup,

menu, nav, output, ruby, section, summary,

time, mark, audio, video

<b>{</b>

margin:

0

;

padding:

0

;

border:

0

;

font

<b>-</b>

size:

100

<b>%</b>

;

font: inherit;

vertical

<b>-</b>

align: baseline;

<b>}</b>

&lbrack;&lbrack;Eric Meyer&apos;s Reset
CSS&rbrack;&rbrack;(http://meyerweb.com/eric/tools/css/reset/)

> Normalize CSS on the other and deals with many of these separately.
> The following is a sample from the version (v4.2.0) of the code.

/**/

*&ast; 1. Change the default font family in all browsers (opinionated).*

*&ast; 2. Correct the line height in all browsers.*

*&ast; 3. Prevent adjustments of font size after orientation changes in IE
and iOS.*

**/

/* Document*

*==========================================================================
*/

html

{

<b>font-family</b>

:

sans-serif

;

/* 1 */

<b>line-height</b>

:

1.15

;

/* 2 */

-ms-text-size-adjust

:

100

&percnt;

;

/* 3 */

-webkit-text-size-adjust

:

100

&percnt;

;

/* 3 */

}

/* Sections*

*==========================================================================
*/

/**/

*&ast; Remove the margin in all browsers (opinionated).*

**/

body

{

<b>margin</b>

:

0

;

}

**/

/* Add the correct display in IE 9-.

*/

article

,

aside

,

footer

,

header

,

nav

,

section

{

<b>display</b>

:

block

;

}

/**
  Correct the font size and margin on &apos;h1&apos; elements within &apos;section&apos; and
  &apos;article&apos; contexts in Chrome, Firefox, and Safari.
**/

h1

{

<b>font-size</b>

:

2

em

;

<b>margin</b>

:

0.67

em

0

;

}

<a href="http://normalize.css/">Normalize CSS</a>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch55">Chapter 55: Internet Explorer Hacks</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch55-1">Section 55.1: Adding Inline Block support to IE6 and IE7</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<b>display</b>

:

inline-block

;

> The display property with the value of inline-block is not supported
> by Internet Explorer 6 and 7. A work-around for this is:

zoom

:

1

;

&ast;

<b>display</b>

:

inline

;

  display


> The zoom property triggers the hasLayout feature of elements, and it
> is available only in Internet Explorer. The &ast; makes sure that the
> invalid property executes only on the affected browsers. Other
> browsers will simply ignore the rule.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch55-2">Section 55.2: High Contrast Mode in Internet Explorer 10 and greater</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> In Internet Explorer 10+ and Edge, Microsoft provides the
> -ms-high-contrast media selector to expose the &quot;High Contrast&quot;
> setting from the browser, which allows the programmer to adjust their
> site&apos;s styles accordingly.
>
> The -ms-high-contrast selector has 3 states: active, black-on-white,
> and white-on-black. In IE10+ it also had a none state, but that is no
> longer supported in Edge going forward.
>
> <b>Examples</b>

<b>&commat;media</b>

screen and

(

&minus;

ms-high-contrast

:

active

)

,

(

&minus;

ms-high-contrast

:

black-on-white

)

{

.header

{

<b>background</b>

:

#fff

;

<b>color</b>

:

#000

;

}

}

> This will change the header background to white and the text color to
> black when high contrast mode is active *and* it is in black-on-white
> mode.

<b>&commat;media</b>

screen and

(

&minus;

ms-high-contrast

:

white-on-black

)

{

.header

{

<b>background</b>

:

#000

;

<b>color</b>

:

#fff

;

}

}

> Similar to the first example, but this specifically selects the
> white-on-black state only, and inverts the header colors to a black
> background with white text.
>
> <b>More Information:</b>

<a href="https://msdn.microsoft.com/en-us/library/windows/apps/hh465764.aspx">Microsoft Documentation</a>
on -ms-high-contrast

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch55-3">Section 55.3: Internet Explorer 6 & Internet Explorer 7 only</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> To target Internet Explorer 6 and Internet Explorer 7, start your
> properties with &ast;:

<pre><code>
.hide-on-ie6-and-ie7 {
&ast;
<b>display</b>: none;
// This line is processed only on IE6 and IE7
}
</code></pre>

> To target Internet Explorer 8, wrap your selectors inside :

<pre><code>
<b>&commat;media</b>
&bsol;&bsol; 0
screen {
  .hide-on-ie8 {
    <b>display</b>: none;
  }
}
</code></pre>

| <b>&commat;media</b> &bsol;&bsol;0             | screen { }                           |

> Everything between is processed only by I

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch56">Chapter 56: Performance</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch56-1">Section 56.1: Use transform and opacity to avoid trigger layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Changing some CSS attribute will trigger the browser to synchronously
calculate the style and layout, which is a bad thing when you need to
animate at 60fps.

<b>DON&apos;T</b>

Animate with left and top trigger layout.

<pre><code>
#box {
  <b>left</b>: 0;
  <b>top</b>: 0;
  <b>transition</b>: left 0.5s, top 0.5s;
  <b>position</b>: absolute;
  <b>width</b>: 50px;
  <b>height</b>: 50px;
  <b>background-color</b>: gray;
}
#box.active {
  <b>left</b>: 100px;
  <b>top</b>: 100px;
}
</code></pre>

<a href="https://jsfiddle.net/trungdq88/gmpzxLyq/">Demo</a>
took 11.7ms for rendering 9.8ms
for painting
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 267.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image267.jpg"
  style="width:75%"
  title=""
  alt="." />
</p>
<!-- [image267.jpg 7.5 x 7.5](./images/image267.jpg) -->

> <b>DO</b>

Animate with transform with the same animation.

<pre><code>#box {
  <b>left</b>: 0;
  <b>top</b>: 0;
  <b>position</b>: absolute;
  <b>width</b>: 50px;
  <b>height</b>: 50px;
  <b>background-color</b>: gray;
  <b>transition</b>: transform 0.5s;
  <b>transform</b>: translate3d(0, 0, 0);
}

#box.active {
  <b>transform</b>: translate3d(100px, 100px, 0);
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 268.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="left" width="100%">
<img src="./images/image268.jpg"
  style="width:50%"
  title=""
  alt="." />
</p>

<p><a href="https://jsfiddle.net/trungdq88/Logdo0rn/">Demo (jsFiddle)</a>
same animation, took <b>1.3ms</b> for rendering, <b>2.0ms</b> for painting.</p>

<!-- [imge268.jpg](./images/image268.jpg) -->
<!-- width 6.2" -->

<!-- the end -->
<!-- 6/28/2024 Fri 5:41pm -->
<!-- 7/1/2024 Mon 2:24am -->
<!-- 7/2/2024 Tue 6:39pm -->
<!-- 7/4/2024 Thu 1:35am -->
<!-- 7/5/2024 Fri 8:48pm -->
<!-- 7/6/2024 Sat 3:21am -->
