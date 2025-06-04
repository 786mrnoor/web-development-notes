# Background Properties

Used to style element backgrounds.

## `background-color`
Sets background color.

- `transparent` - (default)
- `<color>`

## `background-image`
Sets an image as the background.

- `none`
- `url("image-url")`
- `linear-gradient()`
- `radial-gradient()`
- `conic-gradient()`

## `background-repeat`

Specifies if/how the background image should repeat.

- `repeat` (default)
- `repeat-x`
- `repeat-y`
- `no-repeat`
- `space`
- `round`

## `background-position`
Sets the initial position of the background image.  
If you only specify one keyword, the other value will be "center"

- `left top`
- `left center`
- `left bottom`
- `right top`
- `right center`
- `right bottom`
- `center top`
- `center center`
- `center bottom`
- `x% y%`
- `xpos ypos`
- `0% 0%` (default)

## `background-size`
Specifies the size of the background image.

- `auto`(default)
- `cover` - fill entire container, maintain aspect ratio
- `contain` - fit inside element and make sure the image is fully visible
- `<length>` - width height
- `<percentage>` width height

## `background-attachment`
Determines if the background scrolls with the page.
`fixed` is commonly used for **parallax effects**.

- `scroll` - (default) scroll with the page.
- `fixed` - not scroll with the page
- `local` - scroll with the element's contents

## `background-clip`
Defines the painting area of the background.

- `border-box` (default)
- `padding-box`
- `content-box`

## `background-origin`
Defines the positioning area of the background image.

- `border-box`
- `padding-box` (default)
- `content-box`

## `background-blend-mode`
Blends the background image with the background color.

- `normal`
- `multiply`
- `screen`
- `overlay`
- `darken`
- `lighten`
- `color-dodge`
- `saturation`
- `color`
- `luminosity`

## `background`
Set multiple background properties in one line.

If one of the properties in the shorthand declaration is the `background-size` property, you must use a `/` to separate it from the `background-position` property, e.g. `background:url(smiley.gif) 10px 20px/50px 50px;` will result in a background image, positioned 10 pixels from the left, 20 pixels from the top, and the size of the image will be 50 pixels wide and 50 pixels high.

If using multiple `background-image` sources but also want a `background-color`, the `background-color` parameter needs to be last in the list.
