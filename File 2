from flask import Flask, render_template
import sqlite3

app = Flask(__name__)

@app.route('/')
def dashboard():
    conn = sqlite3.connect("database.db")
    users = conn.execute("SELECT COUNT(*) FROM users").fetchone()[0]
    withdraws = conn.execute("SELECT * FROM withdraw_requests WHERE status='pending'").fetchall()
    return render_template("dashboard.html", users=users, withdraws=withdraws)

if __name__ == "__main__":
    app.run()
