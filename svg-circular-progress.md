```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
<style>
.circular-progress {
  width: 80px;
  height: 80px;
}

.progress-ring {
  width: 100%;
  height: 100%;
  transform: rotate(360deg);
}

.circle-bg {
  fill: none;
  stroke: #eee;
  stroke-width: 3;
}

.circle {
  fill: none;
  stroke: red;
  stroke-width: 3;
  stroke-linecap: round;
  stroke-dasharray: 80, 100;
  transition: stroke-dasharray 0.6s ease;
}

.percentage {
  fill: black;
  font-size: 0.5em;
  text-anchor: middle;
  dominant-baseline: middle;
}

</style>
</head>
<body>

<div class="circular-progress">
  <svg viewBox="0 0 36 36" class="progress-ring">
    <path class="circle-bg"
          d="M18 2.0845
             a 15.9155 15.9155 0 0 1 0 31.831
             a 15.9155 15.9155 0 0 1 0 -31.831" />
    <path class="circle"
          stroke-dasharray="60, 100"
          d="M18 2.0845
             a 15.9155 15.9155 0 0 1 0 31.831
             a 15.9155 15.9155 0 0 1 0 -31.831" />
    <text x="18" y="20.35" class="percentage">60%</text>
  </svg>
</div>


</body>
</html>
