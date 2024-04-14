<script>
  let currentQuestion = "Press a button to start 🚀";
  let lastQuestions = {
    general: null,
    interview: null,
    strange: null
  };

  const questions = {
	general: [
		"What is your favorite color?",
		"What kind of music do you like?",
		"Where is your favorite place to unwind?",
		"What’s your favorite way to spend a weekend?",
		"What type of books do you like to read?",
		"Who is your favorite author?",
		"What’s the best movie you've seen this year?",
		"What are your hobbies?",
		"What’s your favorite restaurant?",
		"Do you prefer mountains or oceans?",
		"What was the best vacation you've ever had?",
		"What’s the last thing you cooked or baked?",
		"Do you have any pets? Tell me about them.",
		"What’s your favorite holiday tradition?",
		"What is one thing you can’t live without?",
		"What’s your favorite app on your phone?",
		"What kind of sports do you enjoy watching or playing?",
		"What’s a skill you’d like to learn and why?",
		"Who has inspired you in your life?",
		"What’s one city you would like to visit?"
	],
	// ref: https://www.indeed.com/career-advice/interviewing/top-20-interview-questions
    interview: [
		"Tell me about yourself.",
		"Why are you interested in our company?",
		"Why are you interested in this position?",
		"What are your strengths?",
		"What are your weaknesses?",
		"Why did you leave your last job?",
		"How do you prioritize your work?",
		"Describe how you deal with conflict in the workplace.",
		"What's your preferred work environment/leadership style?",
		"Why should we hire you over other qualified candidates?",
		"Why are you looking for a new role?",
		"How do you stay motivated?",
		"How do you learn a new skill or technology?",
		"How do you manage your stress levels?",
		"Where do you hope to see yourself in five years?",
		"What is your leadership style?",
		"Describe a workplace challenge and how you overcame it.",
		"Tell me about a time you disagreed with a supervisor.",
		"Tell me about a time you failed.",
		"What questions do you have for us?"
    ],
	strange: [
		"If you could be any animal, what would you be?",
		"What's the weirdest dream you've ever had?",
		"If you were a fruit, which one would you be and why?",
		"What's the strangest food you've ever eaten?",
		"If you had to wear one color for the rest of your life, what would it be and why?",
		"If you could only use one emoji for the rest of your life, which one would it be?",
		"What song would play every time you entered a room?",
		"If you could talk to one species of animal, which would you choose and why?",
		"What would be the worst buy-one-get-one-free sale of all time?",
		"If you could instantly become an expert in something, what would it be and why?",
		"If you could change your first name, what would you change it to?",
		"If you could be a character in any movie, who would you be?",
		"What’s the most unusual place you’ve ever visited?",
		"If you had to eat only one food for the rest of your life, what would it be?",
		"If you could have dinner with any fictional character, who would it be?",
		"What is the most useless fact you know?",
		"If you were reincarnated as an ice cream flavor, which would you be?",
		"What is something that everyone looks stupid doing?",
		"If you were the world leader for a day, what would be your first rule?",
		"If you could have any mythical creature as a pet, what would you choose?"
	]
  };

  function askQuestion(category) {
    let possibleQuestions = questions[category].filter(q => q !== lastQuestions[category]);
    if (possibleQuestions.length === 0) {
      // 全ての質問が既に使われた場合は、再度リセット
      possibleQuestions = questions[category];
    }
    const randomIndex = Math.floor(Math.random() * possibleQuestions.length);
    currentQuestion = possibleQuestions[randomIndex];
    lastQuestions[category] = currentQuestion;
  }
</script>

<div class="container">
  <button class="button" on:click={() => askQuestion('general')}>General</button>
  <button class="button" on:click={() => askQuestion('interview')}>Interview</button>
  <button class="button" on:click={() => askQuestion('strange')}>Strange</button>
  <div class="question">{currentQuestion}</div>
</div>
