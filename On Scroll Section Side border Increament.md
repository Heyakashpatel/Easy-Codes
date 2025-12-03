```Javascript-
ON SCROLL CARDS SECTION SIDE LINE KEEP GROWING

const section = document.querySelector('.scroll-cards');
const sideline = document.querySelector('.audit-sideline-2');

const startOffset = 150;
const maxPercent = 0.85;

function updateSideLine() {
    const rect = section.getBoundingClientRect();
    const viewportTop = window.scrollY;
    const sectionTop = section.offsetTop;
    const sectionHeight = section.clientHeight;

    const progressStart = sectionTop + startOffset;
    const progressEnd = sectionTop + sectionHeight;

    const maxHeight = (progressEnd - progressStart) * maxPercent;

    if (viewportTop < progressStart) {
        sideline.style.height = "0px";
        return;
    }

    if (viewportTop > progressEnd) {
        sideline.style.height = maxHeight + "px";
        return;
    }

    let scrolled = viewportTop - progressStart;

    scrolled = Math.min(scrolled, maxHeight);

    sideline.style.height = scrolled + "px";
}

window.addEventListener('scroll', updateSideLine);
window.addEventListener('resize', updateSideLine);
```
