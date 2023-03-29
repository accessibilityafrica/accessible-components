# Description

Forms are an essential part of user interfaces that allow users to provide input and interact with a website or application. Forms typically consist of one or more form elements, such as input fields, dropdown lists, checkboxes, radio buttons, and buttons.

# Best Practices

## Labels

- All form controls, such as text fields, checkboxes, radio buttons, and drop-down menus, should be labeled for identification purposes. The common method for achieving this is by utilizing the <label> element.
- In certain situations, the purpose is clear when the content is visually displayed, therefore the label can be hidden. However, it will still need to be accessed through other forms of interaction i.e screen reader and speech input users

### aria-label

[aria-label](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label attribute adds a descriptive label to an element that is read by assistive technologies e.g screen readers

### aria-labelledby

[aria-labelledby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby) attribute provides a description for an element by referencing other elements on the webpage.

## Helper/Descriptive Text

- Approach One: Placing a hint and label as spans inside the label texts ensures they are both read by screenreaders. This also increases the hit area, when a user taps on the content inside the label element, it focuses on the respective input element.
- Approach Two: Placing the descriptive text in a p element and reference it using [aria-describedby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby). Note, aria-describedby is not supported by IE11

## Input Types

## Errors

## Validation

## Grouping

## What to avoid

1. Avoid placeholder texts to provide hints.
2. Not using proper semantic element i.e using <div> instead of <form>
3. Relying on visual interpretation only.

# Importance of Accessible Forms

1. Form controls are more readily identifiable and comprehensible for individuals who use screen readers
2. Enhancing layout structure, instructions and feedback in forms aids individuals with cognitive impairments in comprehension and filling out of the form.

# Resources

1. MDN Accessible Form Blueprint.
2. [W3C Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)
