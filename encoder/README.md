docker build -t kxtdev/encoder:v1 . 

docker run --rm \
-v $PWD:/working \
-e PASSWORD=$PASSWORD \
-e IN=/working/file.txt \
-e OUT=/working/file.enc \
kxtdev/encoder:v1

notes:
    -d: decrypt
    -a: base64 your data after encryption or before decryption
    -pbkdf2: using key derivation - https://en.wikipedia.org/wiki/Key_derivation_function