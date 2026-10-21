# NOTES: Three Layers

Your name: Elijah Dixon

Fill each TODO. Write plain, short sentences. Do not delete the headings.

*Note: The built in copilot was used to fill section 1 (following how it was used in class). The model was set to 'Auto', and was optimized for balance.

## Part 1. Predict, then find [S1]

Write your prediction before you open any code. Then search. In the last column, write each file the search finds and what that file does.

| Action | Search word | My prediction (file) | Files found and what each does |
|---|---|---|---|
| Prints "Not yet. Try again." | `Not yet` | `app.py` | `app.py` prints the retry message when the answer is incorrect but another try remains. |
| Decides that the second miss shows the answer | `reveal` | `dataman/logic.py` | `app.py` displays the revealed answer; `dataman/logic.py` decides to reveal it; `tests/test_logic.py` checks that outcome. |
| Saves one attempt | `save_attempt` | `dataman/logic.py` | `dataman/logic.py` calls `save_attempt`; `dataman/store.py` defines it for memory and JSON storage. |
| Refuses the 11th problem | `SetFull` | `dataman/logic.py` | `app.py` catches `SetFull`; `dataman/logic.py` raises it at the size limit; `exercise/bank.py` defines it for the exercise; `exercise/test_bank.py` and `tests/test_logic.py` test the refusal. |

Search command: `grep -rn "SEARCH WORD" --include=*.py .`

## Part 2. What the program remembered [S1]

After the restart, what did the program remember? It remembered what attempt I was on.

Which file made that possible? The file 'dataman_store.json'.

## Part 3. The interface change [S1]

What did you change in `app.py`? The text outputted when an answer is incorrect.

Why did no test need to change? The test isnt looking for the text itself, only that the code corresponding to the process itself is working (eg. the status)

## Part 4. The rule in the real library [S2]

The same 10-problem rule exists in the real library. Write the file and the function name. TODO

## Part 5. The red test [S2]

With the rule removed from the library, what did the screen show? TODO

With the rule removed, which test failed? TODO

## Part 6. The data swap [S2]

A real database would replace which file? TODO

Which file holds the rules and does not change when the database changes? TODO

## Reflection [S2]

Write 3 to 5 sentences. Pick one layer. Say what you changed in it. Say what stayed the same in the other two layers. TODO

## Beta feedback (optional)

This bonus is a beta test. Which step took longer than its time? What confused you? Write it here. Your answer helps the next class.
