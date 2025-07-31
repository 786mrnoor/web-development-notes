# HTML

- HTML is the standard markup language for creating Web pages.

- HTML describes the structure of a Web page.

## HTML Tags

The HTML tags are used to define the elements on the web page. They are the keywords that are enclosed inside the angle brackets(`<>`). The examples of HTML tags are `<div>`, `<p>`, `<a>`, `<span>`, `<img>` etc.

## HTML Element

- An HTML element is defined by a opening tag, some content, and a closing tag.
- Some HTML elements have no content (like the `<br>` element). These elements are called empty elements. Empty elements do not have a closing tag.

## HTML Attributes

- All HTML elements can have attributes.
- Attributes provide additional information about elements.
- Attributes are always specified in the opening tag.
- Attributes usually come in name/value pairs like: `name="value"`.

## Example Explained

- The `<!DOCTYPE html>` declaration defines that this document is an HTML5 document.
- The `<html>` element is the root element of an HTML page.
- The `<head>` element contains meta information about the HTML page.
- The `<title>` element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's tab).
- The `<body>` element is a container for all the visible contents.

## HTML Meta Tags

`<meta>` tags are used to define the metadata about the HTML document, **including character set**, **description**, **keywords**, **author**, and **viewport settings**. Placed within the `<head>` element.

## HTML Formatting Elements

- `<b>` - Bold text
- `<strong>` - Important text
- `<i>` - Italic text
- `<em>` - Emphasized text
- `<mark>` - Marked text
- `<small>` - Smaller text
- `<del>` - Deleted text
- `<ins>` - Inserted text
- `<sub>` - Subscript text
- `<sup>` - Superscript text

> **Note:** The `<strong>` tag is similar to the `<b>` tag but screen readers consider `<strong>` text to be more important and read it with a different tone to convey its importance.  
> **Screen Reader:** A screen reader is a software used by visually impaired people that helps them use a website. It translates on screen information into speech.

## COLOR

### RGB Color Values

**rgb(red, green, blue):**

- To display black, set all color parameters to 0, like this: rgb(0, 0, 0).
- To display white, set all color parameters to 255, like this: rgb(255, 255, 255).

**rgba (red, green, blue, alpha):**

- The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (not transparent at all).

### HEX Color Values

In HTML, a color can be specified using a hexadecimal value in the form:

`#rrggbb`

**Shades of Gray**: Shades of gray are often defined using equal values for all three parameters:

- `rgb(60, 60, 60)`
- `rgb(100, 100, 100)`
- `#c6c6c6`
- `#666`

### HSL Color Values

**hsl(hue, saturation, lightness)**

- Hue is a degree on the color wheel from 0 to 360. 0 is red, 120 is green, and 240 is blue.
- Saturation is a percentage value. 0% means a shade of gray, and 100% is the full color.
- Lightness is also a percentage value. 0% is black, and 100% is white.

## Favicon

A favicon is a small image displayed next to the page title in the browser tab.

## HTML Block and Inline Elements

- A block-level element always starts on a new line.
- A block-level element always takes up the full width available.
- An inline element does not always starts on a new line.
- An inline element only takes up the required width.
- `width`, `height`, `margin-top` and `margin-bottom` propeties does not work on **non-replaced inline elements**

## HTML File Paths

| Example                           | Description                                                                            |
| --------------------------------- | -------------------------------------------------------------------------------------- |
| `<img src="picture.jpg">`         | The "picture.jpg" file is located in the same folder as the current page.              |
| `<img src="images/picture.jpg">`  | The "picture.jpg" file is located in the images folder in the current folder.          |
| `<img src="/images/picture.jpg">` | The "picture.jpg" file is located in the images folder at the root of the current web. |
| `<img src="../picture.jpg">`      | The "picture.jpg" file is located in the folder one level up from the current folder.  |

## HTML Semantic Elements

- A semantic element clearly describes its meaning to both the browser and the developer.
- Semantic HTML improves accessibility, SEO, and code readability. Key elements include `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, and `<footer>`.
- Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.

## HTML Entities

Reserved characters in HTML must be replaced with entities:

- `<` (less than) = `&lt;`

- `>` (greater than) = `&gt;`

## HTML Forms

An HTML form is used to collect user input.

## HTML Canvas Graphics

The HTML `<canvas>` element is used to draw graphics on a web page.

## HTML SVG Graphics

- SVG defines vector-based graphics in XML, which can be directly embedded in HTML pages.
- SVG graphics are scalable, and do not lose any quality if they are zoomed or resized:

## IMPORTANT HTML ELEMENTS

### [`<details>`](imp-html-elements/details-element.md)

### [`<dialog>`](imp-html-elements/dialog-element.md)

### `<iframe>`
