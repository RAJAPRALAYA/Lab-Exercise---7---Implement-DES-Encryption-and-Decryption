# Lab-Exercise---7---Implement-DES-Encryption-and-Decryption

# Aim:

To use the Data Encryption Standard(DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

# Procedure:

DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
DES uses a Feistel network structure with 16 rounds of processing for encryption.
DES has a 64-bit key, but only 56 bits are used for encryption(the remaining 8 bits are for parity)
DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

# Program:

```
from Crypto.Cipher import DES
from Crypto.Util.Padding import pad, unpad

key = b'12345678'

# Create DES cipher
cipher = DES.new(key, DES.MODE_ECB)

# Original message
text = b"HelloDES!"

# Encryption
padded_text = pad(text, DES.block_size)
encrypted = cipher.encrypt(padded_text)

# Decryption
decrypted_padded = cipher.decrypt(encrypted)
decrypted = unpad(decrypted_padded, DES.block_size)

# Display output
print("Original:", text.decode())
print("Encrypted:", encrypted.hex())
print("Decrypted:", decrypted.decode())
```

# Output:




# Result:

Thus, the implementation DES Encryption and Decryption are executed successfully.
