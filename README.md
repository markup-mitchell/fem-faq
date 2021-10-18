# Frontend Mentor - FAQ accordion card solution

This is a solution to the [FAQ accordion card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/faq-accordion-card-XlyjD0Oam). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Overview

I had a lot of fun with this one. These junior and newbie challenges - it's one thing to put them together like the screenschots on mobile and desktop, but if you come at them like they're ACTUAL components you'd actually want to re-use in some way, they present a lot of the problems you get in real life.

I went through a few stages with this - let's see if I can remember them:

## Stages

### The Accordian

I've done plenty of media objects and cards IRL so I went after the content first. I knew it was going to be the `<detail>` element all the way, and I've never used that for real, so it was interesting to get into the weeds a bit.

Styling it was reasonably strightforward, if fiddly to figure out how it all fit together

I've been meaning to do something with variable fonts for ages, so this was a nice opportunity to transition between weights. Because the text changes color on hover the effect is quite hard to observe, but I think that's all to the good.

I used `:before` on the `summary`s to make the whole `detail` a click target for ease of use. This makes the text unselectable, which isn't ideal, but I'm only prepared to go so far down the rabbit-hole with these challenges. I made that choice to avoid JS, and I raise it here just to flag it as a known issue.

The `details` element transitions can't be animated with CSS, unfortunately, but I did find that `transition: all` rule affected the change in the `summary`'s `margin-bottom` property, producing a sort of pseudo-animated effect. It's not super-smooth, but I'll take it over javascript.

### Card Component - first iteration

I went pretty far with the design using my normal nested-flexbox approach, which looks adequate given the card contents are one-dimensional at both screen sizes...

BUT I was bothered by the fact that I had to add arbitrary padding to the page layout because I was pulling the image out of the card with negative margin and changing the visual extremities.

I wanted to be able to treat the card as a component with hard boundaries that didn't need ad hoc adjustments in any given context.

So.

### Card Component - second iteration

I restructured the card to use CSS grid, so that I could allocate elements to visual locations without monkeying with the flow.

It was an interesting change of perspective to realise that the "card" no longer had to be a structural container; it's just a design element that can be layered in underneath the content in the grid configuration. That's given me some new directions to explore.

I really wanted to make the component multi-purpose. Like, it could house whatever arbitrary content and imaged you might want. But I had to give up on that idea - it just feels too weirdly specific. Perhaps if variations on those assets were produced... but it seems doubtful.

It would be nice to come up with something more generic - a card with a prop-based API that could be configured with images "spilling out" in various ways.

### Rationalise the media-queries

I really wanted this to be elegant and easy to read, but I haven't achieved that.

The idea was to keep all the relevant layout shifts in `:root` custom properties so the relationships were explicit and expliciy for each breakpoint, but there are just too many moving parts for it to be very comprehensible.

### Postion things for repsonsiveness

I allowed myself to deviate from the design a little for what I think are good reasons. I had to edit a bunch of the SVG documents to suit my intended implementation, since I wasn't happy with the asset exports provided.

I set up the illustration elements in a way that would gracefully (IMO) allow the accordian to expand and contract and to accommodate changes in the copy, which would be inevitable in a real world situation.

I think I've interpreted the spirit of the design and moved it into an interactive format that captures the intended effect.

### Other bits and bobs

- give some measure of responsiveness to the mobile image for a better look on tablets
- focus-visible styling for keyboard navigation
- set `overflow-x: scroll` for permanent scrollbar to prevent layout shift when accordian expands past the fold

DONE (for now)
