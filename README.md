# Password-manager
A simple command-line password manager written in Python that securely stores your passwords using symmetric encryption with the cryptography library.

🚀 Features

Encrypts passwords using the Fernet module from the cryptography package.

Secure master password support.

Stores encrypted passwords in a local file (password.txt).

View decrypted passwords securely.

📁 File Structure
├── password_manager.py   # Main script
├── key.key               # Encryption key file (auto-generated)
├── password.txt          # Encrypted password storage

🛠 Requirements

Python 3.x

cryptography library

Install dependencies:

pip install cryptography

🔑 Key Generation

Before using the script, generate your encryption key:

from cryptography.fernet import Fernet

def write_key():
    key = Fernet.generate_key()
    with open("key.key", "wb") as key_file:
        key_file.write(key)

write_key()


⚠️ Run this code once to generate the key.key file. Keep it safe! If lost, you won’t be able to decrypt your passwords.

🧠 Master Password

When you run the script, it will ask you for a master password. This is combined with your encryption key to ensure that your passwords are safe. Make sure to remember it — you’ll need the same master password each time.

💻 How to Use

Run the script:

python password_manager.py


Enter your master password when prompted.

Choose one of the options:

add – Add a new password.

view – View stored passwords.

q – Quit the application.

🔒 Example Usage
What is the master Password? *****
Would you like to add a password or view existing ones? (view/add), press q to quit. add
Account name: github
Password: myGitHubPassword123

Would you like to add a password or view existing ones? (view/add), press q to quit. view
User: github | Password: myGitHubPassword123

⚠️ Security Warning

This is a basic example for educational purposes. For real-world applications:
Avoid storing master password in plain text.
Use salting and hashing.
Never commit your key.key or password.txt files to a public repository.
Consider using more secure password managers or libraries for production-level projects.
