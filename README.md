# What I learned ?

This task from : https://roadmap.sh/projects/expense-tracker 

During the development of this project, I learned a great deal about working with file I/O (using JSON and CSV formats), data validation (ensuring that amounts and other inputs are valid), and how to structure an application with modular code. Additionally, I learned how to build a command-line interface and handle user input through the terminal.

I also had to implement error handling effectively, ensuring that invalid inputs (e.g., negative amounts, non-existent expense IDs) are managed gracefully. One of the most useful lessons was how to balance functionality and user experience — for example, by warning the user when the budget is exceeded and providing helpful feedback throughout the process.

Future Improvements
Recurring Expenses: Adding functionality for recurring expenses, such as monthly subscriptions.
User Authentication: Allowing multiple users to track their own expenses securely.
Charts and Visualizations: Providing graphical representations of expenses for better analysis.
Notes
Make sure to input valid amounts (positive numbers) when adding or updating expenses.
If you encounter any issues or bugs, feel free to submit an issue or pull request!

# Expense Tracker Application

This is a simple command-line application designed to help users manage their finances by tracking their expenses. The application allows users to add, update, delete, and view their expenses. Additionally, it provides summaries of all expenses and allows users to filter expenses by category and month.

## Features

- **Add an Expense**: Users can add a new expense with a description and amount.
- **Update an Expense**: Users can update an existing expense.
- **Delete an Expense**: Users can delete an expense from their records.
- **View All Expenses**: Users can view a list of all their expenses.
- **View Summary of All Expenses**: The application can show a summary of all expenses including total and category breakdown.
- **View Summary for a Specific Month**: Users can view a summary of expenses for a specific month of the current year.
- **Expense Categories**: Expenses can be assigned categories, and users can filter by category.
- **Budgeting**: Users can set a monthly budget, and the application will warn if the budget is exceeded.
- **Export to CSV**: Users can export their expenses to a CSV file for further analysis.

## How It Works

The application runs entirely from the command line, and it interacts with a text-based data file to store and retrieve expenses. Expenses are stored with descriptions, amounts, categories, and timestamps.

### Data Storage

The data is saved in a simple **JSON file**, which makes it easy to load and update the data. The format is simple to work with, ensuring both usability and flexibility. You can also export your expenses to a **CSV file** for further analysis or reporting.

## Features Implemented

### Expense Management
- **Add Expense**: I used functions to handle expense addition, allowing the user to input a description and an amount. I ensured that the amount was always a positive number by adding validation.
- **Update Expense**: This feature allows users to modify an existing expense, which can include changing the description, category, or amount.
- **Delete Expense**: Users can delete an expense by ID, and I added error handling for when an invalid ID is entered.
  
### Summaries
- **Summary of All Expenses**: I created a summary function that aggregates all expenses and presents the total amount spent.
- **Summary for a Specific Month**: I added logic to filter expenses by month, providing a summary for a specific month in the current year.
  
### Additional Features
- **Expense Categories**: I introduced categories (e.g., Food, Transport, Entertainment) and allowed users to filter expenses by category. This was a fun challenge since I had to modify the data structure to accommodate categories.
- **Budget Alerts**: I implemented a budgeting feature where users can set a monthly budget. If expenses exceed the budget, the application alerts the user.
- **CSV Export**: I added functionality to export the expenses into a CSV format, which was an excellent exercise in working with file formats and string manipulation.

## How to Use

### Requirements

- Python 3.x (or any language of your choice, but Python is used in the implementation).
- Command-line interface.

### Running the Application

1. **Clone or Download the Project**:
    ```bash
    git clone https://github.com/yourusername/Expense-Tracker.git
    cd Expense-Tracker
    ```

2. **Run the Application**:
    ```bash
    python expense_tracker.py
    ```

3. **Usage**:
    After running the application, use the following commands to interact with your expenses:

    - **Add an expense**:
      ```bash
      python expense_tracker.py add "Lunch" 12.50 --category "Food"
      ```

    - **Update an expense**:
      ```bash
      python expense_tracker.py update 1 "Lunch at Restaurant" 20.00 --category "Food"
      ```

    - **Delete an expense**:
      ```bash
      python expense_tracker.py delete 1
      ```

    - **View all expenses**:
      ```bash
      python expense_tracker.py view
      ```

    - **View expenses by category**:
      ```bash
      python expense_tracker.py view --category "Food"
      ```

    - **View expenses for a specific month**:
      ```bash
      python expense_tracker.py summary --month 4
      ```

    - **Set a monthly budget**:
      ```bash
      python expense_tracker.py budget 500
      ```

    - **Export to CSV**:
      ```bash
      python expense_tracker.py export
      ```

### Example Output

```bash
Expenses for the month of April:

- Lunch at Restaurant | $20.00 | Category: Food
- Transport to Office | $15.00 | Category: Transport
...
Total Expenses: $35.00

Remaining Budget: $465.00
