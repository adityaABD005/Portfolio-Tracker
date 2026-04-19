# Code Explanation — Stock Portfolio Tracker (Tkinter GUI)

## 1. Basic Setup

* `STOCK_PRICES` → Dictionary storing predefined stock prices
* `DATA_FILE` → File name used to save/load portfolio data (`portfolio.json`)

---

## 2. Class: PortfolioApp

This class manages the entire application including GUI and logic.

### Initialization (`__init__`)

* Sets window title

* Initializes an empty dictionary:

  * `self.portfolio` → stores stocks and their quantities

* Creates UI components:

  * Labels → for stock symbol and quantity
  * Entry fields → for user input
  * Buttons → Add, View, Calculate, Save, Load
  * Text area → displays output

---

## 3. Adding Stock

### `add_stock()`

* Takes user input:

  * Stock symbol
  * Quantity

* Validations:

  * Stock must exist in `STOCK_PRICES`
  * Quantity must be a positive integer

* Updates portfolio:

  ```python
  self.portfolio[symbol] = self.portfolio.get(symbol, 0) + qty
  ```

* Shows success/error messages using messagebox

* Clears input fields after adding

---

## 4. Viewing Portfolio

### `view_portfolio()`

* Clears previous output

* Checks if portfolio is empty

* Displays for each stock:

  * Symbol
  * Quantity
  * Price
  * Total value (`price × quantity`)

---

## 5. Calculating Total Investment

### `calculate_total()`

* Loops through all stocks

* Calculates total investment:

  ```python
  total += STOCK_PRICES[symbol] * qty
  ```

* Displays final total in output box

---

## 6. Saving Portfolio

### `save_portfolio()`

* Saves portfolio data into JSON file

* Uses:

  ```python
  json.dump(self.portfolio, file)
  ```

* Shows confirmation message

---

## 7. Loading Portfolio

### `load_portfolio()`

* Reads data from JSON file

* Updates `self.portfolio`

* Handles error:

  * If file not found → shows error message

---

## 8. Output Display

* Uses `Text` widget to display:

  * Portfolio details
  * Total investment
* Allows multi-line formatted output

---

## 9. GUI Interaction

* Buttons trigger functions:

  * Add → `add_stock()`
  * View → `view_portfolio()`
  * Total → `calculate_total()`
  * Save → `save_portfolio()`
  * Load → `load_portfolio()`

---

## 10. Application Start

```python
root = tk.Tk()
app = PortfolioApp(root)
root.mainloop()
```

* Initializes main window
* Runs the GUI loop (keeps app running)

---

## Overall Working

This project is a **GUI-based stock management system**:

* User adds stocks and quantity
* Application calculates individual and total values
* Data can be saved and loaded using JSON

---

## Concepts Used

* Tkinter (GUI development)
* Dictionaries (data storage)
* File handling (JSON)
* Input validation
* Event-driven programming

---
