### Special Case: Templates -  &#123;&#123;}}

If you need to include templates in your code samples, be sure to escape them.

For example:
<pre class="prettyprint">
&lt;pre class="prettyprint">
&amp;lt;polymer-media-query query="max-width:640px" queryMatches="&amp;#123;{isPhone}}">
&lt;/pre>
</pre>

If it's inline, you'll need to wrap it in a `<code>` block instead of backticks.
<pre class="prettyprint">
* Declarative two-way data-binding: &lt;code>&lt;input id="input" value="&amp;#123;{foo}}">&lt;/code>
</pre>

## Images

When adding a caption, wrap images in `<figure>` blocks, and ideally, use
responsive images with the `scrset` attribute when possible. Be sure you
include `alt` attributes for your images as well.
