# Origami.js #

[Example usage](devonzuegel.com/)

## Usage ##

#### Defining the `#origami` div ####
Wrap the relevant html with a `<div id="origami">{{ HTML TO FOLD }}</div>`.

#### Including the `.js` or `.coffee` files

#### CSS ####
```css
#origami        {  display: none  }
#origami-header {  /* ... */  }
```

#### Options ####

The following options are customizable:

- `hierarchy`: Defines the hierarchy of headers to be folded.
    + Earlier values supercede later ones. For instance, given the default `['H1', 'H2', 'H3', 'H4', 'H5', 'H6']`, a `H6` tag following an `H1` header will be folded under when that header is folded.
    + Tags that are not included in this array are given the lowest priority. For example, any `p` tag will be folded under any of the `H*` tags given the defaults.
- `fold`: Defines the headers that have the origami button and corresponding folding functionality. This is distinct from the `hierarchy` options, which tells what tags supercede others.
- `btn_symbols`: Defines the symbols on the origami button on open and close. If you wish the buttons' styling to be defined entirely through css, make both of these values the empty string `""` and update the `btn_klass` attributes.
- `start_closed`: Defines the header tag types that will begin folded.
- `hdr_klass`: Defines the classes for the entire header when it is folded and unfolded. If you wish to apply two classes, write them as one string, separated by a space: `"class-one class-two"`.
- `btn_klass`: Defines the classes for the origami buton when its assocaited header is folded and unfolded. If you wish to apply two classes, write them as one string, separated by a space: `"class-one class-two"`.
- `duration`: A string or number determining how long the animation will run. Higher values indicate slower animations, not faster ones. The strings 'fast' and 'slow' can be supplied to indicate durations of 200 and 600 milliseconds, respectively.

The default values for these options are:
```coffee
optns = {
    hierarchy: ['H1', 'H2', 'H3', 'H4', 'H5', 'H6']
    fold:      ['H1', 'H2', 'H3', 'H4', 'H5', 'H6']
    btn_symbols:
        open:   '+'
        closed: '-'
    start_closed: []  # No headers start folded.
    hdr_klass:        # No default classes defined for header.
        open: ''
        closed: ''
    btn_klass:        # No default classes defined for button.
        open: ''
        closed: ''
    duration: 200     # Milliseconds.
}
```


## Dependencies ##

#### JQuery ####
Include the following script tag in the `head` of your html page:
```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
```

#### Coffeescript Compiler ####
If you opt to use the `.coffee` file instead of the `.js` file (not recommended), you must also include the following script **after** the `.coffee` script. This will compile the Coffeescript to Javascript.
```html
<script type="text/javascript" src="https://rawgit.com/jashkenas/coffeescript/master/extras/coffee-script.js"></script>
```
