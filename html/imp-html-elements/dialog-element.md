# `<dialog>`

The `<dialog>` element represents a **modal** or **non-modal** dialog box such as a **dismissible alert** and **subwindow**.

**Modal dialog** boxes interrupt interaction with the rest of the page being inert, while **non-modal** dialog boxes allow interaction with the rest of the page.

Use the `.showModal()` method to display a **modal** dialog and the `.show()` method to display a **non-modal** dialog. 

The dialog box can be closed using the `.close()` method or using the dialog method when submitting a `<form>` that is nested within the `<dialog>` element. Modal dialogs can also be closed by pressing the `Esc key`.

## Attributes

- `closedby`: 
  - `any`: The dialog can be dismissed using any of the three methods.

  - `closerequest`: The dialog can be dismissed with a platform-specific user action(`Esc` Key) or a developer-specified mechanism (`JS`).
  - `none`: The dialog can only be dismissed with a developer-specified mechanism(`JS`).

  - If the `<dialog>` element does not have a valid closedby value specified, then 
    - if it was opened using `.showModal()`, it behaves as if the value was `"closerequest"`
    - otherwise it behaves as if the value was `"none"`.

- `open`:
  - Indicates that the dialog box is active and is available for interaction.
  - If the open attribute is not set, the dialog box will not be visible to the user. It is recommended to use the `.show()` or `.showModal()` method to render dialogs, rather than the open attribute. If a `<dialog>` is opened using the open attribute, it is **non-modal**.