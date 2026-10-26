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

After the restart, what did the program remember? 
It remembered what attempt I was on.

Which file made that possible? 
The file 'dataman_store.json'.

## Part 3. The interface change [S1]

What did you change in `app.py`? 
The text outputted when an answer is incorrect.

Why did no test need to change? 
The test isnt looking for the print statement itself, only that the code corresponding to the process itself is working accordingly.

## Part 4. The rule in the real library [S2]

The same 10-problem rule exists in the real library. Write the file and the function name. 
dataman/logic.py, add_problem()

Break on purpose: I dont think any tests will fail, but we will be allowed to add an 11th problem, which shouldn't happen.

## Part 5. The red test [S2]

With the rule removed from the library, what did the screen show?
This was shown:

def test_eleventh_problem_is_refused():
        bank = MemoryBank(MemoryStore(), "set-1")
        for i in range(1, 11):
            bank.add_problem(f"P{i}")
>       with pytest.raises(SetFull):
             ^^^^^^^^^^^^^^^^^^^^^^
E       Failed: DID NOT RAISE <class 'dataman.logic.SetFull'>
'''

tests/test_logic.py:59: Failed

With the rule removed, which test failed? 
test_eleventh_problem_is_refused()

## Part 6. The data swap [S2]

A real database would replace which file? 
dataman_store.json

Which file holds the rules and does not change when the database changes? 
logic.py holds the rules.

## Reflection [S2]

Write 3 to 5 sentences. Pick one layer. Say what you changed in it. Say what stayed the same in the other two layers.

In the interface (dataman/app.py), I changed what was displayed when you got an answer incorrect, and nothing else.
For the logic layer (logic.py), nothing was changed. We tested what changing some rules would do, but did not save those changes.
And finally, no changes were made in the data layer (dataman/store.py)

## Beta feedback (optional)

This bonus is a beta test. Which step took longer than its time? What confused you? Write it here. Your answer helps the next class.

I feel like some of the instructions could be laid out a bit different. Instead of the instructions being in sentences laid out one after another, they could be bullet points instead? After I understoon how they were bign presented I had no difficulty reading through, but initially I was a bit hesistant to start on the assignment on my own. 

I really like the checks left after every section, they help a lot when it comes to making sure I have everything done.
