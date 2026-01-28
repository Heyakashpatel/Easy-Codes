```HTML
<div class="card">
    <div class="card-inner">
      <div class="card-front">
        Front
      </div>
      <div class="card-back">
        Back
      </div>
    </div>
  </div>

  NOTICE THE HTML STRUCTURE ABOVE

  ```CSS
<style>
    .card {
      width: 300px;
      height: 500px;
      perspective: 1000px;
    }

    .card-inner {
      position: relative;
      width: 100%;
      height: 100%;
      transition: transform 0.6s ease;
      transform-style: preserve-3d;
    }

    .card:hover .card-inner {
      transform: rotateY(180deg);
    }
    
    .card:hover{
      cursor: pointer;
    }

    .card-front,
    .card-back {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 24px;
      font-weight: bold;
    }

    .card-front {
      background: tomato;
      border: 1px solid #ddd;
    }

    .card-back {
      background: #333;
      color: white;
      transform: rotateY(180deg);
    }
  </style>
```
