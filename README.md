<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Pixelify+Sans:wght@500&display=swap">
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Caveat&family=Croissant+One&family=Pacifico&family=Pixelify+Sans:wght@500&display=swap" rel="stylesheet">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Caveat&family=Croissant+One&family=Domine&family=Pacifico&family=Pixelify+Sans:wght@500&family=Satisfy&family=Young+Serif&display=swap" rel="stylesheet">



    <style>
      body {
        background-color: black;
      }
      
      .score {
        color: white;
        font-family: 'Pixelify Sans', cursive;

        text-align: center;
        font-size: 24px;
        margin-top: 10px;
      }

      .reset-button {
  /* Your existing styles */
  position: fixed;
  bottom: 20px;
  left: 20px;
  /*transform: translateX(-50%); */
  background-color: #AEDFF7;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease, text-shadow 0.3s ease;
  font-family: 'Pixelify Sans', cursive;
  font-size: 24px;
  color: white;
  text-shadow: 0 0 10px rgba(247, 190, 174, 1), 0 0 20px rgba(239, 74, 9, 1), 0 0 30px rgba(83, 17, 214, 1);
}

.reset-button:hover {
  transform: scale(1.1);
  box-shadow: 0 0 10px rgba(247, 190, 174, 1), 0 0 20px rgba(239, 74, 9, 1), 0 0 30px rgba(83, 17, 214, 1);
  text-shadow: 0 0 20px rgba(247, 190, 174, 1), 0 0 40px rgba(239, 74, 9, 1), 0 0 60px rgba(83, 17, 214, 1);
  background-color: darkred;
}



      .moto {
        color: white;
        font-family: 'Pixelify Sans', cursive;
        text-align: center;
        font-size: 55px;
        margin-top: 20px;
        padding: 50px;
      }

      .circularbox {
        display: flex;
        justify-content: space-around;
      }

      .rockimg, .paperimg1, .scissorimg2 {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: transparent;
      }

      .rockimg img, .paperimg1 img, .scissorimg2 img {
        max-width: 100%;
        height: auto;
        border-radius: 50%;
      }

      .reset-button {
        /* Your existing styles */
        position: absolute;
        bottom: 80px; /* Adjust this value to control the distance from the bottom */
        left: 640px;
        background-color: red;
        
      }

      /* Modal styles */
      .modal {
        display: none;
        position: fixed;
        z-index: 1;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        background-color: rgb(0,0,0);
        background-color: rgba(0,0,0,0.4);
        padding-top: 60px;
      }

      .modal-content {
        background-color: #fefefe;
        margin: 5% auto;
        padding: 20px;
        border: 1px solid #888;
        width: 80%;
      }

      .close {
        color: #aaa;
        float: right;
        font-size: 28px;
        font-weight: bold;
      }

      .close:hover,
      .close:focus {
        color: black;
        text-decoration: none;
        cursor: pointer;
      }






 
      #result {
        color: white;

        font-family: 'Caveat', cursive;
