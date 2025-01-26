def caesar_cipher(text, shift, direction):
    """
    Encrypts or decrypts text using the Caesar Cipher algorithm.

    Args:
        text (str): The input text to be encrypted or decrypted.
        shift (int): The shift value for the Caesar Cipher.
        direction (str): 'encrypt' or 'decrypt' to specify the operation.

    Returns:
        str: The encrypted or decrypted text.
    """
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    result = ''

    for char in text:
        if char.isalpha():
            index = alphabet.index(char.lower())
            if direction == 'encrypt':
                new_index = (index + shift) % 26
            elif direction == 'decrypt':
                new_index = (index - shift) % 26
            if char.isupper():
                result += alphabet[new_index].upper()
            else:
                result += alphabet[new_index]
        else:
            result += char

    return result

def main():
    while True:
        print("Caesar Cipher Program")
        print("1. Encrypt")
        print("2. Decrypt")
        print("3. Quit")
        choice = input("Choose an option: ")

        if choice == '1':
            text = input("Enter the text to encrypt: ")
            shift = int(input("Enter the shift value: "))
            encrypted_text = caesar_cipher(text, shift, 'encrypt')
            print(f"Encrypted text: {encrypted_text}")
        elif choice == '2':
            text = input("Enter the text to decrypt: ")
            shift = int(input("Enter the shift value: "))
            decrypted_text = caesar_cipher(text, shift, 'decrypt')
            print(f"Decrypted text: {decrypted_text}")
        elif choice == '3':
            break
        else:
            print("Invalid choice. Please choose a valid option.")

if __name__ == "__main__":
    main()
