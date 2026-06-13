# Glow — Sign-Up Page

A sign-up page for **Glow**, a fictional mood-journaling app — a gentle space to check in with yourself, track your moods, and watch your inner weather shift over time.

Built as part of [The Odin Project](https://www.theodinproject.com/)'s Intermediate HTML & CSS course, then extended with a custom "soft-girl engineer" brand identity.

<img width="1915" height="942" alt="image" src="https://github.com/user-attachments/assets/967c5331-99a1-4b50-8276-48121d160dde" />

## Features

- **Two-column layout** — a full-height photo sidebar paired with a content panel, built with Flexbox
- **Responsive grid form** — six fields arranged in a two-column CSS Grid
- **Custom validation states:**
  - Gold focus glow on the active input (`:focus`)
  - Red border + glow on invalid passwords (`:user-invalid`)
  - Minimum password length enforced via `minlength`
- **Branded visual identity** — cream palette, warm gold accents, circular logo badge, and a Fraunces + Poppins type pairing
- **Staggered entrance animation** that respects `prefers-reduced-motion`
- **Accessibility & UX details** — associated labels, `autocomplete` attributes, placeholders, and clear required/optional field markers

## Built With

- HTML5
- CSS3 (Flexbox, Grid, custom properties, keyframe animations)
- [Google Fonts](https://fonts.google.com/) — Fraunces & Poppins

## Running Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/linmicarm/sign-up-form.git
   ```
2. Open `index.html` in your browser.

That's it — no build step or dependencies.

## Lessons Learned

- **An element only has the height of its content.** My sidebar's background image wouldn't show until I established a height chain — `min-height: 100vh` on the parent container, which then let the flex children stretch to fill it. This clicked the relationship between content, containers, and the viewport.
- **`:user-invalid` vs `:invalid`.** Plain `:invalid` flags empty required fields the moment the page loads, which feels aggressive. `:user-invalid` waits until the user has actually interacted with a field — a much better experience, and the reason validation should *respond* to the user rather than pre-judge them.
- **Transparency belongs on the color, not the element.** Using `rgba()` on a `background-color` keeps the foreground text fully solid, while the `opacity` property would have faded the text too. Small distinction, big visual difference.
- **`border-radius: 50%` only makes a circle when width and height are equal** — otherwise it's an oval. Tying the logo badge's dimensions together was the fix.
- **Auto margins absorb free space in flexbox.** `margin-top: auto` on the photo credit pushed it to the bottom of the sidebar without needing `justify-content: space-between`, giving finer control over individual items.
- **`id` is for the page; `name` is for the server.** Inputs need a `name` attribute to actually submit data — `id` only links labels and CSS. A form can look complete and still send nothing.

## Future Optimizations

- **Responsive design** — the layout is desktop-only for now. The next step is a mobile breakpoint that stacks the sidebar above the form and collapses the two-column grid into one.
- **JavaScript password matching** — currently each password field validates independently. Confirming the two fields *match* requires JS, which is a planned enhancement.
- **CSS custom properties** — the gold, cream, and gray values are repeated throughout the stylesheet. Pulling them into `:root` variables (`--gold`, `--cream`) would make rebranding a one-line change.
- **Real form submission** — wiring the form to an actual backend or form service (and adding success/error feedback) would make it fully functional rather than a front-end mockup.
- **Optimized background image** — serving a compressed/appropriately-sized version of the photo would improve load time.

## What I'd Do Differently Next Time

- **Plan the CSS structure up front.** A couple of bugs came from pasted blocks ending up nested or with mismatched braces. Sketching the selector hierarchy before writing styles would have caught these earlier.
- **Set up CSS variables from the start** rather than hard-coding colors and refactoring later.
- **Build mobile-first.** Starting with the single-column layout and expanding to two columns is usually cleaner than retrofitting responsiveness onto a desktop design.

## Credits

- Background photo by [Imani Bahati](https://unsplash.com/@imani_bht) on [Unsplash](https://unsplash.com/)
- Logo designed in [Canva](https://www.canva.com/)
- Project brief from [The Odin Project](https://www.theodinproject.com/lessons/node-path-intermediate-html-and-css-sign-up-form)
