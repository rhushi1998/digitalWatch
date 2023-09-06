# DigitalWatch

We will create a user-friendly digital clock that displays the current time on a website with a beautiful design, title, and background image. We'll get the current time from the computer and display it in a digital format using JavaScript, . The clock will always show the accurate time, synchronized with the computer's time. This project will help us learn crucial skills such as working with JavaScript to retrieve the current time and creating an attractive website design.

## Hosted Link
https://rhushi1998.github.io/digitalWatch/

## Code

### HTML

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digital Clock</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h2>Digital Clock</h2>
    <div class="clock">
      <div>
        <span id="hour">00</span>
        <span class="text">Hours</span>
      </div>
      <div>
        <span id="minutes">00</span>
        <span class="text">Minutes</span>
      </div>
      <div>
        <span id="seconds">00</span>
        <span class="text">Seconds</span>
      </div>
      <div>
        <span id="ampm">AM</span>
      </div>
    </div>
    <script src="index.js"></script>
  </body>
</html>

### JS
const hourEl = document.getElementById("hour");
const minuteEl = document.getElementById("minutes");
const secondEl = document.getElementById("seconds");
const ampmEl = document.getElementById("ampm");

function updateClock() {
  let h = new Date().getHours();
  let m = new Date().getMinutes();
  let s = new Date().getSeconds();
  let ampm = "AM";

  if (h > 12) {
    h = h - 12;
    ampm = "PM";
  }

  h = h < 10 ? "0" + h : h;
  m = m < 10 ? "0" + m : m;
  s = s < 10 ? "0" + s : s;

  hourEl.innerText = h;
  minuteEl.innerText = m;
  secondEl.innerText = s;
  ampmEl.innerText = ampm;
  setTimeout(() => {
    updateClock();
  }, 1000);
}

updateClock();
