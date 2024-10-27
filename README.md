# Encryption Techniques
Cryptography is the act of using codes or ciphers to protect secrets. 
Encryption techniques are methods of securing data by converting it into unreadable formats that can only be reverted by authorized users. Common techniques include:  

Symmetric Encryption: Uses a single key for both encryption and decryption (e.g., AES, DES).  
Asymmetric Encryption: Uses a public key for encryption and a private key for decryption (e.g., RSA).  
Hash Functions: Generates a fixed-size hash value from data, often for verifying integrity (e.g., SHA-256).  

### Key Characteristics of AES:
Block Size: 128 bits (16 bytes) — AES processes data in blocks of this size.
Key Sizes: AES supports 128-bit, 192-bit, and 256-bit keys, with longer keys offering higher security.
Symmetric Encryption: The same key is used for both encryption and decryption.
Modes of Operation: AES operates in different modes, each designed for specific use cases. The most common modes include:
ECB (Electronic Codebook Mode): Each block is encrypted independently, but it is insecure because identical plaintext blocks will yield identical ciphertext blocks.
CBC (Cipher Block Chaining Mode): Each block is XOR-ed with the previous ciphertext block before being encrypted, adding randomness and making it more secure than ECB.
CFB (Cipher Feedback Mode): The cipher is used as a stream cipher.
OFB (Output Feedback Mode): Also used as a stream cipher.
GCM (Galois Counter Mode): Provides both encryption and authentication.
In the example above, AES is used in CBC (Cipher Block Chaining) mode, which is more secure than ECB because it introduces an Initialization Vector (IV) to ensure different ciphertexts for identical messages.

### Steps in AES Encryption:
Key Generation: You need a secret key, which can be 128, 192, or 256 bits long.
Padding: The message may need to be padded if its length is not a multiple of the block size (16 bytes). Padding ensures that the last block of data is the correct size.
Encryption: The message is encrypted block by block using the key, applying XOR operations and substitutions according to the AES algorithm.
Decryption: The same key is used to decrypt the message by reversing the encryption process.
AES is widely used in various applications such as securing communications, file encryption, and more due to its efficiency and security properties. It has been adopted as the encryption standard by the U.S. government and is used across many industries worldwide.

## CBC (Cipher Block Chaining) 
CBC (Cipher Block Chaining) is one of the most commonly used modes of operation for AES (Advanced Encryption Standard). 
It enhances security by ensuring that identical plaintext blocks do not produce identical ciphertext blocks. Here's how it works and why it's widely used.

How CBC Works:
In CBC mode, each block of plaintext is XOR-ed with the previous ciphertext block before being encrypted. This creates a dependency between blocks, meaning each block of ciphertext depends on all previous blocks, adding an extra layer of security.
