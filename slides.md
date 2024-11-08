---
layout: intro
---

# Solving Inconsistent Spacing System

---
layout: center
---

# Overview 

  - What is a ❝Spacing System❞
  - What is the ❝Root Font Size❞
  - px vs rem

  <br/>

  - Problem #1: The Root Font Size Mismatch
  - Problem #2: Lack of a Shared Spacing System
  - Problem #3: The Impact on Accessibility

  <br/>

  - Designing The Spacing System
  - Converting to the new Spacing System
  - Enforcing future consistency

---
layout: quote
---

# ❝Spacing System❞

TL;DR: A spacing system is a key component of a Design System that defines consistent, standardized spacing rules.

A spacing system in a web design system is a set of standardized, predefined values that dictate the spacing used throughout a digital product or website. 

This system provides consistent spacing (e.g., margins, paddings, gaps) across various elements, layouts, and components, improving visual harmony and making the design process faster and more scalable.

---
layout: quote
---

# ❝Root Font Size❞
TL;DR: The root font size is set on the HTML element of a webpage and some elements in the page scale with it. 


The root font size serves as the base font size for the entire document, and it’s typically specified in pixels (e.g., 16px).

By setting a root font size, you establish a foundational unit for relative sizing throughout your stylesheet, especially when using rem units. rem (root em) units are relative to this root font size, making it easier to scale typography, spacing, and other size-related properties uniformly across a website.

---
layout: quote
---

# px vs rem
TL;DR: Px is an absolute size. Rem is a relative size that scales with the root font size


Use px when you need fixed-size elements that won't change, such as for borders or shadows. <br/>
Use rem for font sizes to make it more accessible to users who have changed their browser's default font size.

---
layout: image
image: ./assets/box_px_rem.gif
backgroundSize: 30rem
---
---
layout: image-left
image: ./assets/story_15px.webp
---

# Problem #1: The Root Font Size Mismatch

<div class="book-quote">
  "Once, in a bustling digital realm, an adventurous developer quietly changed the root font to 15px, neglecting to inform the designers. Now, the designers spoke in 16px, while the developers spoke in 15px—and chaos ensued"
</div>

<div class="problem">
  <p>Example of the Problem</p>
  <ol>
    <li> Designer creates a <code>4rem</code> blue square </li>
    <li> Developer codes the <code>4rem</code> blue square </li>
    <li> Designer notices the square to be <code>60px</code> instead of <code>64px</code></li>
    <li> Developer compensates by mutlipling the box's sizes to a factor of <code>16/15</code> </li>
    <li> The new size in the code is <code>4.26rem</code> by <code>4.26rem</code> </li>
  </ol>
</div>

---
layout: image-left
image: ./assets/story_15px.webp
---

# Problem #1: To Do List

<ul class="todo">
  <li> Update root font size from <code>15px</code> to <code>16px</code> </li>
  <li> Convert rem values considering the new root font size and multiply by a factor <code>15/16</code> </li>
</ul>

---
layout: image-left
image: ./assets/story_design.webp
---

# Problem #2: Lack of a Shared Spacing System

<div class="book-quote">
  "But without a shared standard, each crafted their parts in slightly different sizes. Slowly, the design grew patchy, and what was once seamless became scattered—a web of mismatched pieces."
</div>

<div class="problem">
  <p> Example of the Problem </p>
  <ol>
    <li> Designer creates a a text field <code>2rem</code> high </li>
    <li> After a few months another designer creates another text field <code>2.2rem</code> high </li>
    <li> An inconsistency in the text field element has been introduced </li>
  </ol>
</div>

---
layout: image-left
image: ./assets/story_design.webp
---

# Problem #2: To Do List

<ul class="todo">
  <li>Create a list of shared sizes </li>
  <li>Replace all current sizes with the closest one in the shared list </li>
  <li>Enforce strict usage of shared sizes </li>
</ul>

---
layout: image-left
image: ./assets/story_a11y.webp
---

# Problem #3: The Impact on Accessibility

<div class="book-quote">
  "But by using px instead of rem and using a hard-coded 15 px root font size, they had created rigid designs. When villagers tried to zoom, the components refused to grow, leaving many struggling to see. And so, they learned: flexibility is key to a design everyone can use."
</div>

<div class="problem">
  <p> Example of the Problem </p>
  <ol>
    <li> An old user doesn't see well </li>
    <li> The old user sets the default root font size on his browser to be <code>24px</code> </li>
    <li> The old user navigates to Beefree App and can't read the text well </li>
  </ol>
</div>

---
layout: image-left
image: ./assets/story_a11y.webp
---

# Problem #3: To Do List

<ul class="todo">
  <li> Remove hard-coded 15px root font size </li>
  <li> Decide what property needs to grow with the root font size </li>
  <li> Covert all relevant CSS properties from px to rem </li>
</ul>

---
layout: fact
---

# The Solution

  <span style="display: inline-block; margin: auto; text-align: left;">
    <br/>
    ☐ Designing The Spacing System <br/>
    <br/>
    ☐ Converting <br/>
    <br/>
    ☐ Testing <br/>
    <br/>
    ☐ Enforcing future consistency <br/>
    <br/>
  </span>

