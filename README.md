import random
import string

def password_generator():
    # Get user input for password length
    while True:
        try:
            length = int(input("Enter the length of your password: "))
            if length < 8:
                print("Password length should be at least 8 characters.")
            else:
                break
        except ValueError:
            print("Invalid input. Please enter a number.")

    # Get user input for password complexity
    while True:
        complexity = input("Enter the complexity of your password (1-3): ")
        if complexity not in ['1', '2', '3']:
            print("Invalid input. Please enter 1, 2, or 3.")
        else:
           break
           # Generate password based on user input
    if complexity == '1':
        password = ''.join(random.choice(string.ascii_lowercase) for _ in range(length))
    elif complexity == '2':
        password = ''.join(random.choice(string.ascii_letters + string.digits) for _ in range(length))
    else:
        password = ''.join(random.choice(string.ascii_letters + string.digits + string.punctuation) for _ in range(length))

    print("Generated password: ", password)

password_generator()

 
