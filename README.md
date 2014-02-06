# Y.Views Classes #

It's often useful to have `Y.View` instances stamped with reasonable CSS classes by default. This extension makes that easier!

## Usage ##

The extension is mixed into the parent view like any other extension using `Y.Base.create`.

```javascript
var View = Y.Base.create("view", Y.View, [
    Extensions.ViewClasses
], {
    ...
});
```
    
The extension looks for a `css` property on the `Y.View` instance to append to the default classes. 

```javascript
var View = Y.Base.create(..., {
    ...,
    css : "fooga booga wooga"
});
```

## Example ##

```javascript
var View = Y.Base.create("my-view", Y.View, [
    Extensions.ViewClasses
], {
    css : "fooga wooga",

    render : function() {
        this.get("container").setHTML("<p>Hi</p>");
    }
});

(new View()).render()

```

will render the following HTML

```html
<div class="app-view my-view fooga wooga">
    <p>Hi</p>
</div>
```

## License ##

```
Copyright (c) 2014 Patrick Cavit

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
