ruta_proyecto: /web/_project.yaml ruta_libro: /web/resources/_book.yaml descripción: Esta es la descripción de la página colocada en el encabezado.

{# wf_updated_on: 2017-09-20 #} {# wf_published_on: 2016-09-13 #}

# Sintaxis de Markdown {: .page-title}

{% include "web / _shared / contributors / petelepage.html"%}

Web **Fundamental** proporciona una amplia variedad de elementos con estilo y clases CSS para usar en la documentación. Aunque puede complementar estos estilos con CSS personalizado, solo debe usar CSS personalizado cuando sea estrictamente necesario. Si encuentra que necesita crear un nuevo estilo que se aplicará a más de una página, presente un problema en GitHub para que otras páginas también puedan usarlo. Esto asegura la consistencia en todo el sitio.

Nota: Este documento está destinado a complementar la [guía de estilo de documentación para desarrolladores de Google](/style/) . Si hay diferencias, la guía de estilo oficial tiene prioridad a menos que se especifique lo contrario.

## Encabezados

El encabezado superior de la página es el título de la página. El cuerpo de la página no debe contener otro encabezado de nivel 1, para evitar confusos navegadores no visuales.

**¿Cuándo debo capitalizar los encabezados?**

Use [sentence case](/style/capitalization#capitalization-in-titles-and-headings), for **all** titles, and section headings.

Sí, somos inconsistentes con esto, pero estamos tratando de solucionarlo, por favor, haga todo lo posible para cumplir con estas pautas.

## Título 2 {: # título-qué-qué}

Precaución: Si planea vincular encabezados específicos [&lt; `a href="#heading-what-what"` &gt;](#heading-what-what) dentro de su documento, se recomienda **encarecidamente** que los defina usted mismo con la sintaxis `{: #anchor-name }` . Esto asegura que cuando los documentos estén localizados, el ancla seguirá funcionando, pero también asegura que cualquier diferencia entre los procesadores Markdown no sea un problema.

### Título 3

DevSite agregará automáticamente elementos `<h2>` y `<h3>` a la tabla de contenido. Para evitar que se agregue uno (como estos dos aquí, que no aparecen en la tabla de contenido), aplique `class="hide-from-toc"` . También puede poner un `<h2>` o `<h3>` dentro de un encabezado de tabla ( `<th>` ) para forzar la tabla dentro de la tabla de contenido. Dentro del encabezado de una tabla, `<h2>` y `<h3>` tienen el estilo de un texto normal, por lo que los lectores no podrán saberlo.

#### Título 4

##### Título 5

###### Título 6

```
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

## Código de muestra

Si su contribución contiene código, asegúrese de que siga la [guía de estilo de codificación de Google para JavaScript](https://google.github.io/styleguide/javascriptguide.xml) . De lo contrario, tendremos que pedirle que realice cambios, y eso no es divertido para nadie.

### Código en línea

Para indicar un intervalo de código, envuélvalo con comillas de retroceso (`). A diferencia de un bloque de código preformateado, un intervalo de código indica código dentro de un párrafo normal. Por ejemplo:

```
Use the `printf()` function.
```

Resultará en:

Use la `printf()` .

### Bloques de código

Para producir un bloque de código en Markdown, simplemente sangra cada línea del bloque por al menos 4 espacios o 1 pestaña. Por ejemplo, dada esta entrada:

```
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```

resultará en:

Aquí hay un ejemplo de AppleScript:

```
tell application "Foo"
    beep
end tell
```

Dentro de un bloque de código, los símbolos ( `&` ) y los corchetes angulares ( `<` y `>` ) se convierten automáticamente en entidades HTML. Esto hace que sea muy fácil incluir un código fuente HTML de ejemplo usando Markdown: simplemente péguelo e indentifíquelo, y Markdown se encargará de la molestia de codificar los signos y los corchetes angulares.

Advertencia: DevSite no admite envolver bloques de código en `&<>` . DevSite no diseñará automáticamente estos bloques y nuestras pruebas de integración fallarán.

### Destacando

Use `<strong>` para llamar la atención sobre el contenido dentro de un bloque `<pre>` . Al hacerlo, se aclarará el contenido circundante para enfatizar la sección resaltada por el bloque `<strong>` . Por ejemplo:

<pre class="prettyprint">// ... // ... // ... for (i = 0; i &lt; 10; i ++) {printf ("Contando% d \ n", i); <strong>if (i% 3 == 0) {someFunc (i); }</strong> } // ... // ... // ...</pre>

```
&lt;pre class="prettyprint"&gt;
// ...
// ...
// ...
for (i = 0; i &lt; 10; i++) {
    printf("Counting %d\n", i);

    &lt;strong&gt;if (i % 3 == 0) {
        someFunc(i);
    }&lt;/strong&gt;
}
// ...
// ...
// ...
&lt;/pre&gt;
```

### Haga clic para copiar

Haga clic para copiar se habilita automáticamente para todos los bloques de código.

### Caso especial: Plantillas - &#123; &#123;}}

Si necesita incluir plantillas en sus ejemplos de código, asegúrese de escapar de ellas.

Por ejemplo:

<pre class="prettyprint">&lt; pre class = "prettyprint" &gt; &lt; polímero-media-query query = "max-width: 640px" queryMatches = "&amp;#123; {isPhone}}" &gt; &lt; / pre {gt }</pre>

Si está en línea, deberá envolverlo en un bloque `<code>` lugar de backticks.

<pre class="prettyprint">* Enlace de datos bidireccional declarativo: &lt; código &gt; &lt; input id = "input" value = "&amp;#123; {foo}}" &gt; &lt; / code &gt;</pre>

## Imágenes

Al agregar un subtítulo, ajuste las imágenes en bloques `<figure>` e, idealmente, use imágenes receptivas con el atributo `scrset` cuando sea posible. Asegúrese de incluir también atributos `alt` para sus imágenes.

<figure><img src="https://placehold.it/350x150" alt="Imagen de muestra"><figcaption> Este título debe usarse para describir la imagen. </figcaption></figure>

Por ejemplo:

```
&lt;figure&gt;
  &lt;img src="https://placehold.it/350x150" alt="sample image"&gt;
  &lt;figcaption&gt;This caption should be used to describe the image.&lt;/figcaption&gt;
&lt;/figure&gt;
```

Note: Optimized images are served automatically only for `index.yaml` pages, simply provide a 2x version, and the server will do the rest.

Puede aplicar `class="screenshot"` a una imagen para darle un borde que la desplace del texto cercano. Esto normalmente se usa para capturas de pantalla que tienen fondos blancos y que de otra manera se pierden en la página. No lo use para imágenes que no lo necesitan.

### Imágenes flotantes a la derecha

<div class="attempt-right">
  <figure><img src="https://placehold.it/350x150" alt="Diálogo de alerta"><figcaption> <b>Figura 1</b> : cuadro de diálogo de alerta </figcaption></figure>
</div>

La imagen de la derecha también tiene `class="attempt-right"` , que flota la imagen a la derecha en pantallas más grandes, pero fuerza la imagen en un diseño vertical en pantallas más pequeñas, tabletas y más pequeñas, donde flotar a la derecha podría causar problemas. También está disponible `class="attempt-left"` . Para usar `attempt-left` e `attempt-right` juntos, asegúrese de que el elemento `attempt-left` sea lo primero.

<div class="clearfix"></div>

```
&lt;div class="attempt-right"&gt;
  &lt;figure&gt;
    &lt;img src="https://placehold.it/350x150" alt="Alert dialog"&gt;
    &lt;figcaption&gt;&lt;b&gt;Figure 1&lt;/b&gt;: Alert dialog&lt;/figcaption&gt;
  &lt;/figure&gt;
&lt;/div&gt;
```

Precaución: cuando se utiliza el `attempt-left` e `attempt-right` , puede ser necesario incluir un bloque `<div class="clearfix"></div>` .

### Hacer y no hacer imágenes

Agregue la clase de `success` o `warning` al pie de figura para indicar un buen o mal ejemplo.

<div class="attempt-left">
  <figure><img src="https://placehold.it/350x150" alt="Diálogo de alerta"><figcaption class="success"> <b>DO</b> : Esto es lo correcto </figcaption></figure>
</div>
<div class="attempt-right">
  <figure><img src="https://placehold.it/350x150" alt="Diálogo de alerta"><figcaption class="warning"> <b>NO</b> : Esto es lo incorrecto que hacer </figcaption></figure>
</div>

<div class="clearfix"></div>

```
&lt;div class="attempt-left"&gt;
  &lt;figure&gt;
    &lt;img src="https://placehold.it/350x150" alt="Alert dialog"&gt;
    &lt;figcaption class="success"&gt;
      &lt;b&gt;DO&lt;/b&gt;: This is the right thing to do
     &lt;/figcaption&gt;
  &lt;/figure&gt;
&lt;/div&gt;
&lt;div class="attempt-right"&gt;
  &lt;figure&gt;
    &lt;img src="https://placehold.it/350x150" alt="Alert dialog"&gt;
    &lt;figcaption class="warning"&gt;
      &lt;b&gt;DON'T&lt;/b&gt;: This is the wrong thing to do
     &lt;/figcaption&gt;
  &lt;/figure&gt;
&lt;/div&gt;
```

## Rótulos

Nota: este tipo de texto destacado es una nota o sugerencia ordinaria.

Precaución: este tipo de llamada sugiere proceder con precaución.

Advertencia: este tipo de llamada es más fuerte que una precaución; significa "No hagas esto".

Éxito: este tipo de llamada describe una acción exitosa o un estado libre de errores. Usado solo en contenido interactivo o dinámico; no lo use en páginas estáticas ordinarias.

Punto clave: este tipo de llamada define un concepto importante.

Término clave: este tipo de llamada define una terminología importante.

Objetivo: este tipo de llamada define el objetivo de un procedimiento.

Comida para perros: este tipo de texto es para notas que se aplican temporalmente durante las pruebas internas de comida para perros. Elimine todas las llamadas de Dogfood antes de hacer público un documento.

## Comparaciones

<p><span class="compare-worse">No recomendado</span> : sangría con pestañas</p>
<pre class="prettyprint">(código de muestra incorrecto)</pre>

<p><span class="compare-better">Recomendado</span> : sangría con espacios</p>
<pre class="prettyprint">(buen código de muestra)</pre>

<p><span class="compare-no">No permitido</span> - sangría con espacios</p>
<pre class="prettyprint">(código de muestra muy malo)</pre>

## Liza

### Desordenado

- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
- Lorem ipsum dolor sit amet, consectetur adipiscing elit.

### Ordenado

1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
3. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
4. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
5. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    3. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
6. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

## Mesas

Las tablas son compatibles con el marcado estándar. Aquí hay una tabla típica con una fila de encabezado, varias filas regulares y una fila marcada como `<tr class="alt">` , que produce un fondo más oscuro que puede usarse como un encabezado alternativo.

<table>
  <tr>
<th>Uno</th>
<th>Dos</th>
<th>Tres</th>
</tr>
  <tr>
<td>1.0</td>
<td>2,0</td>
<td>3.0</td>
</tr>
  <tr>
<td>1.1</td>
<td>2.1</td>
<td>3.1</td>
</tr>
  <tr class="alt"><td colspan="3">¡Aquí vienen algunos números que terminan en .2!</td></tr>
  <tr>
<td>1,2</td>
<td>2.2 2.2</td>
<td>3.2</td>
</tr>
</table>

```
&lt;table&gt;
  &lt;tr&gt;&lt;th&gt;One&lt;/th&gt;&lt;th&gt;Two&lt;/th&gt;&lt;th&gt;Three&lt;/th&gt;&lt;/tr&gt;
  &lt;tr&gt;&lt;td&gt;1.0&lt;/td&gt;&lt;td&gt;2.0&lt;/td&gt;&lt;td&gt;3.0&lt;/td&gt;&lt;/tr&gt;
  &lt;tr&gt;&lt;td&gt;1.1&lt;/td&gt;&lt;td&gt;2.1&lt;/td&gt;&lt;td&gt;3.1&lt;/td&gt;&lt;/tr&gt;
  &lt;tr class="alt"&gt;&lt;td colspan="3"&gt;Here come some numbers that end in .2!&lt;/td&gt;&lt;/tr&gt;
  &lt;tr&gt;&lt;td&gt;1.2&lt;/td&gt;&lt;td&gt;2.2&lt;/td&gt;&lt;td&gt;3.2&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;
```

### Tablas receptivas

Para que una tabla responda, agregue la clase `responsive` a la tabla.

<table class="responsive">
  <tbody>
    <tr>
      <th colspan="2">Parámetros</th>
    </tr>
    <tr>
      <td><code>value</code></td>
<td>
<code>String</code> <br> el valor de la opción, que los encuestados ven como una etiqueta cuando ven el formulario</td>
    </tr>
    <tr>
      <td><code>navigationType</code></td>
<td>
<code>&lt;a href="#"&gt;PageNavigationType&lt;/a&gt;</code> <br> el tipo de navegación de la elección</td>
    </tr>
  </tbody>
</table>

- Debe haber ***solo dos columnas*** en la tabla: la primera columna para las cosas que se están definiendo (la clave) y la segunda columna para toda la información sobre esa clave, en varias líneas si es necesario. Esta restricción de dos columnas significa que las tablas receptivas no se pueden usar para datos tabulares verdaderamente bidimensionales, comparación de características basada en marcas de verificación, pero son muy adecuadas para la información de referencia (o cualquier otro dato que pueda expresarse razonablemente por una lista de definiciones en lugar de una mesa).
- Si hay varias líneas de información sobre la clave, por ejemplo, un tipo y una descripción, ajuste cada línea en `<p>` para forzar los saltos de línea (en lugar de `<br>` ).
- Debe haber solo una celda en la fila del encabezado. Use `<th colspan="2">` para forzarlo a abarcar ambas columnas. Para recordarle este comportamiento, ocultamos automáticamente cualquier `<th>` después del primero (que intencionalmente parece muy roto).

<div class="clearfix"></div>

```
&lt;table class="responsive"&gt;
  &lt;tbody&gt;
    &lt;tr&gt;
      &lt;th colspan=2&gt;Parameters&lt;/th&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
      &lt;td&gt;
        &lt;code&gt;value&lt;/code&gt;
      &lt;/td&gt;
      &lt;td&gt;
        &lt;code&gt;String&lt;/code&gt;&lt;br&gt;
        the choice's value, which respondents see as a label when viewing the form
      &lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
      &lt;td&gt;
        &lt;code&gt;navigationType&lt;/code&gt;
      &lt;/td&gt;
      &lt;td&gt;
        &lt;code&gt;
          &lt;a href="#"&gt;PageNavigationType&lt;/a&gt;
        &lt;/code&gt;
        &lt;br&gt;the choice's navigation type
      &lt;/td&gt;
    &lt;/tr&gt;
  &lt;/tbody&gt;
&lt;/table&gt;
```

### Mesas invisibles

Puede organizar el texto en columnas, o hacer que una tabla sea invisible, utilizando `<table class="columns">...</table>` . Esto se usa típicamente para organizar listas largas y estrechas.

<table class="columns">
  <tr>
    <td>
      <code>auto</code><br>
      <code>descanso</code><br>
      <code>caso</code><br>
      <code>carbonizarse</code>
    </td>
    <td>
      <code>const</code><br>
      <code>Seguir</code><br>
      <code>defecto</code><br>
      <code>hacer</code>
    </td>
    <td>
      <code>doble</code><br>
      <code>más</code><br>
      <code>enumeración</code><br>
      <code>externo</code>
    </td>
  </tr>
</table>

```
&lt;table class="columns"&gt;
  &lt;tr&gt;
    &lt;td&gt;
      &lt;code&gt;auto&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;break&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;case&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;char&lt;/code&gt;
    &lt;/td&gt;
    &lt;td&gt;
      &lt;code&gt;const&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;continue&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;default&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;do&lt;/code&gt;
    &lt;/td&gt;
    &lt;td&gt;
      &lt;code&gt;double&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;else&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;enum&lt;/code&gt;&lt;br /&gt;
      &lt;code&gt;extern&lt;/code&gt;
    &lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;
```

## enlaces externos

Para marcar un enlace como externo, use `<a href="https://www.google.com/" class="external">External Link</a>` cuando cree en HTML, o agregue `{: .external}` a los enlaces al crear en Markdown.

<a href="https://www.google.com/" class="external">Enlace externo</a>

## Atributos personalizados y anclas con nombre

Markdown admite atributos de marcado personalizados para elementos y encabezados HTML a nivel de bloque.

El formato para esto permite una clase personalizada, una ID personalizada y / o pares de atributos / valores personalizados en la misma declaración:

```
This is a paragraph.
{: .customClass #custom_id attribute='value' }
```

Esto genera este HTML:

```
&lt;p class="customClass" id="custom_id" attribute="value"&gt;This is a paragraph.&lt;/p&gt;
```

### Atributos personalizados en encabezados

Como los encabezados solo se pueden definir en una línea, la lista de atributos se debe definir al final de la definición del encabezado:

```
## Header with custom ID {: #custom_id }
```

Genera:

```
&lt;h2 id="custom_id"&gt;Header with custom ID&lt;/h2&gt;
```

## Cotización de bloque

```
&gt; Lorem ipsum dolor sit amet, consectetur adipiscing elit.
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

## Información sobre herramientas

Cualquier elemento que tenga un atributo de `title` mostrará una información sobre herramientas (con el valor del atributo) al pasar el mouse. Por ejemplo: "... algún día el <abbr title="píxeles por pulgada">PPI de la</abbr> pantalla puede aumentar aún más ..." (tenga en cuenta que el subrayado punteado proviene del elemento abbr, no de la información sobre herramientas).

```
...someday screen &lt;abbr title="pixels per inch"&gt;PPI&lt;/abbr&gt; may increase further...
```

Advertencia: asegúrese de utilizar información sobre herramientas solo para obtener información complementaria, no texto esencial o características principales de la experiencia del usuario, ya que la presencia de información sobre herramientas no es obvia y los usuarios de dispositivos móviles no las verán en absoluto.

## Clases diversas

Use `class="inline"` , `class="inline-block"` y `class="block"` para forzar el diseño en línea, en línea o en bloque, en los casos excepcionales cuando sea necesario.

Use `class="clearfix"` para borrar un elemento flotante, por ejemplo, después de usar `attempt-left` o `attempt-right` .

## Comentarios

Un comentario de una línea y un comentario de varias líneas tienen una sintaxis diferente. Ambos se eliminan de las páginas web que se producen al organizar o publicar.

### Comentarios de una línea

Un comentario de una línea. Los caracteres hash (#) utilizados de esta manera están reservados solo para comentarios de una línea.

<pre class="prettyprint">&#123; # Viajar en el tiempo es divertido #}</pre>

### Comentarios multilínea

Un comentario de varias líneas, con etiquetas de inicio y fin que rodean el comentario.

<pre class="prettyprint">&#123;% comment%} Viajar en el tiempo es divertido. Lo hago literalmente todo el tiempo. &#123;% endcomment%}</pre>