font-family: 'Croissant One', cursive;
font-family: 'Domine', serif;
font-family: 'Pacifico', cursive;
font-family: 'Pixelify Sans', cursive;
font-family: 'Satisfy', cursive;
font-family: 'Young Serif', serif;

        


        text-align: center;
        font-size: 30px;
        margin-top: 110px;
        opacity: 0; /* Initially set to be invisible */
        transition: opacity 1.5s ease; /* Transition effect */
        
      }

      .show-result {
        opacity: 1 !important; /* When the class is added, it makes the element visible */
      }

      .score {
        color: white;
        font-family: 'Caveat', cursive;
font-family: 'Croissant One', cursive;
font-family: 'Domine', serif;
font-family: 'Pacifico', cursive;
font-family: 'Pixelify Sans', cursive;
font-family: 'Satisfy', cursive;
font-family: 'Young Serif', serif;
        text-align: center;
        font-size: 24px;
        margin-top: 10px;
      }
      .rockimg:hover, .paperimg1:hover, .scissorimg2:hover {
        border: 2px solid green;
        animation: borderAnimation 1s infinite alternate;
      }

      @keyframes borderAnimation {
        0% {
          transform: scale(1);
        }
        100% {
          transform: scale(1.05);
        }
      }
      .rockimg, .paperimg1, .scissorimg2 {
        /* Your existing styles */
        box-shadow: 0 0 20px #FF6EC7;
        transition: box-shadow 0.5s ease-in-out;
      }

      .rockimg:hover, .paperimg1:hover, .scissorimg2:hover {
        box-shadow: 0 0 40px rgba(255, 174, 0, 1);
      }

      .rockimg:hover, .paperimg1:hover, .scissorimg2:hover {
    /* Your existing styles */
    cursor: pointer ;
  }




  .instructions-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background-color: #AEDFF7;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: transform 0.3s ease, box-shadow 0.3s ease, text-shadow 0.3s ease;
        font-family: 'Pixelify Sans', cursive;
        font-size: 16px;
        color: white;
        text-shadow: 0 0 10px rgba(247, 190, 174, 1), 0 0 20px rgba(239, 74, 9, 1), 0 0 30px rgba(83, 17, 214, 1);
      }

      .instructions-button:hover {
        transform: scale(1.1);
        box-shadow: 0 0 10px rgba(247, 190, 174, 1), 0 0 20px rgba(239, 74, 9, 1), 0 0 30px rgba(83, 17, 214, 1);
        text-shadow: 0 0 20px rgba(247, 190, 174, 1), 0 0 40px rgba(239, 74, 9, 1), 0 0 60px rgba(83, 17, 214, 1);
      }

      .instructions-popup {
        display: none;
        position: fixed;
        z-index: 1;
        right: 30px;
        bottom: 70px;
        background-color: #fefefe;
        border: 1px solid #888;
        width: 250px;
        padding: 10px;
        border-radius: 10px;
        font-family: 'Pixelify Sans', cursive;
        font-size: 14px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
      }

      .instructions-popup h2 {
        text-align: center;
      }

      .close-instructions {
        cursor: pointer;
        float: right;
      }

      .instructions-button{
        color: #000;
        padding: auto;
        margin: auto;
      }





      .moto {
    color: white;
    font-family: 'Pixelify Sans', cursive;
    text-align: center;
    font-size: 40px;
    margin-top: -3px;
    padding: 38px;
    animation: coolTransition 2s infinite;
}

@keyframes coolTransition {
    0% {
        transform: scale(1);
        opacity: 0.2;
    }
    50% {
        transform: scale(1.1);
        opacity: 1;
    }
    100% {
        transform: scale(1);
        opacity: 0.2;
    }
}


