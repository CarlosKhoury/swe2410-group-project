# 🔐 Flask Password Manager

A secure Flask-based password manager web app that allows users to store, organize, and manage credentials safely.

This project replaces a previous Streamlit frontend with Flask for improved Python compatibility, better routing, and a more traditional web app experience.

<img width="1882" height="856" alt="image" src="https://github.com/user-attachments/assets/ff8ad480-7538-48dc-9c1c-f365fdf3629f" />

---

## Features

### Authentication
- User registration with email + password validation
- Secure login system
- Session-based authentication
- Logout support

  <img width="1842" height="828" alt="image" src="https://github.com/user-attachments/assets/8ad8633b-775e-412d-8211-34f54f59d105" />


### Multi-Factor Authentication (MFA)
- TOTP-based 2FA using authenticator apps
- QR code generation for easy setup
- Enable/disable MFA from account settings
- Login flow with password + authenticator verification

### Password Vault
- Add, edit, and delete saved credentials
- Store:
  - Passwords
  - API keys
- Organize entries into groups:
  - Work
  - Personal
  - Social
  - Other

### Password Utilities
- Random secure password generator
- Password strength checker

### Dashboard Analytics
Vault health metrics:
- Total entries
- Weak passwords
- Reused passwords
- API key count

### Search & Filtering
Filter vault entries by:
- Entry type
- Group
- Search query

### Error Handling
- 404 redirects
- 500 error recovery

---

## Tech Stack

### Backend
- Python
- Flask

### Security / Authentication
- PyOTP (TOTP MFA)
- Session authentication
- Secure password validation

### QR Code Generation
- qrcode

### Database
- Custom database layer via `DatabaseManager`

### Existing Modules Integrated
- `LoginPage`
- `CreateAccount`
- `PasswordManager`
- `passwordGenerator`

---

## Project Structure

```bash
password-manager/
│
├── app.py
├── loginPage.py
├── createAccount.py
├── passwordManager.py
├── passwordGenerator.py
├── databaseConnect.py
│
├── templates/
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── mfa.html
│   └── account_mfa.html
│
└── static/
```

---

## Installation

### 1. Clone repository

```bash
git clone https://github.com/yourusername/password-manager.git
cd password-manager
```

### 2. Create virtual environment

```bash
python -m venv venv
```

Activate:

**Windows**
```bash
venv\Scripts\activate
```

**Mac/Linux**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install flask pyotp qrcode pillow
```

---

## Running the App

Start the server:

```bash
python app.py
```

App runs on:

```bash
http://localhost:5000
```

---

## API Endpoints

### Authentication
- `/login`
- `/register`
- `/logout`

### MFA
- `/login/mfa`
- `/account/mfa`
- `/account/mfa/start`
- `/account/mfa/confirm`
- `/account/mfa/disable`

### Vault
- `/dashboard`
- `/add-entry`
- `/edit-entry/<id>`
- `/delete-entry/<id>`

### API Routes
- `/api/entries`
- `/api/password-strength/<password>`
- `/api/generate-password`

---

## Security Features

- Session-based login protection
- Route protection via decorators
- TOTP-based MFA
- Password strength enforcement
- Input validation
- Secret key generation

---

## Example Workflow

1. Register account
2. Log in
3. Enable MFA (optional but recommended)
4. Add passwords/API keys
5. Organize credentials by category
6. Monitor vault health
7. Generate strong passwords as needed

---

## Future Improvements

- Password encryption at rest
- Password sharing
- Browser extension
- Password breach detection
- Dark mode UI
- Cloud sync

---

## License

MIT License

---

## Author

Built by Carlos Khoury
