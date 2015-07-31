###1. Basic formatting

####a. We delimit attribute values using double-quotes.

Good:         `<div class=”much-class”>`
Not so good:  `<div class=’very-attribute’>`

####b. Each indentation is two spaces long.

Good: 
```
<div class="parent">
··<div class="parent__child"></div>

··<div class="parent__child parent__child--variant">
····<span>Can I live?</span>
··</div>
</div>
```

Not so good:
```
<div class="parent">
····<div class="parent__child"></div> <!-- Too much indentation -->

··<div class="parent__child parent__child--variant">
··<span>Can I live?</span> <!-- Not enough indentation -->
··</div>
</div>
```

####c. We don’t include a forward-slash on void elements.

Good:         `<br>`
Not so good:  `<br/>`

###2. Structure

We strive for easy-to-parse, tidy code and have found a few rules pretty great for keeping things readable and neat:

####a. Some things can stay on one line.

Good: `<div></div>`
Also good: `<div>Can I live?</div>`

Use judgement as to when it stops being readable, or is nearing your maximum line length.

For example, this might be best:
```
<div>
··Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
</div>
```

####b. Nesting elements means visual nesting too. 

Good:
```
<div>
··<a>Foo</a>
</div>
```

####c. Add space between elements for clarity - it probably isn’t necessarily between parent & child elements or multiple one-line elements, but might be better between same-level multi-line elements (or multi-line blocks, such as a stack of one-line elements).

Maybe:
```
<ul>
··<li>1</li> <!-- No space between parent `ul` or child `li` -->
··<li>2</li> <!-- No further nesting for such a small one-line element -->
··<li>3</li>
··<li>4</li>
</ul>
```

Maybe:
```
<ul>
··<li>
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</li>
  
··<li> <!-- Space between same-level multi-line elements -->
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</li>
</ul>
```

Maybe:
```
<div>
··<span>Foo</span>
··<span>Bar</span>

··<span>Foo</span> <!-- Space between multi-line blocks -->
··<span>Bar</span>

··<span> 
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</span>
  
··<span>
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</span>
</div>
```

####d. Try using line-breaks for multiple attributes.

Good:
```
<div custom-attribute 
class="something" 
role="something-else"></div> 
<!-- The closing tag    ^^^    can stay on the same line for empty elements-->

<div custom-attribute 
class="something" 
role="something-else">
··Foo <!-- Otherwise nest plz -->
</div> 
```

####e. Use your judgement on all the above for when things become less readable.

Might be OK:
`<input required custom-attribute>`

Might not be OK:
`<custom-element class=”foo” custom-attribute=”value-for-custom-attr”>Bar</custom-element>`

Isn’t this nicer?:
```
<custom-element class="foo"
custom-attribute=”value-for-custom-attr”>
  Bar
</custom-element>
```
