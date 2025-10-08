```HTML
<div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <h2>Front</h2>
    </div>
    <div class="flip-card-back">
      <h2>Back</h2>
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

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; 
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  color: white;
}

.flip-card-front {
  background-color: #2980b9;
}

.flip-card-back {
  background-color: #e74c3c;
  transform: rotateY(180deg);
}
```
