```html
<div class="tilt-card">
  <img src="your-image.png" alt="Bulk SMS">
  <div class="content">
    <h3>Bulk SMS</h3>
    <p>Fast, reliable delivery of promotional, transactional, and informational SMS...</p>
    <button>Learn More</button>
  </div>
</div>
```
```css
.tilt-card {
  width: 300px;
  height: 400px;
  background: #fff;
  border-radius: 15px;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  transition: transform 0.2s ease;
  transform-style: preserve-3d;
  perspective: 1000px;
}

.tilt-card img {
  width: 100%;
  display: block;
}

.tilt-card .content {
  padding: 20px;
}

.tilt-card:hover {
  cursor: pointer;
}
```

```js
const card = document.querySelector('.tilt-card');

card.addEventListener('mousemove', (e) => {
  const rect = card.getBoundingClientRect();
  const x = e.clientX - rect.left; // x position within the card
  const y = e.clientY - rect.top;  // y position within the card

  const centerX = rect.width / 2;
  const centerY = rect.height / 2;

  const rotateX = ((y - centerY) / centerY) * 10; // max 10 degrees
  const rotateY = ((x - centerX) / centerX) * -10;

  card.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.05)`;
});

card.addEventListener('mouseleave', () => {
  card.style.transform = 'rotateX(0) rotateY(0) scale(1)';
});
```
