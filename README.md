# uplift_b3_milestone_1
# Personal Expense Tracker — Write-Up

## What it does
This is a command-line Python program for logging personal expenses. The user
enters a description, amount, and category for each expense until they type
`done`. The program then prints a summary: total spent, a breakdown by
category, the highest and lowest expense, and a status message comparing the
total against a fixed monthly budget.

## How to run it
Open `Personal_Expense_Tracker.ipynb` in Jupyter and run all cells in order,
or run the plain script from a terminal:

```
python expense_tracker.py
```

The program expects three inputs per expense: a description (text), an
amount (a positive number, e.g. `12.50`), and a category (text, optional —
defaults to "Uncategorized"). Type `done` instead of a description to finish
and see the summary.

## A challenge I debugged
While testing in VS Code's Jupyter extension, I ran the self-test cell on
its own and got `NameError: name 'add_expense' is not defined`. The
traceback pointed straight to the `add_expense(...)` call, which was
confusing since the function was clearly defined earlier in the notebook.
Reading it more carefully, I realized Jupyter only knows about cells
you've actually executed in that session — I had run the self-test cell
without first running the cell above it that defines the functions. The
fix was restarting the kernel and running the cells top to bottom in
order, which cleared the confusion and let the functions load before
anything tried to call them.

A second, smaller snag: since the program uses `input()`, VS Code doesn't
show prompts inline in the notebook — they pop up as a small text box at
the top of the editor window, easy to miss on the first run. Once I knew
to look there, entering expenses worked as expected.

## A non-coding challenge
Beyond the code itself, the bigger challenge was mental: I'm coming from
Java, so I kept catching myself translating Python concepts back into
Java terms just to understand them. That approach only goes so far,
since not everything in Java has a direct Python equivalent — some
concepts work differently or don't exist at all. When a Python idea
didn't map cleanly onto what I already knew, I had to slow down and
research it on its own terms rather than forcing a Java comparison, to
understand what it was actually for.
