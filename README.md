# Origami.js #

## Dependencies ##

- JQuery
- coffee-script.js

## Usage ##

#### Defining the `#origami` div ####

#### Options ####

The following options are customizable:

- `hierarchy`: Defines the hierarchy of headers to be folded.
    + Earlier values supercede later ones. For instance, given the default `['H1', 'H2', 'H3', 'H4', 'H5', 'H6']`, a `H6` tag following an `H1` header will be folded under when that header is folded.
    + Tags that are not included in this array are given the lowest priority. For example, any `p` tag will be folded under any of the `H*` tags given the defaults.

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
