# Description

Forms are an essential part of user interfaces that allow users to provide input and interact with a website or application. Forms typically consist of one or more form elements, such as input fields, dropdown lists, checkboxes, radio buttons, and buttons.

# Best Practices

## 1. Labels

All form controls, such as text fields, checkboxes, radio buttons, and drop-down menus, should be labeled for identification purposes. The common method for achieving this is by utilizing the `label` element.

In certain situations, the purpose is clear when the content is visually displayed, therefore the label can be hidden. However, it will still need to be accessed through other forms of interaction i.e screen reader and speech input users

### a. aria-label

The [aria-label](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label) attribute adds a descriptive label to an element that is read by assistive technologies e.g screen readers

### b. aria-labelledby

The [aria-labelledby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby) attribute provides a description for an element by referencing other elements on the webpage.

## 2. Helper/Descriptive Text

- **Approach One:** Placing a hint and label as spans inside the label texts ensures they are both read by screenreaders. This also increases the hit area i.e when a user taps on the content inside the label element, it focuses on the respective input element. This is useful on small screens and to some people with motor disabilities.

```html
<label>
  <span>Password</span>
  <span>Password length must be above 8 characters</span>
</label>
```

- **Approach Two:** Placing the descriptive text in a p element and reference it using [aria-describedby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby). Note, aria-describedby is not supported by IE11. Hit area is not increased.

```html
<label for="password">Password</label>
<p id="description">Password length must be above 8 characters</p>
<input type="password" id="password" aria-labelledby="description" />
```

Each label should be closest to its form control.

## 3. Input Types

There are numerous different HTML input types e.g `text`, `password`, `url`. They each help with collecting specific data from users. Use them appropriately.

A label with descriptive text for each input should be available. Associate a label with its corresponding input by matching `for` and `id` attributes.

```html
<label for="name">Name</label> <input id="name" type="text" />
```

[List of HTML input types](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)

## 4. Feedback

It is essential to inform users of the outcome of their form submission, whether it is successful or not.

### Errors

#### a. Overall Feedback

There are several techniques that can be implemented to communicate overall error feedback:

##### Document Title.
   The document title i.e `title` tag, is the first part of a web page to be read out. Screen reader users will immediately access any information if something went wrong with their submission.

Useful when page reloads after a server request.

##### Summary.
   It is helpful to list errors at the top, before the form.
   
   This section should have a distinct heading that is easily identified.
   
   If page does not reload/refresh, make use of `aria-live="assertive"` or `role="alert"`. These ensure that users of assistive technology i.e screen readers are notified that there are errors.

```html
<div aria-live="assertive" id="message"></div>
```

```html
<div role=""alert"></div>
```

#### b. In-line Feedback
  Place the relevant error message just above the field. Placing it below increases the chances of it being obscured by browser autocomplete panel or by the onscreen keyboard.

## 5. Validation

## 6. Grouping

# What to avoid

1. Avoid placeholder texts to provide hints.
2. Not using proper semantic element i.e using `div` instead of `form`
3. Relying on visual interpretation only.
4. Changing border color or using color only to communicate error.

# Importance of accessible forms

1. Form controls are more readily identifiable and comprehensible for individuals who use screen readers
2. Enhancing layout structure, instructions and feedback in forms aids individuals with cognitive impairments in comprehension and filling out of the form.

# Resources

1. MDN Accessible Form Blueprint.
2. [W3C Forms Tutorial](https://www.w3.org/WAI/tutorials/forms/)
