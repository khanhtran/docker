docker build -t kxtdev/decoder:v1 . 

docker run --rm \
-v $PWD:/working \
-e PASSWORD=<password> \
-e IN=/working/file.base64.aes \
-e kxtdev/decoder:v1

notes:
    -d: decrypt
    -a: base64 your data after encryption or before decryption
    -pbkdf2: using key derivation - https://en.wikipedia.org/wiki/Key_derivation_function