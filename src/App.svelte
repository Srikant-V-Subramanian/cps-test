<script>
  let clicks = 0;

  let cps = 0;

  let timer = 15;

  function changeTimer() {
    timer--;
  }

  // calls increment() when button is clicked => start timer when clicks == 0
  function increment() {
    if (timer == 0) {
      clearInterval(resetTimer);
    }

    if (clicks == 0) {
      var resetTimer = setInterval(changeTimer, 1000);
      setTimeout(function () {
        cps = clicks / 15;
        console.log(cps);
        console.log(clicks);
      }, 15000);
    }
    clicks++;
  }
</script>

<main>
  <h1>CPS TEST</h1>
  <button on:click={increment}>Click this button.</button>
  <p>Clicks : {clicks}</p>
  <p>CPS : {cps}</p>
  <p>Timer : {timer}</p>
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  main {
    font-family: "Roboto", sans-serif;
  }
</style>
