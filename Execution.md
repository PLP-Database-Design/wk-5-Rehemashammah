**ID: TC-01**

**Feature: Reset Game**

**Objective: Verify full reset clears all game data**

**Steps:**

Start a game and solve 3 puzzles to earn points and a bonus.

Click the Reset Game button.

Observe the score, solved count, and bonus counter.

**Expected Result:**

Score, solved count, and bonus all reset to 0.

UI returns to initial state.

**Actual Result:**

Score and solved count reset correctly, bonus remains 3.

Status: ❌ Fail
Risk Priority: High (R1)

**ID: TC-02**

**Feature: Reset Game**

**Objective: Ensure reset action requires user confirmation**

**Steps:**

Begin a new game and make partial progress.

Click the Reset Game button.

**Expected Result:**

A confirmation message (e.g., “Are you sure?”) should appear before reset.

**Actual Result:**

Game resets instantly without confirmation.

Status: ❌ Fail
Risk Priority: High (R2)

**ID: TC-03**

**Feature: Leaderboard**

**Objective: Verify top-3 sorting logic**

**Steps:**

Achieve scores 5, 12, and 8 in separate game rounds.

Open the Leaderboard section.

**Expected Result:**

Scores appear sorted in descending order (12, 8, 5).

**Actual Result:**

Sorted correctly.

Status: ✅ Pass
Risk Priority: High (R3)

**ID: TC-04**

**Feature: Leaderboard**

**Objective: Leaderboard data not persistent data on different browsers**

**Steps:**
 Play and achieve a score of 10.
 Check that the leaderboard shows your score.
 Refresh the browser window
 Try playing the game on a different browser.
  Check the leaderboard of both browsers

**Expected Result:**

Leaderboard of highest scorer should be the same on any browser

**Actual Result:**

Each browser has different leaderboard scores.

Status: ❌ Fail
Risk Priority: Critical (R4)

**ID: TC-05**

Feature: Bonus Round
Objective: Validate doubling of score on every 3rd puzzle

**Steps:**

Solve 2 puzzles normally.

Solve the 3rd puzzle.

**Expected Result:**

Score for 3rd puzzle should be doubled (×2).

**Actual Result:**

Works correctly.

Status: ✅ Pass
Risk Priority: Medium (R5)

**ID: TC-06**

**Feature: Bonus Round**

**Objective: Confirm bonus triggers only on every 3rd puzzle**

**Steps:**

Solve puzzles 1–6 sequentially.

Observe when the bonus is applied.

**Expected Result:**

Bonus applies only on puzzles 3 and 6.

**Actual Result:**

Works correctly.

Status: ✅ Pass
Risk Priority: Medium (R6)

**ID: TC-07 (Negative Test 1)**

**Feature: Reset Game**

**Objective: Ensure reset mid-game does not crash the game**

**Steps:**

Begin a new puzzle.

Before finishing, click Reset Game.

**Expected Result:**

Game resets safely without errors or freezing.

**Actual Result:**

Works fine; no crashes.

Status: ✅ Pass
Risk Priority: High (R1)

**ID: TC-08 (Negative Test 2)**

**Feature: Leaderboard Input Validation**

**Objective: Ensure invalid or empty scores are not stored**

**Steps:**

Manipulate browser console or game to enter an empty value.

Check if it accepts the empty string.

**Expected Result:**

Empty string should give you an error message. i.e., "Please enter a guess!".

**Actual Result:**

Empty Strings are not stored.

Status: ✅ Pass
Risk Priority: Medium (R4)

**ID: TC-09 (Usability Test)**

**Feature: User Interface**

**Objective: Validate button visibility, clarity, and labeling**

**Steps:**

Observe all game buttons — Start, Reset, Leaderboard, Submit Answer.

Check label clarity and visual contrast.

**Expected Result:**

Buttons are clear, visible, and readable.

Color contrast and size are appropriate.

**Actual Result:**

Buttons are clear and labeled correctly.

Status: ✅ Pass
Risk Priority: Low