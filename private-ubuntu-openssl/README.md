docker build -t kxtdev/private-ubuntu-openssl:v1 . 

docker run --rm -it kxtdev/private-ubuntu-openssl:v1 bash

ONE-TIME-KEY-GENERATION:
    openssl enc -aes-128-cbc -pbkdf2 -k secret -P (256 key length doesn't work with s3)

Encrypt(base64 out):
    openssl enc -aes-256-cbc -a -pbkdf2 -in file.txt -out file.base64.aes
    
Decrypt(base64 in):
    openssl enc -aes-256-cbc -d -a -pbkdf2 -in file.base64.aes -out file.decoded.txt

notes:
    -d: decrypt
    -a: base64 your data after encryption or before decryption
    -pbkdf2: using key derivation - https://en.wikipedia.org/wiki/Key_derivation_function