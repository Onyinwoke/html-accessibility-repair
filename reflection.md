# Assignment 2.9: HTML Accessibility Reflection

Completing the MDN HTML accessibility exercises helped me understand that writing HTML is not just about how a webpage looks. It is also about how people navigate, understand, and interact with it.

## Lessons Learned

### 1. Semantic HTML matters

I learned that HTML elements should be used for their intended purpose. For example, a `<button>` is more appropriate for an action than a clickable `<div>`. Native elements provide built-in keyboard behaviour and communicate their purpose to assistive technologies.

### 2. Forms need properly connected labels

I learned that every form input should have a meaningful label. Using `<label for="name">` with an input whose `id="name"` connects the label to the correct field. I also learned that `<fieldset>` and `<legend>` help group related form controls and describe the group.

### 3. Links should explain their destination

I learned to avoid vague link text such as "Click here." Descriptive links help users understand where a link leads, even when they navigate through a list of links without reading the surrounding paragraph.

### 4. Images need appropriate alternative text

I learned that meaningful images need alternative text that communicates their purpose or relevant content. Decorative images should use `alt=""` so screen readers can skip them rather than announce unnecessary information.

## Conclusion

This assignment has helped me see accessibility as an important part of writing good HTML from the beginning. I will apply semantic elements, connected form labels, meaningful links, and appropriate alternative text in future projects rather than treating accessibility as an afterthought.