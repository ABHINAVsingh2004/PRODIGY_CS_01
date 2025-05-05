# PRODIGY_CS_01
def caesar_cipher(text, shift, mode="encrypt"):
    result = ""
    if mode == "decrypt":
        shift = -shift  # Reverse shift for decryption
    
    for char in text:
        if char.isalpha():
            shift_amount = shift % 26
            new_char = chr(((ord(char.lower()) - ord('a') + shift_amount) % 26) + ord('a'))
            if char.isupper():
                new_char = new_char.upper()
            result += new_char
        else:
            result += char  # Keep non-alphabet characters unchanged
    
    return result

# User input
mode = input("Enter mode (encrypt/decrypt): ").strip().lower()
text = input("Enter the text: ")
shift = int(input("Enter shift value: "))

# Perform encryption or decryption
output = caesar_cipher(text, shift, mode)
print(f"Result: {output}")
