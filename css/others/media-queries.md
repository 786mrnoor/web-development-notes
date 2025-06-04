# CSS Media Queries

**Media queries** make your website responsive by applying different styles at **different screen sizes, resolutions, or devices**. 

```css
@media not|only mediatype and (mediafeature and|or|not mediafeature) {
  /* CSS-Code; */
}
```

## Common Media Types

| Media Type | Description                     |
| ---------- | ------------------------------- |
| `all`      | Default for all devices         |
| `screen`   | Computer, tablet, phone screens |
| `print`    | Styles for print preview        |
| `speech`   | Screen readers                  |

## Common Media Features
| Feature        | Example                    | Description                        |
| -------------- | -------------------------- | ---------------------------------- |
| `width`        | `(max-width: 768px)`       | Target screen width                |
| `height`       | `(min-height: 500px)`      | Target screen height               |
| `orientation`  | `(orientation: portrait)`  | Phone/tablet orientation           |
| `aspect-ratio` | `(aspect-ratio: 16/9)`     | Width-to-height ratio              |
| `resolution`   | `(min-resolution: 300dpi)` | DPI for print/screens              |
| `hover`        | `(hover: hover)`           | Checks if device supports hovering |

## Combine Multiple Conditions

**AND (and)**
```css
@media screen and (max-width: 768px) and (orientation: portrait) {
  /* Apply styles */
}
```

**COMMA (`,` = OR)**
```css
@media (max-width: 500px), (orientation: landscape) {
  /* Apply styles if either is true */
}
```