<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Countdown Timer</title>
</head>
<body>
  <h1>Countdown Timer</h1>
  <button onclick="startCountdown(10)">Start Countdown</button>
  <div id="timer"></div>

  <script>
    function startCountdown(time_sec) {
      var timerElement = document.getElementById("timer");
      var interval = setInterval(function() {
        if (time_sec === 0) {
          clearInterval(interval);
          timerElement.textContent = "Stop";
          return;
        }
        var mins = Math.floor(time_sec / 60);
        var secs = time_sec % 60;
        var timeformat = mins.toString().padStart(2, '0') + ':' + secs.toString().padStart(2, '0');
        timerElement.textContent = timeformat;
        time_sec--;
      }, 1000);
    }
  </script>
</body>
</html>
