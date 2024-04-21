# Gmail Email Management Script

This Python script automates the process of connecting to a Gmail account via IMAP to identify and delete emails from specified senders. It uses a YAML file to securely load user credentials and a JSON file to specify which email senders should have their messages deleted.


## Features

- **Secure Credential Storage**: Utilizes a YAML file to store and retrieve Gmail login credentials.
- **Customizable Email Deletion**: Allows the user to specify a list of email addresses in a JSON file, and deletes all emails from these senders.
- **Logging**: Implements logging to keep track of operations and errors for easier debugging and verification.
- **Data Summary**: Provides a summary of the emails processed with details about the number of messages marked for deletion from each sender.

## Prerequisites

- Python 3.6+
- Libraries: `imaplib`, `email`, `os`, `pandas`, `logging`, `json`, `yaml`
- A Gmail account with IMAP access enabled.
- Appropriate permissions to access the Gmail account via third-party apps.

## Setup

1. **Install Python Packages**: Ensure that all required Python packages are installed. You can install them using pip:
   
   ```bash
   pip install pandas pyyaml
   ```

2. **Configure Gmail for IMAP**:
   - Log into your Gmail account.
   - Go to Settings -> See all settings -> Forwarding and POP/IMAP.
   - Enable IMAP and save changes.

3. **Credential and Email List Files**:
   - **YAML File**: Create a `gmail_access.yaml` file in the `config` directory with the following structure:
     ```yaml
     user: your-email@gmail.com
     password: yourpassword
     ```
   - **JSON File**: Create an `email_list.json` file in the `config` directory with the structure:
     ```json
     {
       "emails": ["sender1@example.com", "sender2@example.com"]
     }
     ```

## Usage

Run the script from the .ipynb file which you can convert to a .py file and run from the terminal.

Running the script will execute the main function, which orchestrates the entire process:

1. **Load Credentials**: Fetches Gmail login credentials from the YAML file.
2. **Connect to Gmail IMAP**: Establishes a secure IMAP connection with Gmail.
3. **Load Email List**: Retrieves a list of email addresses from the JSON file.
4. **Delete Emails**: Marks all emails from the specified senders for deletion.
5. **Cleanup**: Closes the IMAP session and logs out, ensuring no resources are left open.

## Output

The script prints a summary of the operations, detailing the email addresses processed and the number of emails marked for deletion for each.

## Logging

Logging is configured to provide timestamps and details of operations, helping track the flow and spot potential issues.
