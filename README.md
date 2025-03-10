# SCT_SC_1
def caesar_cipher(text, shift, mode):
    result = ""

    # Adjust shift for decryption
    if mode == 'decrypt':
        shift = -shift

    # Loop through each character in the text
    for char in text:
        # Check if character is an uppercase letter
        if char.isupper():
            # Shift within the range of uppercase letters
            new_char = chr((ord(char) - 65 + shift) % 26 + 65)
            result += new_char
        # Check if character is a lowercase letter
        elif char.islower():
            # Shift within the range of lowercase letters
            new_char = chr((ord(char) - 97 + shift) % 26 + 97)
            result += new_char
        else:
            # Non-alphabetic characters are added without change
            result += char

    return result


def main():
    print("Caesar Cipher Program")
    mode = input("Choose mode (encrypt/decrypt): ").lower()

    if mode not in ['encrypt', 'decrypt']:
        print("Invalid mode. Please choose 'encrypt' or 'decrypt'.decrypt")
        return

    text = input("Enter your message: ")
    shift = int(input("Enter shift value (e.g., 3): "))

    result = caesar_cipher(text, shift, mode)
    print(f"Result: {result}")


if __name__ == "__main__":
    main()
