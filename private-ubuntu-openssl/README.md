docker build -t kxtdev/private-ubuntu-openssl:v1 . 

docker run --rm -it kxtdev/private-ubuntu-openssl:v1 bash

Encrypt(base64 out):
    openssl enc -aes-256-cbc -a -pbkdf2 -in myseeds.txt -out my_encrypted_seeds.aes
    
Decrypt(base64 in):
    openssl enc -aes-256-cbc -d -a -pbkdf2 -in my_encrypted_seeds.aes

notes:
    -d: decrypt
    -a: base64 your data after encryption or before decryption
    -pbkdf2: using key derivation - https://en.wikipedia.org/wiki/Key_derivation_function

ONE-TIME-KEY-GENERATION:
    openssl enc -aes-256-cbc -pbkdf2 -k secret -P