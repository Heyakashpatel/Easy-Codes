```html 



<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

.container {
  width: 100%;
  margin: 40px auto;
}

.row {
  margin-bottom: 0;
}

/* track */
.bar-track {
  width: 100%;
  height: 100%;
  position: relative;
}

/* bar */
.bar {
  height: 65px !important;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
  box-sizing: border-box;
  transition: width 0.6s ease;
  overflow: hidden;
  min-width: fit-content;
  flex-wrap: wrap;
}

/* label */
.label-box {
  background: #fff;
  color: #404040;
  padding: 6px 10px;
  font-size: 13px;
  white-space: nowrap;
  flex-shrink: 0;
  width: fit-content;
}

/* value */
.value {
  color: #fff;
  font-weight: 700;
  font-size: 23px;
  flex-shrink: 0;
}
</style>
</head>

<body>

<div class="container" id="barchart"></div>
<div class="container" id="barchart2"></div>

<script>
function createBarChart(
  containerId,
  labels,
  values,
  barColor,
  trackColor,
  barShadow,
  trackShadow
) {
  const container = document.getElementById(containerId);
  const items = [];

  labels.forEach((label, i) => {
    const row = document.createElement("div");
    row.className = "row";

    const track = document.createElement("div");
    track.className = "bar-track";
    track.style.background = trackColor;
    track.style.boxShadow = trackShadow;

    const bar = document.createElement("div");
    bar.className = "bar";
    bar.style.background = barColor;
    bar.style.boxShadow = barShadow;

    const labelBox = document.createElement("div");
    labelBox.className = "label-box";
    labelBox.textContent = label;

    const valueText = document.createElement("div");
    valueText.className = "value";
    valueText.textContent = values[i] + "%";

    bar.appendChild(labelBox);
    bar.appendChild(valueText);

    track.appendChild(bar);
    row.appendChild(track);
    container.appendChild(row);

    bar.style.width = values[i] + "%";

    items.push({ track, bar, labelBox, valueText });
  });

  function updateLayout() {
    items.forEach(({ track, bar, labelBox, valueText }) => {

      const barWidth = bar.getBoundingClientRect().width;
      const labelWidth = labelBox.getBoundingClientRect().width;
      const valueWidth = valueText.getBoundingClientRect().width;

      const neededWidth = labelWidth + valueWidth + 30;

      const shouldMoveOut = neededWidth > barWidth;

      if (shouldMoveOut) {
        if (labelBox.parentElement === bar) {
          track.insertBefore(labelBox, bar);
        }
      } else {
        if (labelBox.parentElement === track) {
          bar.insertBefore(labelBox, valueText);
        }
      }
    });
  }

  window.addEventListener("resize", updateLayout);
  setTimeout(updateLayout, 100);
}

/* DATA */
const labels = [
  "Much more prepared",
  "More prepared",
  "About the same",
  "Less prepared"
];

const values = [16.09, 22.99, 31.09, 26.09];

/* CHART 1 */
createBarChart(
  "barchart",
  labels,
  values,
  "#921F65",
  "#F2EAEF",
  "0px 4px 8px 0px #C6489599 inset",
  "0px 4px 8px 0px #F5DAEA inset"
);


/* DATA 2 */
const labels2 = [
  "Much more prepared",
  "More prepared",
  "About the same",
  "Less prepared"
];

const values2 = [16.09, 22.99, 31.09, 18.09];

/* CHART 2 */
createBarChart(
  "barchart2",
  labels2,
  values2,
  "#8976FF",  // bar color
  "#EAE7FF",  // track background
  "0px 4px 8px 0px #DBD6FFB2 inset", // bar shadow
  "0px 4px 8px 0px #DDD8FFB2 inset"     // track shadow (or your choice)
);

</script>

</body>
</html>
