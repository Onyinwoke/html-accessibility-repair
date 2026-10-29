# Assignment 2.9: HTML Accessibility Repair

## Introduction

This assignment examines inaccessible HTML markup and replaces it with native semantic HTML. The goal is to improve keyboard accessibility, screen-reader support, and usability for all users.

## 1. Login: Use a Native Button

**Original markup**

```html
<div onclick="login()">Login</div>
```

**Problem**

A `<div>` is a generic container, not an interactive control. It is not keyboard-accessible by default, and assistive technologies do not automatically identify it as a button.

**Repaired markup**

```html
<button type="button">Login</button>
```

**User impact**

- **Keyboard users:** Can focus the button and activate it using standard keyboard controls.
- **Screen-reader users:** Hear that the element is a button and can identify its purpose.
- **Other users:** Benefit from the familiar appearance and behaviour of a native button.

The button must be connected to the actual login functionality for it to perform the intended action.

## 2. About Us: Use a Semantic Heading

**Original markup**

```html
<div class="heading">About Us</div>
```

**Problem**

The `<div>` does not communicate that the text is a heading. A CSS class named `heading` does not give an element semantic meaning.

**Repaired markup**

```html
<h1>About Us</h1>
```

**User impact**

- **Keyboard and assistive-technology users:** Can use heading navigation when supported by their tools.
- **Screen-reader users:** Can identify the main heading and understand the page structure.
- **Other users:** Can recognise the main topic more easily.

The page should use headings in a logical hierarchy, such as `<h1>` for the main title and `<h2>` for major sections.

## 3. Team Image: Provide Alternative Text

**Original markup**

```html
<img src="team.jpg">
```

**Problem**

The image has no `alt` attribute. Screen readers may not be able to communicate its meaning to users who cannot see it.

**Repaired markup**

```html
<img src="team.jpg" alt="Our team members">
```

**User impact**

- **Screen-reader users:** Receive a text alternative describing the image's purpose.
- **Users with images disabled or unavailable:** May still understand the image's intended meaning.
- **Other users:** Benefit when the description provides useful context.

The alternative text must accurately describe the actual image. If an image is purely decorative and adds no meaningful information, use `alt=""` instead.

## 4. Name Input: Add an Explicit Label

**Original markup**

```html
<div>
  Name
  <input type="text">
</div>
```

**Problem**

The word "Name" is ordinary text, not a programmatically associated label. The input also lacks an `id` and a `name` attribute.

**Repaired markup**

```html
<label for="name">Name</label>
<input type="text" id="name" name="name" required>
```

**User impact**

- **Screen-reader users:** Can have the field's name announced when navigating to the input.
- **Keyboard users:** Can move to the input using normal keyboard navigation.
- **Mouse and touch users:** Can click or tap the label to focus the field.

The label's `for` value must match the input's `id` exactly. The `name` attribute identifies the field when form data is submitted.

## 5. Services Link: Use Meaningful Link Text

**Original markup**

```html
<a href="/services">Click here</a>
```

**Problem**

"Click here" does not explain the destination. Users who navigate through a list of links may not understand where it leads.

**Repaired markup**

```html
<a href="/services">Services and what we offer</a>
```

**User impact**

- **Screen-reader users:** Can understand the link's purpose, including when links are read out of context.
- **Keyboard users:** Can navigate to the link and activate it using the keyboard.
- **Other users:** Can understand the destination before opening it.

Links should describe their destinations or purposes. The destination should also be valid for the website.

## 6. Document Language: Declare the Language

**Original markup**

```html
<html>
```

**Problem**

The document does not declare its primary language. Assistive technologies may not know which pronunciation rules to use.

**Repaired markup**

```html
<html lang="en">
```

**User impact**

Screen readers can use the declared language to select appropriate pronunciation rules. This improves comprehension for users who rely on spoken output.

The language code should match the primary language of the document.

## 7. Heading Hierarchy: Organise the Page

**Problem**

Using generic containers instead of headings makes the page structure harder for assistive technologies to interpret. Skipping heading levels without a clear reason can also make the structure confusing.

**Repaired example**

```html
<h1>About Us</h1>

<section aria-labelledby="team-heading">
  <h2 id="team-heading">Meet Our Team</h2>
</section>

<section aria-labelledby="login-heading">
  <h2 id="login-heading">Member Login</h2>
</section>

<section aria-labelledby="contact-heading">
  <h2 id="contact-heading">Contact Us</h2>
</section>
```

**User impact**

A logical heading hierarchy helps screen-reader users navigate sections and helps all users understand how the content is organised. The `aria-labelledby` attributes associate each section with its visible heading.

## 8. Native HTML and Keyboard Accessibility

Native HTML controls should be preferred over generic elements that imitate interactive controls.

- Use `<button>` for actions.
- Use `<a>` for navigation.
- Use `<label>` for form inputs.
- Use semantic headings to structure content.
- Provide appropriate image alternatives.
- Declare the document language.

These elements provide built-in browser behaviour and accessibility information. JavaScript should implement application functionality where needed, not imitate native controls unnecessarily.

## Conclusion

This repair demonstrates that accessibility starts with choosing the right HTML elements. Semantic markup, explicit labels, meaningful links, appropriate alternative text, and logical headings make websites easier to navigate and understand for a wider range of users.