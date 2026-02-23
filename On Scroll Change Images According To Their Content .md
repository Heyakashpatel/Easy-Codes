
```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scroll Sync Without Data Attributes</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}

body {
  background: #f3f3f3;
}

.wrapper {
  display: flex;
  max-width: 1400px;
  margin: auto;
}

/* LEFT SIDE */
.left {
  width: 50%;
}

.feature {
  height: 100vh;
  padding: 100px 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.feature h2 {
  font-size: 40px;
  margin-bottom: 20px;
}

.feature p {
  font-size: 18px;
  margin-bottom: 20px;
  color: #555;
}

.feature button {
  padding: 10px 20px;
  background: black;
  color: white;
  border: none;
  cursor: pointer;
}

/* RIGHT SIDE */
.right {
  width: 50%;
  height: 100vh;
  position: sticky;
  top: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: white;
}

.image-container {
  position: relative;
  width: 80%;
}

.image-container img {
  position: absolute;
  width: 100%;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.image-container img.active {
  opacity: 1;
}

/* Mobile */
@media(max-width: 900px){
  .wrapper {
    flex-direction: column;
  }
  .left, .right {
    width: 100%;
  }
  .right {
    position: relative;
    height: 400px;
  }
}
</style>
</head>
<body>

<div class="wrapper">

  <div class="left">
    <div class="feature">
      <h2>First Section</h2>
      <p>Scroll to change image.</p>
      <button>Learn More</button>
    </div>

    <div class="feature">
      <h2>Second Section</h2>
      <p>Image changes automatically.</p>
      <button>Learn More</button>
    </div>

    <div class="feature">
      <h2>Third Section</h2>
      <p>Only one image is visible.</p>
      <button>Learn More</button>
    </div>
  </div>

  <div class="right">
    <div class="image-container">
      <img src="https://picsum.photos/id/1015/800/600" class="active">
      <img src="https://picsum.photos/id/1016/800/600">
      <img src="https://picsum.photos/id/1018/800/600">
    </div>
  </div>

</div>

<script>
const sections = document.querySelectorAll('.feature');
const images = document.querySelectorAll('.image-container img');

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const index = [...sections].indexOf(entry.target);

      images.forEach(img => img.classList.remove('active'));

      if (images[index]) {
        images[index].classList.add('active');
      }
    }
  });
}, {
  threshold: 0.9
});

sections.forEach(section => observer.observe(section));
</script>

</body>
</html>
```
