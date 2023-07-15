# cookies_grabber
This code is a Python script that attempts to steal and send Chrome browser credentials to a specified Discord webhook. Here's a breakdown of the code:

Import necessary modules: The script imports several modules including os, json, base64, sqlite3, shutil, datetime, and discord_webhook.

Check module dependencies: The script tries to import additional modules such as discord_webhook, win32crypt, and Crypto.Cipher.AES. If any of these modules are not found, it attempts to install them using pip.

Define the Discord webhook URL: The script sets the WEBHOOK variable with the URL of the Discord webhook where the stolen credentials will be sent.

Define utility functions:

getUsername(): Retrieves the username of the current user.
my_chrome_datetime(time_in_milliseconds): Converts Chrome's timestamp format to a human-readable datetime object.
encryption_key(): Retrieves the encryption key used by Chrome to encrypt the saved passwords.
decrypt_password(enc_password, key): Decrypts the encrypted password using the encryption key.
stealcreds(): Copies and accesses the Chrome password database, decrypts the passwords, and stores the data in a dictionary.
Initialize a Discord webhook: The script creates a DiscordWebhook object with the specified webhook URL and sets the username and content of the webhook message.

Attempt to steal and send credentials:

The script calls the stealcreds() function to retrieve the Chrome credentials and stores them in the data variable.
It saves the data as a JSON file in the temporary directory.
The script adds the JSON file as an attachment to the Discord webhook message.
The webhook message is sent to the specified webhook URL.
If any exception occurs during the process, an error message is added to the webhook content and sent to the Discord webhook.
