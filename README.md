# password_check
Highly secure password breaches checker

The Password Checker is a tool that allows you to check if your passwords have been compromised in data breaches. 
It uses the Pwned Passwords API by Troy Hunt to lookup passwords in a secure and privacy-focused manner.
__________________________________________________________________________________________________________
Prerequisites
Python 3.x
requests library (pip install requests)

__________________________________________________________________________________________________________
Usage
1. Clone the repository or download the check_passwords.py file.

2. In the terminal, navigate to the directory where check_passwords.py is located.

3. Run the following command to check passwords from a file:
      python3 check_passwords.py <password_file>
  Replace <password_file> with the path to the file that contains the passwords you want to check.
  The file should contain one password per line.

  If you use the passwords.txt from the repository your command should look like this:
      python3 password_check.py passwords.txt 

4. The tool will check each password against the Pwned Passwords API and display the results in the terminal. 
  If a password is found in the API's database, it means the password has been compromised and should be changed.


Example output:
   password1 was found 12345 times... you should probably change your password!
   password2 was NOT found. Carry on!

__________________________________________________________________________________________________________
How it Works
1. The tool reads the passwords from the specified file.

2. For each password, it calculates the SHA-1 hash of the password and converts it to uppercase.

3. The first 5 characters of the hash are used as a prefix for the lookup in the Pwned Passwords API.

4. The tool sends a GET request to the Pwned Passwords API with the hash prefix.

5. The API responds with a list of hashes that match the prefix.

6. The tool compares the remaining characters of the hash with the received hashes to find a match.

7. If a match is found, it means the password has been compromised.
   The tool displays the number of times the password has been found in data breaches.

8. If no match is found, it means the password has not been compromised.

9. The tool repeats the process for each password in the file.

10. The tool completes and displays the results in the terminal.

__________________________________________________________________________________________________________
Note: The Password Checker does not send the actual password to the API, only the hash prefix. 
This ensures the security and privacy of the passwords being checked.

That's it! You can now use the Password Checker to check your passwords and ensure their security.

__________________________________________________________________________________________________________
Special thanks to Troy Hunt for providing the Have I Been Pwned API. 
The API enables secure and privacy-focused password checks, helping users protect their online accounts from data breaches.
