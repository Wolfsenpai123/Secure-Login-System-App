# SecureAuth - Python Login System with Argon2

A simple and secure desktop login system built with **Python**, **CustomTkinter**, **SQLite**, and **Argon2** for password hashing.

This project demonstrates the core ideas of a secure authentication system, including password hashing, login attempt tracking, account lock after multiple failed attempts, last login tracking, and password changing.

---

## Features

- Secure password hashing with **Argon2**
- User login system
- Default admin account for testing
- Failed login attempt tracking
- Account lock after too many failed attempts
- Last login timestamp
- Change password functionality
- Simple modern desktop UI with **CustomTkinter**

---

## Tech Stack

- **Python**
- **CustomTkinter**
- **SQLite**
- **argon2-cffi**

---

## Project Structure

```bash
Secure Login System/
├── main.py
├── security.py
└── users.db

