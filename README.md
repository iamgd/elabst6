# elabst6
# 🔐 Create a Strong Password and Evaluate Its Strength

# 🧩 Objective

The goal of this task is to understand how password complexity affects security by creating, testing, and analyzing multiple passwords of varying strength.

# 🧱 Steps Performed

# 1. Create Multiple Passwords

Created a passwords.txt file containing several passwords with different levels of complexity.

Included examples with lowercase only, mixed case, numbers and special characters.

# 2. Install Password Strength Tools

Installed necessary packages on Kali Linux:

sudo apt update
sudo apt install cracklib-runtime libcrack2 libpwquality-tools libpam-pwquality -y

# 3. Test Password Strength

Checked each password using:

while IFS= read -r pw; do
  score=$(echo "$pw" | pwscore)
  printf '%s: %s\n' "$pw" "$score"
done < passwords.txt > pwscore_report.txt

Also used:

while read p; do
  echo "$p : $(echo $p | cracklib-check)"
done < passwords.txt > strength_report.txt

# 4. Analyze Results

 - Compared feedback and scores from the tools.

 - Observed that longer passwords with mixed character types scored higher.

 - Weak passwords were flagged as “too simple” or “based on a dictionary word.”

# 5. Identify Best Practices

Derived key points on what makes a password strong and resistant to brute force or dictionary attacks.

Length and Complexity

    Minimum Length: 
    Aim for at least 12-16 characters. Longer passwords are significantly harder to crack.

    Character Variety: 
    Use a mix of uppercase letters, lowercase letters, numbers, and special characters (e.g., @, #, $).

Avoid Common Pitfalls

    No Personal Information: 
    Avoid using names, birthdays, or easily guessed information.

    No Dictionary Words: 
    Do not use words that can be found in a dictionary or common phrases.

Techniques for Strong Passwords

    Passphrases: 
    Create a memorable phrase by combining unrelated words (e.g., "Dadoo*Jazar#5$1"). This can be easier to remember and harder to guess.

    Random Characters: 
    Use a random string of characters. Password managers can generate these for you.

Unique Passwords for Each Account

    Avoid Reuse: 
    Each account should have a unique password. This prevents a breach on one site from compromising others.

Use a Password Manager

    Convenience and Security: 
    A password manager can help you create, store, and manage strong passwords without needing to remember each one.

Enable Multi-Factor Authentication (MFA)

    Extra Layer of Security: 
    Whenever possible, use MFA, which requires more than just a password to access your accounts.

# 6. Research on Common Attacks

Studied how brute force, dictionary, and rainbow table attacks target weak passwords.
Learned that password complexity and uniqueness make these attacks far less effective.

# 📄 Files Created

passwords.txt → List of test passwords

pwscore_report.txt → Password strength scores

strength_report.txt → Cracklib feedback

final_password_analysis.txt → Combined results and observations

# 🧰 Tools Used

pwscore – Password strength scoring tool

cracklib-check – Checks passwords against known weak patterns

Bitwarden Password Strength Checker – https://bitwarden.com/password-strength/

Kali Linux Terminal – For performing all testing and analysis

# 🧠 Summary of Findings

Passwords with more length, randomness, and mixed characters are far more secure.

Weak or predictable passwords can be cracked within seconds by automated tools.

Using a password manager and multi-factor authentication (MFA) greatly improves security.

