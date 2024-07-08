## My CSS Notes from [Mozilla](https://developer.mozilla.org/en-US/docs/Learn/CSS)

### Adding CSS to document

1. External stylesheets : `<link rel="stylesheet" href="styles.css" />`
2. Internal Stylesheet: _`<style>`_ element inside _**`<head>`**_
3. Inline Style: Using _style="property1:value1;property2:value2"_

### CSS Selectors

1. Type Selector : `span{background-color:yellow}`
   - Universal Selector : `*{margin:0}`
2. Class Selector : `span.highlight{background-color:yellow}`
3. ID Selector : `h1#heading{background-color:yellow}`
4. Attribute Selector : `a[href="www.oracle.com"]{color:red}`
   - `[attr]` - Matches element with attribute
   - `[attr=value]` - Matches element with attribute whose value is _exactly_ value
   - `[attr~=value]` - Matches element with attribute whose value is exactly value or contains value in its list of values
   - `[attr|=value]` - Matches element with attribute with exact value or value followed by hyphen
   - `[attr^=value]` - Matches elements with an attr attribute, whose value begins with value.
   - `[attr$=value]` - Matches elements with an attr attribute whose value ends with value.
   - `[attr*=value]` - Matches elements with an attr attribute whose value contains value anywhere within the string.

### Pseudo Classes and Pseudo Elements

- Pseudo Classes:
  - `:first-child`
  - `:last-child`
  - `:only-child`
  - `:hover` (based on behavior)
  - `:focus`
- Pseudo Elements:

  - `::before`
  - `::after`
  - `::first-line`

### Combinators

- Descendant Combinator : `<space>`
- Child Combinator : `>`
- Adjacent Sibling : `+`
- General Sibling : `~`

### Cascade, specificity, and inheritance

**Inheritance** : Following value for property: _**inherit, initial, revert, revert-layer, unset**_

Increasing order of importance:

1. Source Order
2. Specificity : _id > class > element_
3. Importance

Conflicting declarations applied in following order:

> User-agent < User (Normal) < Author(Normal) < Author(Important) < User (Important) < User-agent(Important)

Cascade Layer:
`@layer firstLayer, secondLayer;`

### Box Model

- Inline Box Vs Block Box

  - not break on to new line
  - width and height don't apply
  - top and bottom padding, margin will apply but will not cause other inline boxes to move away from box
  - left and right padding, margin will apply and will cause other inline boxes to move away from box

- Inline block
  - do not break on to new line
  - width and height respected
  - padding, margin, border etc., will push other elements away from box

### Margins, padding and borders

> margin : margin-top margin-right margin-bottom margin-left
> border : border-top border-right border-bottom border-left
> border : border-width border-style border-color
> border-top-width, border-right-style, border-bottom-color
> border-radius: \<horizontal radius> \<vertical radius> in % or pixels
> padding : padding-top padding-right padding-bottom padding-left

> background-image : url(star.png) or gradients
> background-repeat : repeat-x|repeat-y|no-repeat|repeat
> background-size: cover|contain | some% | some px
> background-position : top|center|bottom right|center|left or pixels(from left followed by from top)
> background-attachment: scroll|fixed|local

> background : background-image background-position / background-size background-repeat background-color

**Example**

> .box {
> background: linear-gradient(105deg, rgb(255 255 255 / 20%) 39%, rgb(51 56 57 / 100%) 96%) center center / 400px 200px no-repeat, url(big-star.png) center no-repeat, rebeccapurple;
> }

### Text Directions

> writing-mode : horizontal-tb | vertical-rl
> inline-size : <> (instead of width)
> block-size: <> (instead of height)
> padding-inline-start: <>
> margin-block-end: <>

### Overflow

> overflow(-x|-y) : visible|hidden|scroll|auto

### Sizing

> max-width : <> (for reducing size)
> min-width: <> (for enlarging)
> max-height:
> min-height:

For Images, set either max-width/max-height to fit into container or set the width and height with object-fit

> object-fit : cover|contain|fill

### Styling tables

> \<th scope='col|row|colgroup|rowgroup'>
> table-layout: fixed|auto
> th:nth-child(1):{width:30%}
> border-collapse:collapse

Zebra Striping

> tr:nth-child(odd):{background-color:<>}
> tr:nth-child(even):{background-color:<>}

### Fonts

> font-family: serif|sans-serif|monospace|cursive|fantasy
> font-size : px|%|em|rem
> font-style:italic|normal|oblique
> font-weight:normal|bold|lighter|bolder|100-900
> text-transform: uppercase|lowercase|capitalize
> text-decoration: overline|underline|none|line-through
> text-align : center|left|right
> line-height: 1.2
> letter-spacing: px
> word-spacing: px
> font : font-style font-variant font-weight font-size/line-height font-family

### Lists

> list-style : list-style-type list-style-position list-style-image

## Layout

### Flexbox

> display:flex
> flex-direction: row|column|row-reverse|column-reverse
> flex-wrap : wrap|nowrap
> flex-flow : flex-direction flex-wrap
> justify-content : flex-start|flex-end|space-around|space-between
> align-items: flex-start|flex-end|center|stretch

On items:

> flex : flex-grow flex-shrink flex-basis
> align-self:
> order:

### Grid

On Container:

> display:grid
> grid-template-rows : fr|px|repeat
> grid-template-columns:
> grid-auto-rows:
> grid-auto-columns:
> grid-gap : (or gap:)
> grid-template-areas:

on items:

> grid-area:
> grid-column:
> grid-row:

### Floats

> float: left|right
> margin-right|margin-left :
> clear: left|right|both

On container(to prevent float overflowing):

> display: flow-root

### Positioning

> position : static|relative|absolute|fixed|sticky
> left:
> right:
> top:
> bottom:
> z-index:

### Multi-column Layout

> column-count: \<number>
> column-width: px
> column-gap: px
> column-rule: 2px solid red
> column-span: \<number> (For spanning subhead)
> break-inside: avoid

### Media Queries

> @media print and (max-width:600px){
> }
