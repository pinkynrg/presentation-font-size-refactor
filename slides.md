---
---

# Solving inconsistent spacing system

---
layout: center
---

# Overview 

  - What is a ❝Spacing System❞
  - What is the ❝Root Font Size❞
  - PX vs REM

  <br/>

  - The Root Font Size Mismatch
  - Lack of a Shared Spacing System
  - The Impact on Accessibility

  <br/>

  - The Final Solution
    - Manual Steps
    - Automated Steps
    - Testing Step
    - Preventive Steps

---
layout: quote
---

# What is a ❝Spacing System❞
TL;DR: A spacing system is basically a shared language between designers and developers.

A spacing system in a web design system is a set of standardized, predefined values that dictate the spacing used throughout a digital product or website. This system provides consistent spacing (e.g., margins, paddings, gaps) across various elements, layouts, and components, improving visual harmony and making the design process faster and more scalable.

---
layout: quote
---

# What is the ❝Root Font Size❞
The root font size in CSS is the font size applied to the `<html>` element. It serves as the base font size for the entire document, and it’s typically specified in pixels (e.g., 16px).

By setting a root font size, you establish a foundational unit for relative sizing throughout your stylesheet, especially when using rem units. rem (root em) units are relative to this root font size, making it easier to scale typography, spacing, and other size-related properties uniformly across a website.

---
layout: fact
---

# PX vs REM

<span style="margin: auto; text-align: left;">
  ~ <br/>
  Px is an absolute value <br/>
  ~ <br/>
  Rem is a relative value: it's a multiple of ❝root font size❞ <br/>
  ~ <br/>
</span>

---

<iframe src="https://codesandbox.io/embed/jsrqky?view=preview&module=%2Fsrc%2FApp.tsx&hidenavigation=1"
  style="width:100%; height: 500px; border:0; border-radius: 4px; overflow:hidden;"
  title="px-vs-rem"
  allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
  sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
  frameBorder="0"
></iframe>

---
layout: image-left
image: ./assets/story_15px.webp
---

# The Root Font Size Mismatch

<br/>

<i>
  "Once, in a bustling digital realm, an adventurous developer quietly changed the root font to 15px, neglecting to inform the designers. Now, the designers spoke in 16px, while the developers spoke in 15px—and chaos ensued"
</i>

<br/>

Example of a Problem:
1. Designer creates a 4rem by 4rem box
2. Developer codes the 4rem by 4rem box
3. Designer notices a 60px by 60px instead of 64px by 64px

---
layout: fact
---

# How to Solve?

<span style="margin: auto; text-align: left;">
  ~ <br/>
  Update the root font size from <code>15px</code> to <code>16px</code> <br/>
  ~ <br/>
  Fix all rem values considering the new root font size<br/>
  ~ <br/>
</span>

---
layout: image-left
image: ./assets/story_design.webp
---

# Lack of a Shared Spacing System

<br/>

<i>
  "But without a shared standard, each crafted their parts in slightly different sizes. Slowly, the design grew patchy, and what was once seamless became scattered—a web of mismatched pieces."
</i>

<br/>

Example of a Problem:
1. Designer creates a a text field 2rem high
2. After a few months another designer creates another text field 2.2rem high
3. An inconsistency in the text field element has been introduced 

---
layout: fact
---

# How to Solve?

<span style="margin: auto; text-align: left;">
  ~ <br/>
  Create a list of shared sizes <br/>
  ~ <br/>
  Replace all current sizes with the closest one in the shared list <br/>
  ~ <br/>
  Enforce strict usage of shared sizes <br/>
  ~ <br/>
</span>

---
layout: image-left
image: ./assets/story_a11y.webp
---

# The Impact on Accessibility

<br/>

<i>
  "But by using px instead of rem, they’d created rigid designs. When villagers tried to zoom, the components refused to grow, leaving many struggling to see. And so, they learned: flexibility is key to a design everyone can use."
</i>

Example of a Problem:
1. Old user doesn't see well 
2. He sets the default root font size on his browser to be 24px
3. He navigates to Beefree App and can't read the text well 

---
layout: fact
---


# How to Solve?

<span style="margin: auto; text-align: left;">
  ~ <br/>
  Decide what property needs to grow with the root font size <br/>
  ~ <br/>
  Covert all relevant CSS properties from px to rem <br/>
  ~ <br/>
</span>

---
layout: fact
---

# The Final Solution

  <span style="margin: auto; text-align: left;">
    ~ <br/>
    Spacing system <br/>
    ~ <br/>
    Convertion <br/>
    ~ <br/>
    Testing <br/>
    ~ <br/>
    Enforce future consistency <br/>
    ~ <br/>
  </span>

---

# Spacing system
Designers and Developers deciding a common language

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
            </ul>
        </div>
        <div class="group">
            <div class="group-title">Base Sizes</div>
            <ul>
                <li>space-05 → 2px</li>
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
layout: iframe-right
url: https://hoomes.francescomeli.com/v1/proxy?url=https://github.com/pinkynrg/px-rem-optimizer
---

# Convertion
Convert of 3000+ values that align with the spacing system

- started doing by head 
- didn't work
- created automated script (24h of work to fine tune the tool)

---

# Testing
picture of every page of beefree app to compare before and after, and see what had to be fixed

- talk about the testing

---

# Enforce future consistency
created a styling rule to force us to use variables instead of raw sizes

- talk about the linting

---
layout: end
---

# Final Toughts

A unified spacing and font sizing system fosters clarity, accessibility, and visual consistency. By standardizing our approach and enforcing it with automated checks, we’ve set a solid foundation for scalable and harmonious designs moving forward.

---