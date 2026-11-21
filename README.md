# Expense Tracker (Python)

A command-line expense tracker built in three stages, from a plain script to a class-based
program with persistent storage. Each version lives in its own folder, so you can read the code
and see how the project evolved as my Python skills grew.

## Project structure

```
expense-tracker/
├── README.md
├── .gitignore
├── v1/
│   ├── README.md
│   └── expensetrackerv1.py      # Procedural script (lists + dictionaries)
├── v2/
│   ├── README.md
│   └── expensetrackerv2.py      # Refactored into functions
└── v3/
    ├── README.md
    └── expenseversion3.py       # OOP + JSON persistence + exception handling
```

## Versions at a glance

| Version | Approach | Data persists? | Input error handling? |
|---------|----------|----------------|-----------------------|
| [v1](./v1) | Single script, list of dictionaries, list comprehensions | No | No |
| [v2](./v2) | Modular functions, shared `print_expense()` helper, generic search | No | No |
| [v3](./v3) | `Expense` and `ExpenseTracker` classes, JSON file storage | Yes (`expenses.json`) | Yes (`try`/`except`) |

## Features (all versions)

- Add an expense (id, amount, category, description, date)
- View all expenses
- Delete an expense by id
- View the most recently deleted expense
- Edit an expense (amount, category, description, or date)
- Search by id, category, or description
- Monthly spending summary (filter by `MM-YYYY`)
- Exit

## Getting started

**Requirements:** Python 3.6 or newer. No external libraries are needed.

```bash
# Clone the repository
git clone https://github.com/<your-username>/expense-tracker.git
cd expense-tracker

# Run any version
python v1/expensetrackerv1.py
python v2/expensetrackerv2.py
python v3/expenseversion3.py      # recommended, saves your data
```

On macOS/Linux you may need to use `python3` instead of `python`.

Each program shows a numbered menu (1-8). Type the number of the action you want and follow the
prompts. Dates should be entered as `DD-MM-YYYY` or any format that contains the `MM-YYYY` part
(for example `15-11-2026`), since the monthly summary matches on that text.

## Example session (v3)

```
1. Add expense
2. View expense
...
Enter your choice:1
Enter Id:1
Enter amount:250
Enter category:Food
Enter description:Lunch
Enter date:15-11-2026
Your expense is added
Saved!
```

## Concepts practiced

- **v1:** control flow, dictionaries, list comprehensions, `next()` with generator expressions
- **v2:** functions, DRY principle, variable scope and `global`, dictionary-based dispatch
- **v3:** classes and objects, `setattr()`, JSON serialization, file I/O, exception handling

## Known limitations

- Search is case-sensitive and needs an exact match
- Monthly summary matches the month as text inside the date string, with no strict date validation
- v1 and v2 lose all data when the program exits
- v3 stores everything in one flat JSON file, which is fine for personal use but not for large data

## Roadmap

- [ ] Case-insensitive and partial-match search
- [ ] Proper date validation using `datetime`
- [ ] Support decimal amounts (currently whole numbers only)
- [ ] Move storage from JSON to SQLite
- [ ] Add unit tests
- [ ] Simple GUI or CLI framework

## Author

Built as a learning project. Feedback and suggestions are welcome, feel free to open an issue.
