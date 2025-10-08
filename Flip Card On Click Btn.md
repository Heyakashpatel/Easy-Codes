```HTML
<div class="flip-card">
  <div class="flip-card-inner" id="cardInner">
    <div class="flip-card-front">
      <h2>Front</h2>
      <button id="flipButton" onclick="flipCard()">Read</button>
    </div>
    <div class="flip-card-back">
      <h2>Back</h2>
      <button id="flipButtonBack" onclick="flipCard()">Back</button>
    </div>
  </div>
</div>
```

```CSS
.flip-card {
  width: 300px;
  height: 200px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}

.flipped {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  color: white;
  padding: 20px;
  box-sizing: border-box;
}

.flip-card-front {
  background-color: #3498db;
}

.flip-card-back {
  background-color: #e74c3c;
  transform: rotateY(180deg);
}
```

```JS
<script>
  function flipCard() {
    const card = document.getElementById('cardInner');
    card.classList.toggle('flipped');
  }
</script>
```
