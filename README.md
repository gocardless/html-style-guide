## GoCardless HTML style guide

Have a look at how we write HTML at GoCardless - let us know if you've found the same rules effective, if you've used others that are better, or if there's anything missing entirely which you think it's worth having a rule for!

###1. Basic formatting

####a. We delimit attribute values using double-quotes

Good:
```html
<div class="much-class">
```

Not so good:
```html
<div class='very-attribute'>
```

####b. Each indentation is two spaces long

Good: 
```html
<div class="parent">
··<div class="parent__child"></div>

··<div class="parent__child parent__child--variant">
····<span>Can I live?</span>
··</div>
</div>
```

Not so good:
```html
<div class="parent">
····<div class="parent__child"></div> <!-- Too much indentation -->

··<div class="parent__child parent__child--variant">
··<span>Can I live?</span> <!-- Not enough indentation -->
··</div>
</div>
```

####c. We don’t include a forward-slash on void elements

Good:         
```html
<br>
```

Not so good:
```html
<br/>
```

###2. Structure

We strive for easy-to-parse, tidy code and have found a few rules pretty great for keeping things readable and neat

####a. Some things can stay on one line

Good: 
```html
<div></div>
```

Also good:
```html
<div>Can I live?</div>
```

Use judgement as to when it stops being readable, or is nearing your maximum line length.

For example, this might be best:
```html
<div>
··Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
</div>
```

####b. Nesting elements means visual nesting too 

Good:
```html
<div>
··<a>Foo</a>
</div>
```

####c. Add space between elements for readability

It probably isn’t necessary between parent & child elements or multiple one-line elements:

eg
```html
<ul>
··<li>1</li> <!-- ^^^ No space between parent `ul` and child `li` -->
··<li>2</li> <!-- ^^^ No space between multiple one-line elements -->
</ul>
```

The parent/child rule would apply to single multi-line elements too:

eg
```html
<div>
··<span> <!-- ^^^ No space between parent `div` and child `span` -->
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</span>
</div>
```

But might be better between same-level multi-line elements:

eg
```html
<ul>
··<li>
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</li>
  
··<li> <!-- ^^^ Space between same-level multi-line elements -->
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</li>
</ul>
```

Also between groups of one-line elements: 

eg:
```html
<div>
··<span>Foo</span>
··<span>Bar</span>

··<span>Foo</span> <!-- ^^^ Space between groups of one-line elements -->
··<span>Bar</span>

··<span> <!-- ^^^ Space between groups of one-line elements -->
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</span>
</div>
```

And finally between any combinations of one-line or multi-line elements (so basically bear in mind spacing as soon as you introduce a multi-line element):

eg:
```html
<div>
··<span>Foo</span>

··<span> <!-- ^^^ Space between one-line and multi-line -->
····Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
··</span>
</div>
```

####d. Try using line-breaks for multiple attributes, keeping the first attribute on the tag's opening line

Good:
```html
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

####e. Use your judgement on all the above for when things become less readable

Might be OK:
```html
<input required custom-attribute>
```

Might not be OK:
```html
<custom-element class="foo" custom-attribute="value-for-custom-attr">Bar</custom-element>
```

Might be better:
```html
<custom-element class="foo"
custom-attribute="value-for-custom-attr">
  Bar
</custom-element>
```
