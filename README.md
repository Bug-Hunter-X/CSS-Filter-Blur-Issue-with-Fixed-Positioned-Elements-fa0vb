# CSS Filter Blur Issue with Fixed Positioned Elements

This repository demonstrates a subtle bug related to using the `filter: blur()` CSS property on elements with `position: fixed`.  When a blur is applied to a fixed element, the blur radius extends beyond the element's boundaries.  If this extends beyond the viewport, unexpected visual artifacts or a lack of blur can result near the edges of the viewport.

The `bug.css` file contains the problematic code, showing the unexpected visual results. The `bugSolution.css` file shows a possible solution to mitigate the problem.

## Bug Details

The issue stems from how the browser renders the blur.  The blur radius isn't clipped to the element's boundaries when using `position: fixed`, causing the blur to extend beyond the viewport.

## Solution

The solution involves adding a container element around the fixed element and applying the blur to the container. This confines the blur effect within the boundaries of the container, preventing visual anomalies at the viewport's edges.