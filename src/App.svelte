<script>
  let counterblue = 10;
  let counterred = 10; 
  let winningPlayer; 

  let displayWin = 'hidden';

  function incrementBlue(e) {
    counterblue += 1;
  }

  function incrementRed(e) {
    counterred += 1; 
  }

  function decrementBlue(e) {
    if (counterblue > 0) {
      counterblue -= 1;
    } else {
      displayWin='visible';
      winningPlayer='Blue';
      counterblue = 10;
      counterred = 10; 
    }
  }

  function decrementRed(e) {
    if (counterred > 0) {
      counterred -= 1;
    } else {
      displayWin='visible';
      winningPlayer='Red';
      counterblue = 10;
      counterred = 10; 
    }
  }

</script>

<div id="gamearea">
  <h1>MTG Counter App</h1>
  <div id="teamarea">
    <div id="teambluearea">
      <h2>Team Blue: <span class="highlightblue">{counterblue}</span></h2>
      <div id="buttonarea">
        <button id="increment" on:click={incrementBlue}>+</button>
        <button id="decrement" on:click={decrementBlue}>-</button>
      </div>
    </div>
    <div id="teamredarea">
      <h2>Team Red: <span class="highlightred">{counterred}</span></h2>
      <div id="buttonarea">
        <button id="increment" on:click={incrementRed}>+</button>
        <button id="decrement" on:click={decrementRed}>-</button>
      </div>
    </div>
  </div>

  <div style="visibility:{displayWin}">
    <h2>{winningPlayer} Wins!</h2>
  </div>

</div>

<style>
#gamearea {
  display: flex; 
  justify-content: center; 
  flex-direction: column; 
  align-items: center; 
}

#teambluearea {
  display: flex; 
  flex-direction: column; 
  align-items: center; 
  margin: 30px; 
  padding: 50px; 
  background: #ffff;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
}

#teamredarea {
  display: flex;
  flex-direction: column; 
  align-items: center; 
  margin: 30px; 
  padding: 50px; 
  border-radius: 5px;
  background: #ffff;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
}

#buttonarea {
  display: flex;
  justify-content: space-evenly; 
  width: 70%; 
}


#teamarea {
  display: flex; 
}

#increment:hover {
  background-color: rgb(94, 204, 94);
}

#decrement:hover {
  background-color: rgb(238, 97, 97); 
}

.highlightred{
  background: rgb(238, 97, 97);
}

.highlightblue{
  background: lightblue; 
  box-shadow: 1px 5px white inset;
}

</style>

