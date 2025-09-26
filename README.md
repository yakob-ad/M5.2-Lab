# M5.2 LAB - ACCESSIBILITY

This project explores accessibility issues in web design by fixing up the provided website, mainly according to existing WCAG standards, so it is more accessible for different types of users.

## Getting Started

To get started, clone this repository to your local machine.

There is no need to install Node.js dependencies.

## Development

It is recommended to use the VSCode Live Server extension to run the project
locally. This will allow you to see changes in real-time as you make them. There
is no need to run a build process or refresh the page manually. Additionally,
you do not need to setup a local server to run the project.

## Running

To run the site using Live Preview in VS Code, press `Ctrl+Shift+P` to open the 
Command Palette, then select `Live Preview: Start Server`. You can copy the URL 
from the VS Code Live Preview and paste it into a web browser such as Chrome to 
view the site externally.

To end Live Preview, open Command Palette and select `Live Preview: Stop Server`.

## Testing

There are no written tests for this project.

## Accessibility Lab Answers
### Color
- The original color scheme used black text on a standard green background (#008000), which resulted in a contrast ratio of approximately 4.09:1. This falls short of the WCAG accessibility guidelines for normal-sized text, making it difficult to read—especially for users with visual impairments or in low-light environments. After testing the contrast and identifying the issue, I resolved it by changing the background color from green to white (#FFFFFF). This adjustment dramatically improved the contrast ratio to 21:1, ensuring the black text is now highly legible and fully compliant with accessibility standards.

### Semantic HTML
- Keyboard navigation works to a certain extent—it highlights the HTML elements I'm tabbing through, confirming that I'm moving across components. However, it fails to activate the Show/Hide comments button, and there's no clear visual cue on the selected element to indicate it's been reached.

-  I replaced all the deprecated font tags with header semantic elements, and the `<br>` tags with the appropriate paragraph elements to organize the different paragraphs. Each section of the article has a header, so I put the headers into a `<section>` element along with the related paragraphs. On top of all this, many generic html tags were replaced by proper semantic elements with meaning, including the `<div class="nav"></div>` part which was replaced with `<nav class="nav"></nav>`.

### The Images
- I added `alt` attribute text for each `<img>` element to ensure screen readers can describe an image for visually impaired users.

### The Audio Player
- For users who are hearing impaired or deaf and unable to listen to the audio, a collapsible transcript is provided as a readable alternative.
The <audio> player isn't accessible to those using older browsers that don't support HTML audio. How can you allow them to still access the audio?
- I put the proper `aria-label` for the audio element and included an alternative link for accessing the audio in case the browser doesn't support audio players

### The Forms
- To make the search form accessible without affecting the visual design, you can add a label that’s only visible to screen readers using the aria-label attribute directly on the `<input>` element. For example: `<input type="search" aria-label="Search the site">`. This ensures assistive technologies can identify the input’s purpose without displaying extra text to sighted users.

- In the comment form, the two `<input>` elements already have visible labels and matching `for` and `id` attributes, which correctly associate them semantically. To reinforce this visually, the existing `.flex-pair` CSS rule already ensures the `<input>` elements are positioned properly.

### The Show/Hide Comment Control
- I replaced the `<div>` with a `<button>`. Unlike the generic `<div>` element, the `<button>` is focusable and interactive and can be accessed using the keyboard Tab and Enter Keys.

### The Table
- For the table, the proper `<th>` tags were used to identify the top row cells as column titles. A `<caption>` was added at the top to highlight what kind of information the table provided.

## Additional Accessibility Improvements
- The search `<form>` in the header includes the `role="search"` attribute, which signals to screen readers that this section is dedicated to search functionality.

- The following line of code in the `<head>` section helps the website adjust to various screen sizes, including mobile devices.
    ```
    <meta name="viewport" content="width=device-width, initial-scale=1">
    ```

