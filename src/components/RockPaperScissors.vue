<template>
    
<section id="RockPaperSciccorsContainer">

    <h1>Beat the Computer At Rock, Paper, Scissors!</h1>

  <div id="ButtonContainer">

    <div class="thumbnail-title">
      <h5>Choose Rock!</h5>

      <button @click="choose('rock')">
      <figure>
          <img class="thumbnail" src="../assets/img/rock.png">
      </figure>
      </button>
    </div>

  <div class="thumbnail-title">
    <h5 class="thumbnail-title">Choose Paper!</h5>
 
    <button @click="choose('paper')">
        <figure>
          <img class="thumbnail" src="../assets/img/paper.png">
      </figure>
    </button>
    </div>

  <div class="thumbnail-title">
    <h5 class="thumbnail-title">Choose Scissors!</h5>
    <button @click="choose('scissors')">
         <figure>
          <img class="thumbnail" src="../assets/img/scissors.png">
      </figure>
    </button>
    </div>
  </div>

  <h3 class="score">{{ userScore }} - {{ computerScore }}</h3>

</section>

</template>

<script>
export default {
    name: 'RockPaperSciccors',
    data () {
        return {
            userPick: null,
            randPick: null,
            userScore: 0,
            computerScore: 0,
    };
  },
  methods: {
    choose: function (pick) {
      this.userPick = pick;
      const picks = ['rock', 'paper', 'scissors'];
      this.randPick = picks[Math.floor(Math.random() * picks.length)];
      this.determineWinner();
    },
    determineWinner: function () {
      if (this.userPick == 'rock') {
        if (this.randPick == 'paper') {
          console.log('Computer wins');
          alert('Computer wins');
          this.computerScore++;
        } else if (this.randPick == 'scissors') {
          console.log('User wins');
          alert('User wins');
          this.userScore++;
        } else {
          console.log('Draw');
          alert('Draw');
        }
      } else if (this.userPick == 'paper') {
        if (this.randPick == 'rock') {
          console.log('User wins');
          alert('User wins');
          this.userScore++;
        } else if (this.randPick == 'scissors') {
          console.log('Computer wins');
          alert('Computer wins');
          this.computerScore++;
        } else {
          console.log('Draw');
          alert('Draw');
        }
      } else {
        if (this.randPick == 'rock') {
          console.log('Computer wins');
          alert('Computer wins');
          this.computerScore++;
        } else if (this.randPick == 'paper') {
          console.log('User wins');
          alert('User wins');
          this.userScore++;
        } else {
          console.log('Draw');
          alert('Draw');
        }
      }
    }
  },
  computed: {
    computedUser: function () {
      return {
        "first-round": this.userPick === null,
        "rock": this.userPick === "rock",
        "paper": this.userPick === "paper",
        "scissors": this.userPick === "scissors"
      };
    },
    computedRand: function () {
      return {
        "first-round": this.randPick === null,
        "rock": this.randPick === "rock",
        "hand": this.randPick === "paper",
        "scissors": this.randPick === "scissors"
      };
    }
  }
};
</script>

<style>
#RockPaperSciccorsContainer {
  height: 100vh;
  display: flex;
  flex-direction: column;
  max-width: 300px;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  font-family: "Open Sans", sans-serif;
  
}

.thumbnail  {

    height: 150px;
    width: auto;
}

#ButtonContainer  {
    display: flex;
    flex-direction: row;
}

.thumbnail-title  {
    display: flex;
    flex-direction: column;
    margin-left: 10px;
}

.score  {
  font-size: 2rem;
}


</style>