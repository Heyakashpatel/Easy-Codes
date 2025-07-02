```html
<html>
  <head>
    <style>
    body {
      background-color: lightblue;
    }
    
    @property --end-angle {
      syntax: '<angle>';
      inherits: false;
      initial-value: 90deg;
    }
    
    .circle {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: conic-gradient(white 0deg var(--end-angle), transparent var(--end-angle) 360deg);
      mask: radial-gradient(farthest-side, transparent calc(100% - 10px), black calc(100% - 10px));
      -webkit-mask: radial-gradient(farthest-side, transparent calc(100% - 10px), black calc(100% - 10px));
      transition: --end-angle 0.7s ease;
      --end-angle: 90deg; /* 75% by default */
    }
    
    .circle:hover {
      --end-angle: 360deg; /* 100% on hover */
    }
    </style>
  </head>
  <body>
    <div class="circle"></div>
  </body>
</html>


