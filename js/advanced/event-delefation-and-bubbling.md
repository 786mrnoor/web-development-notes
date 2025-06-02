# **Event Delegation & Bubbling in JavaScript** 🚀  

## What is an Event?

An event is a signal that something happened on the page — like:

- Clicking a button
- Typing in a field
- Resizing the window

## **What is Event Bubbling?**
When an event happens on an element, it **bubbles up** (propagates) to its parent, then grandparent, to the `window` object.

---

## **What is Event Delegation?**
**Event Delegation** is a pattern in JavaScript where we **attach a single event listener** to a parent element **instead of multiple child elements**. The event **bubbles up** from the child to the parent, allowing efficient event handling.   


## **How Does Event Delegation Work?**
Event Delegation works because of **Event Bubbling**.

---

## **8️⃣ Summary**
✔ **Event Bubbling:** Events bubble from child → parent.  
✔ **Event Delegation:** Attach **one** event listener to a parent.  
✔ **Use `event.target`** to check which child was clicked.  
✔ **Use `stopPropagation()`** to prevent bubbling (if needed). 