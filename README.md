# Pass-Vault

PassVault is a password manager project implemented in Python using MySQL for database management. It provides functionalities for securely storing and managing passwords for various websites and applications.

## Description

PassVault enables users to create, store, and retrieve passwords securely. It utilizes strong password generation techniques and cross-checks generated passwords against the Pwned Passwords API to ensure they are not leaked. The project includes features such as creating new passwords, finding all websites/apps connected to an email, and finding a password for a specific website/app.

## Tech Stack

- Python
- MySQL
- Requests (for API integration)

## Setup

1. **Install MySQL Server**: Set up a MySQL server on your local system.

2. **Database Configuration**: Modify the database credentials in the code to match your MySQL server setup.

3. **Create Database and Tables**: Execute the following SQL commands to create the necessary database and tables:

   ```sql
   CREATE DATABASE Password_Manager;
   USE Password_Manager;
   CREATE TABLE logins (
       id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
       website VARCHAR(255),
       url VARCHAR(255),
       username VARCHAR(255),
       email VARCHAR(255),
       passcode VARCHAR(255),
       masterpass VARCHAR(255)
   );
   CREATE TABLE masterpasswords (
       idMaster INT AUTO_INCREMENT PRIMARY KEY,
       masterpass VARCHAR(255)
   );

## Dependencies Installation: Install the required Python dependencies using pip:

```bash
pip install mysql-connector-python requests
```

## Run PassVault: 

Execute the passvault.py script to run the PassVault password manager.

## Usage

**Create New Password**: 
Enter option 1 to create a new password. Provide the necessary details such as website name, email, etc., and a strong password will be generated and copied to the clipboard.

**Find Accounts by Email**: 
Enter option 2 to search for all websites/apps connected to a specific email. Provide the email address, and PassVault will display the associated accounts.

**Find Password for Website/App**: 
Enter option 3 to find the password for a specific website/app. Provide the website name, and PassVault will display the associated password.

**Exit**: 
Enter option 4 to exit PassVault.

## Security Implementations:

PassVault encrypts and hashes the master password before storing it in the database.
Generated passwords are cross-checked against the Pwned Passwords API to ensure they have not been leaked.

## License
PassVault is licensed under the MIT License.
