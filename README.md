# Python-Password-Generator
Generate strong and secure passwords with Python for your accounts.
 here's a Python program that generates strong and secure passwords for your accounts. The program will allow you to specify the length of the password and whether you want to include uppercase letters, lowercase letters, digits, and special characters.
import random
import string

def generate_password(length=12, use_uppercase=True, use_lowercase=True, use_digits=True, use_special=True):
    if length < 1:
        raise ValueError("Password length must be at least 1")
    
    character_pool = ''
    
    if use_uppercase:
        character_pool += string.ascii_uppercase
    if use_lowercase:
        character_pool += string.ascii_lowercase
    if use_digits:
        character_pool += string.digits
    if use_special:
        character_pool += string.punctuation
    
    if not character_pool:
        raise ValueError("No character types selected")
    
    password = ''.join(random.choice(character_pool) for _ in range(length))
    
    return password

def main():
    print("Password Generator")
    
    try:
        length = int(input("Enter the desired password length: "))
    except ValueError:
        print("Invalid input. Using default length of 12.")
        length = 12
    
    use_uppercase = input("Include uppercase letters? (y/n): ").strip().lower() == 'y'
    use_lowercase = input("Include lowercase letters? (y/n): ").strip().lower() == 'y'
    use_digits = input("Include digits? (y/n): ").strip().lower() == 'y'
    use_special = input("Include special characters? (y/n): ").strip().lower() == 'y'
    
    try:
        password = generate_password(length, use_uppercase, use_lowercase, use_digits, use_special)
        print(f"Generated password: {password}")
    except ValueError as e:
        print(e)

if __name__ == "__main__":
    main()
Explanation
import random, string: These modules provide functions to generate random characters and access character sets like uppercase letters, lowercase letters, digits, and special characters.
generate_password(): This function generates a password based on the specified criteria.
length: The desired length of the password.
use_uppercase, use_lowercase, use_digits, use_special: Flags to include different character types.
The function builds a pool of characters based on the selected criteria and then generates a password by randomly selecting characters from the pool.
main(): This function handles user interaction.
It prompts the user for the desired password length and which character types to include.
It then calls generate_password() to create the password and prints it.
if name == "main": This ensures that the script runs the main() function only when executed directly, not when imported as a module.
Running the Program
Save the code to a file, for example, password_generator.py.
Open a terminal or command prompt.
Navigate to the directory where you saved password_generator.py.
Run the program by typing python password_generator.py.
This program provides a simple and customizable way to generate strong passwords, helping to enhance the security of your accounts.







