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
  - The Root Font Size Mismatch
  - Lack of a Shared Spacing System
  - The Impact on Accessibility
  - The Solution

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
  Rem is a relative value <br/>
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
  Decide what property needs to change with the root font size <br/>
  ~ <br/>
  Covert all relevant CSS properties from px to rem <br/>
  ~ <br/>
</span>

---

# The Solution
The solution is divided into a manual step, an automated step, and a preventive step for future consistency.

1. manual step: 
    - Develop a standardized list of commonly used sizes
    - Update the root font size from <code>15px</code> to <code>16px</code>

2. automatic step:
    - Adjust all rem-based values to align with the new root size
    - Replace all current sizes with the closest one in the standardized sizes list
    - Covert all relevant CSS properties from px to rem
    - Reduce conversion errors as much as possible, consider 3,000 conversion

3. preventive step:
    - Enforce strict usage of the standardized sizes list to maintain consistency going forward.

---
layout: iframe
url: https://hoomes.francescomeli.com/v1/proxy?url=https://github.com/pinkynrg/px-rem-optimizer
---