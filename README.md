#  Stock Portfolio Tracker

## About the Project

This is a simple desktop application built using Python and Tkinter to help users keep track of their stock investments. The goal of this project was to create a beginner-friendly tool with a clean UI that covers basic portfolio management features like adding stocks, viewing holdings, and calculating total investment.

It’s not meant to be production-level software, but more of a learning project to understand GUI development, data handling, and basic application structure in Python.

---

##  Features

* Add stocks with quantity
* View portfolio with calculated values
* Calculate total investment
* Save portfolio data to a JSON file
* Load saved portfolio
* Basic input validation and error handling

---

## Tech Stack

* Python 3
* Tkinter (for GUI)
* JSON (for local data storage)

---

## Project Structure

```
project/
│── portfolio.py        # Main application file
│── portfolio.json      # Stores saved portfolio data
```

---

## Getting Started

### Prerequisites

Make sure you have Python 3 installed.

### Run the application

```bash
python portfolio.py
```

Once you run the script, the GUI window will open.

---

## Usage

### Adding a Stock

Enter a valid stock symbol (like AAPL, TSLA) and quantity, then click **Add Stock**.

### Viewing Portfolio

Click **View Portfolio** to see all added stocks along with:

* Quantity
* Price
* Total value

### Calculating Total Investment

Click **Calculate Total** to get the overall portfolio value.

### Saving Data

Click **Save** to store your portfolio in a JSON file.

### Loading Data

Click **Load** to restore previously saved data.

---

## Available Stocks (Static Data)

| Symbol | Price |
| ------ | ----- |
| AAPL   | 180   |
| TSLA   | 250   |
| GOOG   | 2700  |
| AMZN   | 3300  |
| MSFT   | 300   |

> Note: Prices are hardcoded and do not reflect real market values.

---

## Limitations

* Uses static stock prices (no real-time data)
* No option to edit or delete stocks
* No database integration (JSON only)
* Minimal UI/UX (basic Tkinter layout)

---

## Future Improvements

Some ideas I considered but haven’t implemented yet:

* Integrate real-time stock APIs
* Add charts/visualizations for portfolio distribution
* Edit/Delete stock entries
* Add authentication/login system
* Convert into a web-based app using Flask or Django

---