---

# Designing The Spacing System
Designers and Developers deciding a common language (thank to Fabio Mojetta)

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f9f9f9;
        color: #333;
    }
    .container {
        font-size: 7px;
        display: flex;
        align-items: flex-start;
        gap: 20px;
        padding: 20px;
        max-width: 1000px;
        margin: auto;
    }
    .column {
        display: flex;
        flex-direction: column;
        gap: 15px;
        flex: 1;
        background-color: #1f1f1f;
        padding: 15px;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }
    .group {
        border: 1px dashed #ccc;
        padding: 10px;
        border-radius: 5px;
    }
    .group-title {
        font-weight: bold;
        color: #555;
        margin-bottom: 5px;
    }
    .column ul {
        list-style: none;
        padding: 0;
        margin: 0;
    }
    .column li {
        padding: 2px 0;
    }
</style>

<div class="container">
    <div class="column">
        <div class="group">
            <div class="group-title">Small Sizes</div>
            <ul>
                <li>space-0 → 0px</li>
                <li>space-025 → 1px</li>
                <li>space-05 → 2px</li>
            </ul>
        </div>
        <div class="group">
            <div class="group-title">Base Sizes</div>
            <ul>
                <li>space-1 → 4px</li>
                <li>space-2 → 8px</li>
                <li>space-3 → 12px</li>
                <li>space-4 → 16px</li>
                <li>space-5 → 20px</li>
                <li>space-6 → 24px</li>
                <li>space-7 → 28px</li>
                <li>space-8 → 32px</li>
                <li>space-9 → 36px</li>
                <li>space-10 → 40px</li>
                <li>space-11 → 44px</li>
                <li>space-12 → 48px</li>
            </ul>
        </div>
    </div>
    <div class="column">
        <div class="group">
            <div class="group-title">Medium Sizes</div>
            <ul>
                <li>space-16 → 64px</li>
                <li>space-20 → 80px</li>
                <li>space-24 → 96px</li>
                <li>space-28 → 112px</li>
                <li>space-32 → 128px</li>
                <li>space-36 → 144px</li>
                <li>space-40 → 160px</li>
                <li>space-44 → 176px</li>
                <li>space-48 → 192px</li>
                <li>space-52 → 208px</li>
                <li>space-56 → 224px</li>
                <li>space-60 → 240px</li>
            </ul>
        </div>
    </div>
    <div class="column">
        <div class="group">
            <div class="group-title">Large Sizes</div>
            <ul>
                <li>space-70 → 280px</li>
                <li>space-80 → 320px</li>
                <li>space-90 → 360px</li>
                <li>space-100 → 400px</li>
            </ul>
        </div>
        <div class="group">
            <div class="group-title">Extra Large Sizes</div>
            <ul>
                <li>space-120 → 480px</li>
                <li>space-140 → 560px</li>
                <li>space-160 → 640px</li>
                <li>space-180 → 720px</li>
            </ul>
        </div>
        <div class="group">
            <div class="group-title">Huge Sizes</div>
            <ul>
                <li>space-220 → 880px</li>
                <li>space-260 → 1040px</li>
                <li>space-300 → 1200px</li>
                <li>space-340 → 1360px</li>
            </ul>
        </div>
    </div>
</div>

---
layout: image-left
image: ./assets/graph.png
backgroundSize: 65vh
---

# Converting to the new Spacing System

<br/>

Facts about px-rem-optimizer script:
  - took 23 hours to build
  - was improved by testing its work with Persy
  - was used to convert other internal projects with the same root font size problem
      - beefree-applications
      - bee-ui-library
      - bee-connectors

---

# Enforce future consistency
setup of style rules to force us to use variables instead of raw sizes

- Add space variables in Figma for easy access during design and development
- Code plugin to forbid usage of arbitrary size 
- Code plugin to force usage of design system's sizes (thank to Efrem Bonfiglio)

---

<style>

  /* Container to hold the two iframes side-by-side */
  .iframe-container {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 40px;
  }

  /* Styling for individual iframes to zoom out */
  iframe {
    width: 100%;
    height: 90vh;
    zoom: 0.5;
    transform-origin: 0 0; /* Anchors the zoom effect to the top-left corner */
    border: none; /* Removes iframe border */
  }

  /* Ensures full-width alignment without scrolling */
  .before, .after {
    flex: 1;
    overflow: hidden; /* Prevents scrolling within the iframe */
    position: relative; /* Allows positioning of titles */
  }

  /* Styles for "Before" and "After" titles */
  .before::before, .after::before {
    content: attr(class);
    position: absolute;
    top: 10px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 1.5rem;
    font-weight: bold;
    color: #444;
    background-color: #f5f5f5;
    padding: 0.5em 1em;
    border-radius: 8px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  }
</style>

<div class="iframe-container">
  <div class="before">
    <iframe src="https://zustand.beepro.io/app/login"></iframe>
  </div>
  <div class="after">
    <iframe src="https://router.beepro.io/app/login"></iframe>
  </div>
</div>

---
layout: end
---

# Thanks for listening

---