.moto.animate {
    animation: coolTransition 2s infinite;
}


      
      
    </style>
  </head>
  <body>
    <p class="moto">Rock - Paper - Scissors</p>
    <div class="circularbox">
      <button onclick="playGame('rock');" class="rockimg">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbfqswvfnF4LKEG0K_-ZsdVVmkk9f6giIWhOedQ9jpYUD4jQBvnyZlC2ryil0jOVqfrnA&usqp=CAU" alt="rock">
      </button>

      <button onclick="playGame('paper');" class="paperimg1">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQV99ddM7Uk0kbCyCX0qdz6ivTfl2R3mZLGv_F36YK6nV3DxPENFECO-a_HHThDGltkZ5Q&usqp=CAU" alt="paper">
      </button>

      <button onclick="playGame('scissors');" class="scissorimg2">
        <img src="https://www.seekpng.com/png/detail/111-1114370_rock-paper-scissors-rock-paper-scissors-clipart.png" alt="scissors">
      </button>
    </div>

    <div id="result" class="moto3"></div>

    <!-- Displaying the score -->
    <div id="score" class="score">Player: 0 | Computer: 0</div>

    <!-- Reset button -->
    <button onclick="resetGame()" class="reset-button">Reset Game</button>

        <!-- New div to display the result -->
        <div id="result" class="moto"></div>


          <!-- Modal content -->
    <div id="myModal" class="modal">
        <div class="modal-content">
          <span class="close" onclick="closeModal()">&times;</span>
          <div id="winnerResult"></div>
        </div>
      </div>
  
 <!-- Instructions Button -->
 <button class="instructions-button" onclick="toggleInstructions()">Instructions</button>

        <!-- Instructions Popup -->
    <div class="instructions-popup" id="instructionsPopup">
        <span class="close-instructions" onclick="toggleInstructions()">&times;</span>
        <h2>Instructions</h2>
        <ol>
            <li>Click on one of the buttons below to make your move.</li>
            <li>You can play a maximum of 10 rounds.</li>
            <li>The game will automatically end after 10 rounds.</li>
            <li>Each round, you and the computer will make a move.</li>
            <li>If you choose Rock and the computer chooses Scissors, you win the round.</li>
            <li>If you choose Paper and the computer chooses Rock, you win the round.</li>
            <li>If you choose Scissors and the computer chooses Paper, you win the round.</li>
            <li>The score is kept for both you and the computer on the top right.</li>
            <li>The game will determine the winner after 10 rounds.</li>
            <li>If you want to start a new game, click the 'Reset Game' button.</li>
          </ol>
      </div>



      

        <script>
            let playerScore = 0;
            let computerScore = 0;
            let roundsPlayed = 0;
      
            function playGame(playerMove) {
              if (roundsPlayed < 10) {
                const computerMove = pickComputerMove();
      
                let result = '';
      
                if (playerMove === 'scissors') {
                  if (computerMove === 'rock') {
                    result = 'You lose.';
                    computerScore++;
                  } else if (computerMove === 'paper') {
                    result = 'You win.';
                    playerScore++;
                  } else if (computerMove === 'scissors') {
                    result = 'Tie.';
                  }
                } else if (playerMove === 'paper') {
                  if (computerMove === 'rock') {
                    result = 'You win.';
                    playerScore++;
                  } else if (computerMove === 'paper') {
                    result = 'Tie.';
                  } else if (computerMove === 'scissors') {
                    result = 'You lose.';
                    computerScore++;
                  }
                } else if (playerMove === 'rock') {
                  if (computerMove === 'rock') {
                    result = 'Tie.';
                  } else if (computerMove === 'paper') {
                    result = 'You lose.';
                    computerScore++;
                  } else if (computerMove === 'scissors') {
                    result = 'You win.';
                    playerScore++;
                  }
                }
      
                roundsPlayed++;
      
                const resultElement = document.getElementById('result');
                resultElement.innerHTML = `You picked ${playerMove}. Computer picked ${computerMove}. ${result}`;
      
                // Update the score
                const scoreElement = document.getElementById('score');
                scoreElement.textContent = `Player: ${playerScore} | Computer: ${computerScore}`;
      
                if (roundsPlayed === 10) {
                  // Game over, determine the winner
                  if (playerScore > computerScore) {
                    resultElement.innerHTML += '<br>Player wins the game!';
                  } else if (playerScore < computerScore) {
                    resultElement.innerHTML += '<br>Computer wins the game!';
                  } else {
                    resultElement.innerHTML += '<br>It\'s a tie!';
                  }
                }
      
                // Resetting the transition effect
                resultElement.style.transition = 'none';
      
                // Force a reflow to apply the change
                void resultElement.offsetWidth;
      
                // Adding the class to trigger the transition effect after a short delay
                setTimeout(() => {
                  resultElement.style.transition = ''; // Resetting transition property
                  resultElement.classList.add('show-result');
                }, 100);
              }
            }
      
            function pickComputerMove() {
              const randomNumber = Math.random();
      
              let computerMove = '';
      
              if (randomNumber >= 0 && randomNumber < 1 / 3) {
                computerMove = 'rock';
              } else if (randomNumber >= 1 / 3 && randomNumber < 2 / 3) {
                computerMove = 'paper';
              } else if (randomNumber >= 2 / 3 && randomNumber < 1) {
                computerMove = 'scissors';
              }
      
              return computerMove;
            }
        // Function to reset the game
      function resetGame() {
        playerScore = 0;
        computerScore = 0;
        roundsPlayed = 0;
        const scoreElement = document.getElementById('score');
        scoreElement.textContent = `Player: 0 | Computer: 0`;

        const resultElement = document.getElementById('result');
        resultElement.innerHTML = '';
        resultElement.classList.remove('show-result');
      }


      function toggleInstructions() {
        const instructionsPopup = document.getElementById('instructionsPopup');
        instructionsPopup.style.display = (instructionsPopup.style.display === 'block') ? 'none' : 'block';
      }




      document.getElementById('gameTitle').classList.add('animate');
            
           </script>
  </body>
</html>
