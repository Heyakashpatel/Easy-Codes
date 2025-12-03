```Javascript-
ON SCROLL CARDS SECTION SIDE LINE KEEP GROWING

const section = document.querySelector('.scroll-cards');
const sideline = document.querySelector('.audit-sideline-2');

const startOffset = 150; // offset of the section after how many px you want it to start
const maxPercent = 0.85; // 85% max height you can edit it (1 = 100%height)

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
