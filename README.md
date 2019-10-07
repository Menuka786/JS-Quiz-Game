# JS-Quiz-Game
A multiple choice quiz game about (mostly) JavaScript.

## Description
This is a JavaScript quiz game presented in a multiple choice question format. It consists of a landing page which prompts the user to start the game or view the high scores list, and when the game begins they must answer all the questions within the time limit, which changes dynamically based on how many questions are in the set. Questions answered incorrectly will incur a time penalty. 

When the last question is answered, or when time runs out, the player will be taken to a submission page where they can enter their initials. When submitted, a high score chart is updated and saved locally, and the player is taken to a page showing all the scores logged on their PC. The player can choose to clear the high scores list from this page.


## Challenges
For this project I wanted to make sure I understood the new topics covered in class. This involved using many of the functions and methods we covered last week and this week. Before beginning any of the major JavaScript parts, I wanted to begin styling my page by using Bootstrap and CSS animations. While attaching the animations to Javascript to allow them to play wasn't an issue at first, switching between animations for the main question div provided my first roadblock. This issue was quickly resolved by removing the animation set from the question's main styling, and instead calling each separate animation using className in JavaScript when I wanted it.

While I was applying functionality to the buttons on the page, I ran into my second issue. The correct animation for the quiz block wasn't playing at the start of the game. I found out this was because the click event was propagating and activating another function that was not meant to be called when the game starts, so adding a stopPropagation function to the function I wanted allowed the proper animation to play.

Another issue I ran into was in the answer checking function. My idea for the script was to have it pull the answer value from the questions array after the player made their choice, but what it did was return the answer of the question after it! I found that I needed to apply my global index, questionNum after the check and before the next question was called in order to get the correct value. 