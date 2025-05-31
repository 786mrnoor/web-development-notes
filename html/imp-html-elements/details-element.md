# `<details>`

The `<details>` element is used to create a collapsible section that the user can open and close. It's often used for things like FAQs and Accordion Menus.

- `<details>`: The container element that holds the content.


- `<summary>`: The clickable label that toggles the visibility of the rest of the content inside `<details>`.

## Attributes

- `open`: The details are shown when this attribute exists and hidden when this attribute is absent.
- `name`: This attribute enables multiple `<details>` elements to be connected, with only one open at a time. If multiple grouped `<details>` elements are given the open attribute, only the first one in the source order will be rendered open. `<details>` elements don't have to be adjacent to one another in the source to be part of the same group.

## Events

- `Toggle`: The `toggle` event is dispatched to the `<details>` element whenever its state changes between open and closed.

```js
details.addEventListener("toggle", (event) => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

## Styles

```css
details summary::marker,
:is(::-webkit-details-marker) {
  content: "+ ";
}

details summary{
  list-style: none;
}

details::details-content{
  transition: content-visibility 600ms allow-discrete;   
}
```

## Examples

Multiple named disclosure boxes

Only the first one will be rendered open.

```html
<details name="requirements" open>
  <summary>Graduation Requirements</summary>
  <p>
    Requires 40 credits, including a passing grade in health, geography,
    history, economics, and wood shop.
  </p>
</details>
<details name="requirements" open>
  <summary>System Requirements</summary>
  <p>
    Requires a computer running an operating system. The computer must have some
    memory and ideally some kind of long-term storage. An input device as well
    as some form of output device is recommended.
  </p>
</details>
<details name="requirements" open>
  <summary>Job Requirements</summary>
  <p>
    Requires knowledge of HTML, CSS, JavaScript, accessibility, web performance,
    privacy, security, and internationalization, as well as a dislike of
    broccoli.
  </p>
</details>
```