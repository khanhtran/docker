FROM ubuntu:22.04
LABEL maintainer="Khanh Tran <kxt1979@hotmail.com>"

RUN apt update && \
    apt install -y zsh git wget zsh fonts-powerline locales && \
    locale-gen en_US.UTF-8

RUN wget -O  - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh | bash

#customize theme
RUN cd  && \
    sed -i 's/robbyrussell/agnoster/g' .zshrc && \
    echo 'DEFAULT_USER prompt_context(){}' >> .zshrc

CMD ["zsh"]