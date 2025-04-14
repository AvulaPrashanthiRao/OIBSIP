import random
import string

def generate_password(length=12):
    # Define character sets
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Ensure at least one character from each category is included
    password = [
        random.choice(string.ascii_lowercase),
        random.choice(string.ascii_uppercase),
        random.choice(string.digits),
        random.choice(string.punctuation),
    ]
    
    # Fill the rest of the password length
    password += random.choices(characters, k=length - 4)
    
    # Shuffle the list to avoid predictable order
    random.shuffle(password)
    
    return ''.join(password)

# Example usage
print("Generated Password:", generate_password(16))
