# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS variables and custom properties
- Absolute Positioning
- Mobile-first workflow

### What I learned

During this project, there were several key takeaways and important lessons learned that will reinforce my understanding of CSS and layout techniques. Here's a recap of the issues I encountered and the solutions, along with code samples for reference.

#### **Issue 1: Background Color Not Applying Correctly in the `section`**

##### Problem:
The background color of the `section` was being overridden by the universal selector (`*`), which applied the primary background color to all elements. This was causing the card's background to be the primary color with a white border instead of completely white.

##### Debugging:
I originally used the `*` selector to apply the primary color to background of the page, including the `section`, causing the section's background color to appear as the primary color instead of `primarywhite`.

##### Solution:
After several minutes of troubleshooting I removed the global background color rule and set the `body` background color to primary and the `section` background color to `primarywhite`.

##### Code Fix:
```css
/* Removed the global background color applied to all elements */
* {
    /* background-color: var(--primary); */
}
/* Applied the correct background color to the body */
body {
    background-color: var(--primary); 
    font-family: "Outfit", sans-serif;
}

/* Applied the correct background color to the section */
section {
    background-color: var(--primarywhite);
    /* Other styles for positioning and padding remain the same */
}
```
##### Key Learnings From Issue 1:

I have to be cautious with universal selectors (*) as they can unintentionally override other specific styles in my CSS file. I will practice targeting specific elements where possible.

#### Issue 2: Image Overflowing the Section
##### Problem:

The image inside the picture element was overflowing the boundaries of the section container.

##### Debugging:

The image was not constrained within the section's width, so it stretched beyond the container, causing overflow.

##### Solution:

To resolve this issue I used `width: 100%` and `height: auto` to make the image responsive, ensuring it fits within the container without distortion. Additionally, `object-fit: cover` helped me control how the image fills its container.

##### Code Fix:
``` css
picture img {
    width: 100%;        /* Makes the image fill the container's width */
    height: auto;       /* Maintains the image's aspect ratio */
    object-fit: cover;  /* Ensures the image fills the container without distortion */
    border-radius: 8px; /* Match the section's rounded corners */
}

```
##### Key Learning From Issue 2:

To prevent images from overflowing their containers, I have to ensure they're responsive by using `width: 100%`, `height: auto` and `object-fit` property which helps control how the image is scaled and positioned within its container.

### Continued development

In future projects, I want to continue refining my skills in **positioning elements on the screen**. While I’ve become more comfortable using techniques like `position: absolute` and centering elements, I still find it challenging to fully understand the nuances of positioning, especially when elements are stacked or when working with more complex layouts. I aim to become more proficient in utilizing different positioning strategies to handle layouts more effectively and responsively.

Additionally, **determining file paths** and **image manipulation** to ensure images display correctly remains an area I want to improve. I’ve had issues with relative vs. absolute file paths and ensuring images load as expected, particularly when dealing with folder structures or server environments. I plan to focus on understanding how paths work in different contexts (local development vs. production) and continue exploring best practices for optimizing and scaling images to avoid issues with overflow or incorrect display.


### Useful resources

- [Selectors](https://web.dev/learn/css/selectors?continue=https%3A%2F%2Fweb.dev%2Flearn%2Fcss%2F%23article-https%3A%2F%2Fweb.dev%2Flearn%2Fcss%2Fselectors) - This helped me gain a better understanding of CSS selectors, specifically how the global background setting was overriding the body background. I realized that the global rule needed to be removed in order to allow the body and section backgrounds to apply correctly.
- [How to auto-resize an image](https://sentry.io/answers/how-do-i-auto-resize-an-image-to-fit-a-div-container/) - This is an amazing article which helped me finally understand how to properly auto-resize an image so that it fit into the `section` without overflowing it. I’d highly recommend it to anyone who’s still learning how to handle images effectively with CSS.

## Author

- Website - [Lauren Ché](https://lauren-che.github.io/)
- Frontend Mentor - [@lauren-che](https://www.frontendmentor.io/profile/lauren-che)
