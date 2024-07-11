# Caesar-Cipher
A simple encryption program that encrypts or decrypts programs based on the number of shifts decided by the user. The shift here is the number of alphabets that are to be skipped forward in order to arrive at the new alphabet equivalent.

alphabet = [
    'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o',
    'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'
]
direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
text = input("Type your message:\n").lower()
shift = int(input("Type the shift number:\n"))

text_list = list(text)

def encrypt(plain_text, shift_number):
    cipher_text = []
    for char in plain_text:
        og_index = alphabet.index(char)
        final_index = og_index + shift_number
        if final_index >= 26:
            final_index = final_index - 26
        cipher_letter = alphabet[final_index]
        cipher_text.append(cipher_letter)
    string = "".join([str(i) for i in cipher_text])
    print(string)

encrypt(plain_text=text, shift_number=shift)
