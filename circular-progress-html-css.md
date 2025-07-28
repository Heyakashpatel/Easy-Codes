```html
<head>
<title>Page Title</title>
<style>
.circular-css {
  width: 80px;
  height:80px;
  border-radius: 50%;
  background: conic-gradient(red 40%, #eee 0);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.inner-circle {
  width: 60px;
  height: 60px;
  background-color: white; /* Matches page background for "hollow" effect */
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
}

.value {
  font-size: 18px;
  font-weight: bold;
  color: red;
}


</style>
</head>
<body>

<div class="circular-css">
  <div class="inner-circle">
    <div class="value">40%</div>
  </div>
</div>


</body>
</html>
