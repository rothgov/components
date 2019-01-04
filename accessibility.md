---
title: Accessibility
layout: default
category: Standards
---

# Accessibility
Our products and services should be accessible to all. At minimum, features should conform to Web Content Accessibility Guidelines 2.0 at Level AA. When designing and building patterns check them against these standards:

## Image alternatives
Make sure all images have appropriate alternative text.

### Decorative images
Images just for aesthetic purposes (borders, flourishes, etc) must take `alt=""` to remove them from screen reader output. Omitting the `alt` attribute does not suffice.

### Photographs
Images of Council offices and team members should have alternative text, but just a couple of well-written and evocative sentences. Example from the marketing site: `alt="A customer service advisor turns, smiling to the camera, in our naturally lit and bustling office"`.

### Interactive elements
Interactive elements using icons or the Council logo need to describe their purpose, not the appearance of the image itself. For example, the alternative text for a link to the Twitter account should read "Rotherham Council on Twitter" or similar, not "Picture of the bulbous, blue Twitter bird".

## Keyboard support
Make sure all functionality available by mouse and touch is also available by keyboard. From the keyboard section of the Manual Testing page:

- Tab for moving focus to the next interactive element
- Shift + Tab for moving focus to the previous interactive element
- Enter and/or Space for activating (i.e. pressing/clicking) the interactive element
- ← and/or → for moving focus within tabs and some other custom controls
- Esc for closing menus, dialogs, and popups
- Ensure that CSS focus styles are present and clear.

### Labels
Ensure all buttons, links, and form elements have text labels readable by assistive technologies (screen readers).

For links or buttons, the label is provided (in order of preference) by text, an image alternative, or an `aria-label` attribute.

```
<button>The label</button>

<button><img src="path/to/image.svg" alt="The label"></button>

<button aria-label="The label"></button>
```

For form elements, you would use a `<label>` element associated to the input's `id` using the `for` attribute:

```
<label for="the-id">The label</label>
<textarea id="the-id"></textarea>
```

## Headings
- Headings must only be used where appropriate, to label ensuing sections of content. Statements and straplines are not headings.
- Nesting structure is paramount, using the correct heading levels. For example, in a section beginning with an `<h3>`, an `<h4>` would label a subsection, and another `<h3>` a sibling section
- There should only be one `<h1>` per page/screen. Components describing a part of that page/screen are unlikely to contain an `<h1>`.

## Contrast
Contrast between text and its background must be sufficient in all cases. Solar already meets (WCAG AA) standards for color contrast ratios. If you need to check new colour combinations make sure you check it with a Contrast ratio tool first.

## Color independence
No element of the interface should rely on color to convey meaning. For example, a red color used to convey the presence of an error needs to be accompanied by a symbol such as a warning sign or "✖️".

## Roles
Make sure the correct elements and — where appropriate — ARIA roles are used in relation to their behavior. For example, use a link (`<a>`) if the behaviour is to load a resource/page. Otherwise a `<button>` may be more appropriate.

Do not use `<span>`s or `<div>`s for interactive elements, even where the correct ARIA roles are in place. They still need additional scripting to become focusable and clickable by keyboard. Using a `<button>` is more reliable.

```
<!-- bad -->
<div role="button" tabindex="0">Press me</div>

<!-- good -->
<button>Press me</button>
```

For additional guidelines and resources see [GOV.UK Service Manual](https://www.gov.uk/service-manual/helping-people-to-use-your-service).

### See also:
- [Principles](/styleguide/principles)
- [Colour](/styleguide/colour)

[Back to homepage](/styleguide/)
