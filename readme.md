# HTML Formatting Guidelines

Have you ever worked on an HTML document with poor formatting and structure, but struggle to understand why it is hard to read and how to improve it? This guide will help serve as a baseline to create a readable, consistent document outline.


## Formatting Rules

### 1. Nest elements appropriately. Each element should be on a separate line, nested within its parent container and with appropriate indentation. You may add blank lines between groups of related content.

Correct:

```
<form>
  <div>
    <label>Email</label>
    <input type="text">

    <label>Password</label>
    <input type="password">

    <button type="submit">
      <i class-"..."></i>
      Submit
    </button>
  </div>
</form>
```

Incorrect: do not place more than one element on a line.

```
<form>
  <div>
    <label>Email</label><input type="text">
    <label>Password</label><input type="password">

    <button type="submit">
      <i class-"..."></i>Submit
    </button>
  </div>
</form>
```

_Justification: properly nested elements are the cornerstone for readability. More than one item per line hinders your ability to scan and pick out elements without reading an entire line; if you weren't paying attention, you probably wouldn't notice the `<input>` elements next to their labels. Blank lines between related groups of elemenets creates symmetry._

---

### 2. An element that only zero or one attribute and short or no nested text should be contained on a single line.

Correct:

```
<div class="..."></div>
<span class="...">Text</span>
```

### 3. An element with more than one attributes must have each attribute on a separate line. Elements with zero or one attributes but long nested text should place the nested text on a separate line. There is no hard rule for what constitutes "long nested text". Use good judgement.

Correct:

```
<div
  id="..."
  class="..."
  aria-labelledby="...">
</div>

<span>
  This is an example of really long nested text.
</span>
```

Incorrect: do not place more than one attribute on the same line. Do not inline elements with long nested text.

```
<div id="..." class="..." aria-labeledby="...">
</div>

<span>This is an example of really long nested content.</span>
```

_Justification: multiple attributes on a single line encourages the next developer to add attributes on the same line. Eventually, an element may have so many attributes that it requires you to scroll in order to read them. Scrolling back and forth, trying to keep a mental list of attributes and their values becomes burdensome. Putting each attribute on a single line puts every attribute and their value in the same viewport, greatly improving understandability._

---

### 4. Parent elements that are not inlined (e.g. elements that have multiple attributes) must have a blank line between the nested item and the parent.

Correct:

```
<div
  id="..."
  class="...>

  <input type="text">
</div>
```

Incorrect: do not omit the blank line between the parent and its nested content. Do not further indent the nested element(s).

```
<div
  id="..."
  class="...>
    <input type="text">
</div>
```

_Justification: the blank line between the parent's attributes and the nested item help differentiate the two. Do not attempt to differentiate between the two by adding extra indentation in the children, as in the incorrect example._

---

### 5. Sibling elements can be inlined if they each only have zero or one attribute and short nested text.

Correct:

```
<span>Text</span>
<label class="...">Text</label>
<input type="text">
```

Incorrect: do not add excessive blank lines. Do not place single attributes on a new line.

```
<span>Text</span>

<label
  class="...">

  Text
</label>

<input type="text">
```

---

### 6. Sibling elements should have a blank line between them if they cannot be inlined (e.g. an element has multiple attributes)

Correct:

```
<span>Text</span>
<label class="...">Text</label>

<input
  type="text"
  class="...">

<button type="submit">
  Submit
</button>
```

Incorrect: do not place siblings next to each other if they cannot be inlined.

```
<span>Text</span>
<label class="...">Text</label>
<input
  type="text"
  class="...">
<button type="submit">
  Submit
</button>
```

---

### 7. Sibling elements should have a blank line between them if one contains nested content.

Correct:

```
<div>
  <div>
    <span>Text</span>
  </div>

  <div>
    <span>Text</span>
  </div>

  <div class="clearfix"></div>
</div>
```

Incorrect: do not place elements with nested items adjacent to each other.

```
<div>
  <div>
    <span>Text</span>
  </div>
  <div>
    <span>Text</span>
  </div>
  <div class="clearfix"></div>
</div>
```

_Justification: sibling elements need room to breathe. Without the space, the markup becomes a run-on sentence. The space makes it easier to pick out individual sections while scanning._

---

### 8. Avoid unnecessary whitespace. Do not add blank lines between elements except when following the rules above. Do not add extra spaces between attributes.

```
<div>
  <span>Text</span>
  <span class="...">Text<span>
</div>
```

Incorrect:

```
<div>
  <span>Text</span>

  <span   class="...">Text<span>
</div>
```

---

### 9. Be consistent with attribute order (e.g. type -> id -> name -> class ...). Group related attributes together.

Correct:

```
<input
  type="text"
  id="..."
  name="..."
  class="... "
  placeholder="..."
  minlength="..."
  maxlength="..."
  data-val-required="true"
  data-val-required-msg="This field is required">
```

