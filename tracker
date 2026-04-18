import tkinter as tk
from tkinter import messagebox
import json

# Predefined stock prices
STOCK_PRICES = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOG": 2700,
    "AMZN": 3300,
    "MSFT": 300
}

DATA_FILE = "portfolio.json"


class PortfolioApp:
    def __init__(self, root):
        self.root = root
        self.root.title("Stock Portfolio Tracker")

        self.portfolio = {}

        # Input fields
        self.symbol_label = tk.Label(root, text="Stock Symbol")
        self.symbol_label.pack()

        self.symbol_entry = tk.Entry(root)
        self.symbol_entry.pack()

        self.qty_label = tk.Label(root, text="Quantity")
        self.qty_label.pack()

        self.qty_entry = tk.Entry(root)
        self.qty_entry.pack()

        # Buttons
        self.add_button = tk.Button(root, text="Add Stock", command=self.add_stock)
        self.add_button.pack(pady=5)

        self.view_button = tk.Button(root, text="View Portfolio", command=self.view_portfolio)
        self.view_button.pack(pady=5)

        self.total_button = tk.Button(root, text="Calculate Total", command=self.calculate_total)
        self.total_button.pack(pady=5)

        self.save_button = tk.Button(root, text="Save", command=self.save_portfolio)
        self.save_button.pack(pady=5)

        self.load_button = tk.Button(root, text="Load", command=self.load_portfolio)
        self.load_button.pack(pady=5)

        # Output area
        self.output = tk.Text(root, height=10, width=50)
        self.output.pack(pady=10)

    def add_stock(self):
        symbol = self.symbol_entry.get().upper().strip()
        qty = self.qty_entry.get().strip()

        if symbol not in STOCK_PRICES:
            messagebox.showerror("Error", "Stock not available")
            return

        try:
            qty = int(qty)
            if qty <= 0:
                raise ValueError
        except ValueError:
            messagebox.showerror("Error", "Invalid quantity")
            return

        self.portfolio[symbol] = self.portfolio.get(symbol, 0) + qty
        messagebox.showinfo("Success", f"{symbol} added")

        self.symbol_entry.delete(0, tk.END)
        self.qty_entry.delete(0, tk.END)

    def view_portfolio(self):
        self.output.delete(1.0, tk.END)

        if not self.portfolio:
            self.output.insert(tk.END, "Portfolio is empty\n")
            return

        for symbol, qty in self.portfolio.items():
            price = STOCK_PRICES[symbol]
            value = price * qty
            self.output.insert(tk.END, f"{symbol} | Qty: {qty} | Price: {price} | Value: {value}\n")

    def calculate_total(self):
        total = 0
        for symbol, qty in self.portfolio.items():
            total += STOCK_PRICES[symbol] * qty

        self.output.insert(tk.END, f"\nTotal Investment: {total}\n")

    def save_portfolio(self):
        with open(DATA_FILE, "w") as file:
            json.dump(self.portfolio, file)
        messagebox.showinfo("Saved", "Portfolio saved to file")

    def load_portfolio(self):
        try:
            with open(DATA_FILE, "r") as file:
                self.portfolio = json.load(file)
            messagebox.showinfo("Loaded", "Portfolio loaded")
        except FileNotFoundError:
            messagebox.showerror("Error", "No saved file found")


# Run app
root = tk.Tk()
app = PortfolioApp(root)
root.mainloop()
