# SecureAuth - Python Login System with Argon2

A simple and secure desktop login system built with **Python**, **CustomTkinter**, **SQLite**, and **Argon2** for password hashing.

This project demonstrates the core ideas of a secure authentication system, including password hashing, login attempt tracking, account locking after multiple failed attempts, last login tracking, and password changing.

---

## ✨ Features

- Secure password hashing with **Argon2**
- Desktop login system built with **CustomTkinter**
- Default admin account for testing
- Failed login attempt tracking
- Account lock after too many failed attempts
- Last login timestamp
- Change password functionality
- Simple modern UI

---

## 🛠 Tech Stack

- **Python**
- **CustomTkinter**
- **SQLite**
- **argon2-cffi**

---

## 📁 Project Structure

```bash
Secure Login System/
├── main.py
├── security.py
└── users.db
```

- `main.py` - GUI application
- `security.py` - authentication, password hashing, and database logic
- `users.db` - SQLite database created automatically when the program runs

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone <your-repo-link>
cd "Secure Login System"
```

### 2. Install dependencies

```bash
py -m pip install customtkinter argon2-cffi
```

---

## ▶️ Run the Application

```bash
py main.py
```

---

## 🔐 Default Login

When the application runs for the first time, it creates a default account:

**Username:** `admin`  
**Password:** `admin123`

> It is recommended to change the default password after the first successful login.

---

## 🧠 How It Works

### Password Hashing
Passwords are never stored in plain text.  
They are hashed using **Argon2**, a modern and secure password hashing algorithm.

### Failed Login Attempts
The system tracks failed login attempts for each user.

### Account Lock
After **5 failed login attempts**, the account becomes locked.

### Last Login Tracking
The system records the last successful login time.

### Password Change
Users can update their password after logging in.

---

## 🧪 Testing the Application

### Test Case 1: Successful Login
Use the default credentials:

- Username: `admin`
- Password: `admin123`

Expected result:
- Login succeeds
- Dashboard is displayed
- User information appears correctly

### Test Case 2: Incorrect Password
Enter a wrong password for `admin`.

Expected result:
- Login fails
- Error message is displayed
- Failed attempt count increases

### Test Case 3: Account Lock
Enter the wrong password **5 times**.

Expected result:
- Account becomes locked
- Login is denied even if the password is later correct

### Test Case 4: Change Password
After logging in:
- Click **Change Password**
- Enter a new password
- Log out
- Log in again with the new password

Expected result:
- New password works successfully

---

## 🔄 Reset Locked Account / Reset Attempts

If the account is locked after too many failed attempts, you can reset it manually.

### Option 1: Reset attempts for `admin`

Open PowerShell in the project folder and run:

```powershell
py -c "import sqlite3; conn=sqlite3.connect('users.db'); cur=conn.cursor(); cur.execute(\"UPDATE users SET attempts = 0 WHERE username = 'admin'\"); conn.commit(); conn.close(); print('Unlocked admin account.')"
```

---

### Option 2: Reset attempts for any user

Open PowerShell:

```powershell
py
```

Then run:

```python
import sqlite3
conn = sqlite3.connect("users.db")
cur = conn.cursor()

username = "admin"  # change this to your username
cur.execute("UPDATE users SET attempts = 0 WHERE username = ?", (username,))

conn.commit()
conn.close()
print(f"Unlocked account: {username}")
```

Exit Python:

```python
exit()
```

---

### Option 3: Recreate the whole database

Delete the `users.db` file, then run the app again:

```bash
py main.py
```

This will recreate the database and the default admin account.

---

## 📸 Screenshot

Add your screenshot file to the repository and replace the path below if needed:

```markdown
![SecureAuth Screenshot](screenshot.png)
```

---

## ⚠️ Notes

- This project is built for **learning and demonstration purposes**
- The current version is a **desktop application**, not a web application
- The current account lock mechanism requires a **manual reset**
- A default test account is created automatically

---

## 🚧 Future Improvements

- Temporary lock with timeout instead of permanent lock
- Generic login error messages to reduce user enumeration
- Password strength validation
- User registration system
- Password reset flow
- Better audit logging
- Web version with **Flask** or **FastAPI**
- Session management for web authentication
- Multi-user support

---

## 📜 License

This project is intended for educational use.
