## project 4

# solution

''' javascripts

let randomNumber = parseInt(Math.random() * 100 + 1);
const submit = document.querySelector('#subt');
const userInput = document.querySelector('#guessField');
const guessSlot = document.querySelector('.guesses');
const remaining = document.querySelector('.lastResult');
const lowOrHi = document.querySelector('.lastResult');
const startOver = document.querySelector('.resultParas');

const p = document.createElement('p');

let prevGuess = [];
let numGueuss = 1;
let playGame = true;

if (playGame) {
  submit.addEventListener('click', function (e) {
    e.preventDefault();
    const guess = parseInt(userInput.value);
    validateGuess(guess);
  });
}

function validateGuess(guess) {
  if (isNaN(guess)) {
    alert('please enter valid number');
  } else if (guess < 1) {
    alert('please enter the number more then 1 .');
  } else if (guess > 100) {
    alert('please enter the number less than 100.');
  } else {
    prevGuess.push(guess);
    if (numGueuss === 11) {
      displayGuess(guess);
      displayMessege(`game over. Random number was ${randomNumber}`);
      endGame();
    } else {
      displayGuess(guess);
      checkGuess(guess);
    }
  }
}

function checkGuess(guess) {
  if (guess == randomNumber) {
    displayMessege('You guessed it right.');
    endGame();
  } else if (guess < randomNumber) {
    displayMessege('number is too low');
  } else if (guess > randomNumber) {
    displayMessege('number is too high');
  }
}

function displayGuess(guess) {
  userInput.value = '';
  guessSlot.innerHTML += `${guess}, `;
  numGueuss++;
  remaining.innerHTML = `${11 - numGueuss}`
}

function displayMessege(message) {
  lowOrHi.innerHTML = `<h2>${message}</h2>`;
}

function endGame() {
  userInput.value = '';
  userInput.setAttribute('disabled', '');
  p.classList.add('button');
  p.innerHTML = `<h2 id ="newGame">Start new game </h2>`;
  startOver.appendChild(p);
  playGame = false;
  newGame();
}

function newGame() {
  const newGameButton = document.querySelector('#newGame');
  newGameButton.addEventListener('click', function (e) {
    randomNumber = parseInt(Math.random() * 100 + 1);
    prevGuess = [];
    numGueuss = 1;
    guessSlot.innerHTML = '';
    remaining.innerHTML = `${11 - numGueuss}`;
    userInput.removeAttribute('disabled');
    startOver.removeChild(p);
    playGame = true;
  });
}
 '''