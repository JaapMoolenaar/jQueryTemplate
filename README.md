# jQuery Template
 This is basic jQuery wrap/implementation of underscores templating

Compiles JavaScript templates into functions that can be evaluated for rendering.
Useful for rendering complicated bits of HTML from JSON data sources.

Template functions can both interpolate values, using <%= ... %>, as well as
execute arbitrary JavaScript code, with <% ... %>. If you wish to interpolate
a value, and have it be HTML-escaped, use <%- ... %>. When you evaluate a
template function, pass in a data object that has properties corresponding to
the template's free variables. The settings argument should be a hash
containing any $.template.defaults that should be overridden.

Can be called on an element to use the elements contents as the template
source.

<script type="text/html" id="tmp">hello: <%= name %></script>
$('#tmp').template('render', {name: 'moe'}); => hello: moe

A template can be rendered to an element directly, using the 3rd and 4th
parameter, using the 3rd as destination, and 4th as method; 'html', 'append',
'prepend', etc.
$('#tmp').template('render', {name: 'moe'}, $('#destination')); => hello: moe
$('#tmp').template('render', {name: 'moe'}, $('#destination'), 'html'); => hello: moe

If called on a collection of 1 item, the result of a method will be returned.

The compiled template source can be accessed using the source method:
$('#tmp').template('source')

## Underscore.js
The templating function is based on http://underscorejs.org
Which is (c) 2009-2015 Jeremy Ashkenas, DocumentCloud and Investigative Reporters & Editors
It may be freely distributed under the MIT license.