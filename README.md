# Python-Password-Strength-Checker
A lightweight Python tool to evaluate password security against standard best practices.

Method 1: Quick Testing (No Installation Needed)

#1. Copy this code into a file named password_checker.py:

    import re

    def check_strength(password):

    length = len(password) >= 8
    digit = re.search(r"\d", password) is not None
    upper = re.search(r"[A-Z]", password) is not None
    lower = re.search(r"[a-z]", password) is not None
    special = re.search(r"[!@#$%^&*(),.?\":{}|<>]", password) is not None
    
    score = sum([length, digit, upper, lower, special])
    return "Weak" if score < 3 else "Medium" if score == 3 else "Strong"

    #Try it out!#        
    print(check_strength("Hello123!"))  # Output: Strong

#2. Open your terminal (Command Prompt, Terminal, or PowerShell).

#3. Run the script:
  
    python password_checker.py

(If Python isn’t installed, you'll need to download it first).

Method 2: Interactive Testing

#4. Replace the last line of the script with this:

    if __name__ == "__main__":
      while True:
          password = input("Enter a password (or 'q' to quit): ")
          if password.lower() == 'q':
              break
          print(f"Strength: {check_strength(password)}")

Now you can type passwords directly into the terminal to test them!


