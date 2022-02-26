FROM ubuntu:22.04
LABEL maintainer="Khanh Tran <kxt1979@hotmail.com>"
RUN apt update && apt install -y openssl

CMD ["/bin/bash", "-c",  "openssl enc -aes-256-cbc -a -pbkdf2 -p -in ${IN} -out ${OUT}"]
