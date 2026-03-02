# 🎮 Game Glitch Investigator: The Impossible Guesser

Phase 1: Glitch Hunt (Spot Check)
Run the Streamlit game once and identify at least 4 bugs.
1. No matter what you guess, the feedback is always to "go lower"
2. There is no hard limit on number I guess. For example, it says to choose a number between 1 and 100, but it allows me to guess outside of that scope.
3. The attempts guessed do not reset properly. It seems the math logic is broken here.
   <img width="807" height="935" alt="image" src="https://github.com/user-attachments/assets/1d23a1f7-622f-4ae9-91e0-970fd0b4b08a" />
With the Developer Debug Info, I noticed: /n
-The attempts started at 0
-The “attempts left” display wasn't accurate
-It sometimes said “Out of attempts” while still showing 1 attempt left
4. The only functionality of the "New Game" button was just resetting the number. Evrything else remained, including the score, guess history, and attempt history.


Phase 2: Investigate & Repair (Assigned)
For this phase, you should:
• Fix 2 bugs end-to-end
 • Review at least one AI-generated edit (be skeptical!)
 • Generate pytest cases + run them successfully
 • Draft a short guiding hint you would give a student
 
1. Was able to fix the logic for the guessing. Now, if you guess too high or too low, the feedback to the player reflects accurately.
By updating the conditional checks to ensure the "Go Higher/Lower", it now prompts correctly to correspond to the user's input relative to the secret number.
<img width="1088" height="957" alt="image" src="https://github.com/user-attachments/assets/0d3cffaf-045f-43e8-962a-7cb9ccb435d0" />

2. Added helper function to enforce the number range in which a player can guess.
- Added is_within_range(guess, low, high) with documentation.
- Imported is_within_range
- Restructured guess submission:
- Parse the input
- Check against the range
- Only valid, in‑range guesses increase the attempt count and proceed to normal game flow
- Error message shown:
- Guess must be between {low} and {high}.
 <img width="1757" height="822" alt="image" src="https://github.com/user-attachments/assets/9bc41c2f-0903-43c3-afda-cf84bef9891d" />

 Hints:
 - Test the boundaries: Try guessing 1 or the highest number possible. Check if the "Higher/Lower" hints actually make sense at the extremes.
 - Toggle the difficulty: Switch between levels and see what changes.
 - Definetly use the Developer Debug section, it is meant exactly for debugging. Also, keep an eye on the session data to see if it updates correctly every time something is clicked.


Phase 3: Reflection & README (Review)
Just skim the reflection prompts and understand the expected depth of support.
No need to:
 • Write full reflections
 • Perfect the README

