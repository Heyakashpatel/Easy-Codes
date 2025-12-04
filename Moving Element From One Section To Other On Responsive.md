JAVASCRIOPT TO MOVE ONE ELEMNNT FROM ITS PARENT SECTION / CONTAINER TO SOME OTHER SECTION / CONTAINER ON RESPONSIVE 

```
<script>
  // SETTINGS (you can modify these easily)
  const movingElement = document.querySelector(".slider-content-card");
  const originalContainer = movingElement.parentElement;
  const targetContainer = document.querySelector(".ontab-content");
  const breakpointWidth = 1025; // screen width where movement happens

  // Main function to move element based on screen width
  function moveElementOnBreakpoint() {
    if (window.innerWidth < breakpointWidth) {
      // Move element to target container (only if not already inside)
      if (!targetContainer.contains(movingElement)) {
        targetContainer.appendChild(movingElement);
      }
    } else {
      // Move element back to original container
      if (!originalContainer.contains(movingElement)) {
        originalContainer.appendChild(movingElement);
      }
    }
  }

  // Run once when the page loads
  moveElementOnBreakpoint();

  // Run again whenever the window resizes
  window.addEventListener("resize", moveElementOnBreakpoint);
</script>

```
