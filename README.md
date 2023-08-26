<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Naruto Shippuden</title>
<style>
 /* Réinitialisation des styles de base */
body, h1, p, button {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

body {
  background-color: #f0f0f0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

#question-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
}

.btn {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  padding: 10px 20px;
  margin: 5px;
  cursor: pointer;
}

.btn:hover {
  background-color: #0056b3;
}

#next-button {
  display: none;
}

.hide {
  display: none;
}

.disabled {
  pointer-events: none;
  opacity: 0.6;
}

</style>
</head>
<body>
  <header>
    <h1>Quiz Naruto</h1>
  </header>
  <main>
    <div id="question-container">
      <p id="question">Question ici...</p>
      <div id="answer-buttons" class="btn-container">
        <button class="btn">Réponse 1</button>
        <button class="btn">Réponse 2</button>
        <button class="btn">Réponse 3</button>
        <button class="btn">Réponse 4</button>
      </div>
    </div>
    <button id="next-button" class="btn">Suivant</button>
  </main>
  <footer>
    /* Réinitialisation des styles de base */
    body, h1, p, button {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }
    
    body {
      background-color: #f0f0f0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    
    #question-container {
      background-color: #fff;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      padding: 20px;
      text-align: center;
    }
    
    .btn {
      background-color: #007bff;
      color: #fff;
      border: none;
      border-radius: 4px;
      padding: 10px 20px;
      margin: 5px;
      cursor: pointer;
    }
    
    .btn:hover {
      background-color: #0056b3;
    }
    
    #next-button {
      display: none;
    }
    
    .hide {
      display: none;
    }
    
    .disabled {
      pointer-events: none;
      opacity: 0.6;
    }
        
  </footer>
  <script>
    const questions = [
  {
    question: "Comment est mort Tobirama ?",
    answers: [
      { text: "Contre des brigants tres forts", correct: true },
      { text: "En se faisant poignarder par Danzô", correct: false },
      { text: "Le village de Konoha à fait une rébélion contre lui", correct: false },
      { text: "Contre Madara", correct: false }
    ]
  },
  {
    question: "Quel est le vrai nom de Yamato ?",
    answers: [
      { text: "Yamato", correct: false },
      { text: "Tenzô", correct: true },
      { text: "Tanzo", correct: false },
      { text: "Yamito", correct: false }
    ]
  },
  {
    question: "Qui est l'Hokage 4ème du nom ?",
    answer: [
        { text: "Tsunade", correct: false },
        { text: "Minato", correct: true },
        { text: "Hiruzen", correct: false },
        { text: "Hashirama", correct: false },
  },
  {
    question: "Quel est le vrai nom de Kyuubi ?"
    answer: [
        { text: "Kurama", correct: true },
        { text: "Matatabi", correct: false },
        { text: "Gyuki", correct: false },
        { text: "Saiken", correct: false },

  },
  {
    question: "Quel est le nom de la Mizukage n°4 ?"
    answer: [
    { text: "Mai Terumi", correct: false },
    { text: "Mei Tarumi", correct: false },
    { text: "Mei Teruashi", correct: false },
    { text: "Mei Terumi", correct: true },
];

const questionContainer = document.getElementById("question-container");
const questionElement = document.getElementById("question");
const answerButtons = document.getElementById("answer-buttons");
const nextButton = document.getElementById("next-button");

let currentQuestionIndex = 0;

function showQuestion(question) {
  questionElement.innerText = question.question;
  answerButtons.innerHTML = "";
  question.answers.forEach(answer => {
    const button = document.createElement("button");
    button.innerText = answer.text;
    button.classList.add("btn");
    button.addEventListener("click", () => selectAnswer(answer));
    answerButtons.appendChild(button);
  });
}

function selectAnswer(answer) {
  const isCorrect = answer.correct;
  if (isCorrect) {
    // Ajoutez ici le code pour gérer la réponse correcte
  }
  nextButton.classList.remove("hide");
  answerButtons.classList.add("disabled");
}

function nextQuestion() {
  currentQuestionIndex++;
  if (currentQuestionIndex < questions.length) {
    showQuestion(questions[currentQuestionIndex]);
    nextButton.classList.add("hide");
    answerButtons.classList.remove("disabled");
  } else {
    // Toutes les questions ont été posées, vous pouvez gérer le résultat final ici
  }
}

nextButton.addEventListener("click", nextQuestion);

showQuestion(questions[currentQuestionIndex]);

  </script>
</body>
</html>