Incorrect: do not place attributes haphazardly.

```
<input
  minlength="..."
  type="text"
  name="..."
  placeholder="..."
  data-val-required="true"
  class="... "
  maxlength="..."
  id="..."
  data-val-required-msg="This field is required">
```

_Justification: a consistent order among attributes promotes overall readability. Grouped attributes makes it easier to identify their relationship._

---

### 10. Do not mix tabs and spaces. Pick your preference and stick with it. Enforce your choice with tooling.

_Justification: copy/paste operations will maintain correct alignment that IDEs may hide._


## Example

Consider the following snippet taken from https://search.yahoo.com:

```
<div id="uh-search" class="...">
    <form name="input" id="uh-search-form" class="..." action="https://search.yahoo.com/search" method="get"  target="_top">
        <table class="..." role="presentation">
            <tbody>
                <tr>
                    <td class="...">
                        <input id="uh-search-box" type="text" name="p" class="..." autofocus autocomplete="off" autocapitalize="off" aria-label="Search" tabindex="2">


<input type="hidden" data-fr="..." name="fr" value="yfp-t" />

<input type="hidden" data-fp="..." name="fp" value="1" />

<input type="hidden" data-toggle="..." name="toggle" value="1" />

<input type="hidden" data-cop="..." name="cop" value="mss" />

<input type="hidden" data-ei="..." name="ei" value="UTF-8" />

</td>

<td class="...">
                        <button id="uh-search-button" type="submit" class="..." data-ylk="..."   aria-label="Search Web" title="Search Web" tabindex="3"><i class="..."></i>
</button>
                    </td>

</tr>
            </tbody>
        </table>
    </form>


<ul id="Skip-links" class="...">

<li><a href="#mega-bottombar-mail" class="..." tabindex="3">Skip to Navigation</a></li>

<li><a href="#Main" class="..." tabindex="3">Skip to Main content</a></li>
        <li><a href="#Aside" class="..." tabindex="3">Skip to Related content</a></li>
    </ul>

</div>
```

There are many readability issues in this small snippet. It is difficult to get a full understanding of how elements relate by the lack of proper nesting, and quickly scanning to find a specific element is nearly impossible. How many table rows are there? How many table cells? Where is the closing `</button>` tag? Which elements are missing `aria` attributes? How many `<li>`s are there, and what are their contents? You cannot determine any of this information without thoroughly reading the markup.

Applying the rules above, the result should look like this:

```
<div
  id="uh-search"
  class="...">

  <form
    id="uh-search-form"
    name="input"
    class="..."
    action="https://search.yahoo.com/search"
    method="get"
    target="_top">

    <table
      class="..."
      role="presentation">

      <tbody>
        <tr>
          <td class="...">
            <input
              type="text"
              id="uh-search-box"
              name="p"
              class="..."
              tabindex="2"
              autofocus
              autocomplete="off"
              autocapitalize="off"
              aria-label="Search">

            <input
              type="hidden"
              name="fr"
              data-fr="..."
              value="yfp-t">

            <input
              type="hidden"
              name="fp"
              data-fp="..."
              value="1" >

            <input
              type="hidden"
              name="toggle"
              data-toggle="..."
              value="1">

            <input
              type="hidden"
              name="cop"
              data-cop="..."
              value="mss" >

            <input
              type="hidden"
              name="ei"
              data-ei="..."
              value="UTF-8">
          </td>

          <td class="...">
            <button
              type="submit"
              id="uh-search-button"
              class="..."
              title="Search Web"
              tabindex="3"
              data-ylk="..."
              aria-label="Search Web" >

              <i class="..."></i>
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </form>

  <ul
    id="Skip-links"
    class="...">

    <li>
      <a
        href="#mega-bottombar-mail"
        class="..."
        tabindex="3">

        Skip to Navigation
      </a>
    </li>

    <li>
      <a
        href="#Main"
        class="..."
        tabindex="3">

        Skip to Main content
      </a>
    </li>

    <li>
      <a
        href="#Aside"
        class="..."
        tabindex="3">

        Skip to Related content
      </a>
    </li>
  </ul>
</div>
```

Yes, this adds quite a bit more vertical content to the previous snippet, which seemed rather short (vertically) in comparison. However, there was so much content packed too tightly in the old snippet, leading to dense, hard to read code. Notice how much easier it is to pick out individual elements and their relationships? Notice how much easier it is to read all of the `<input>`'s attributes and their values, and how the attributes are listed in a consistent, semi-predictable order? This is a substantial improvement in readability and understandability.


## XML/XAML/JSX

These rules are not restrictive to HTML only. These rules produce valid XML and JSX code. Testing has determined these rules to be equally valid and produce consistent, readable results with XML, XAML, and JSX.