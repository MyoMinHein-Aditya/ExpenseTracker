# 💰 Expense Tracker

A polished personal finance dashboard built with Flask, SQLite, and a modern one-page UI. It helps you track income, expenses, balance, and monthly summaries in INR (₹).

## Setup & Run

```bash
# 1. Create and activate a virtual environment (recommended)
python -m venv .venv
.venv\Scripts\activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app
python app.py

# 4. Open in browser
# http://localhost:5000
```

## Features

- ✅ **Add Money** — Record income such as salary, freelance payments, or refunds
- ✅ **Add Expense** — Enter purchases and automatically deduct them from your balance
- ✅ **Live Balance** — View your current balance instantly
- ✅ **Monthly Transactions** — Browse transactions grouped by selected month
- ✅ **Monthly Totals** — See added income, spent amount, and net change
- ✅ **Delete Transactions** — Remove entries and auto-adjust the balance
- ✅ **Charts** — View daily spending, monthly overview, and expense breakdown visuals
- ✅ **Excel Export** — Export the selected month’s data to Excel
- ✅ **Persistent Storage** — SQLite database (`expenses.db`) is created automatically
- ✅ **Keyboard Shortcuts** — Press Enter to submit and Esc to close the modal

## Project Structure

```text
expense-tracker/
├── app.py              # Flask backend and chart routes
├── requirements.txt    # Python dependencies
├── templates/
│   └── index.html      # Frontend UI
├── expenses.db         # Auto-created SQLite database
└── README.md           # Project documentation
```

## Reset Database

To clear all transactions and reset the balance to zero:

```bash
python -c "import sqlite3; conn = sqlite3.connect('expenses.db'); conn.execute('DELETE FROM transactions'); conn.execute('UPDATE balance SET amount = 0'); conn.commit(); conn.close(); print('Database cleared successfully.')"
```

You can also simply delete the `expenses.db` file. The app will recreate an empty database on the next run.
