FROM ubuntu:22.04
LABEL maintainer="Khanh Tran <kxt1979@hotmail.com>"

ARG USER_ID
ARG USER_NAME
ARG GROUP_ID

# Group may alreay exists with the same ID, then ignore
RUN addgroup --gid $GROUP_ID user || echo "Adding group if not exists"
RUN adduser --disabled-password --gecos '' --uid $USER_ID --gid $GROUP_ID $USER_NAME
RUN apt update && \
    apt install -y zsh git wget zsh fonts-powerline locales && \
    locale-gen en_US.UTF-8

USER $USER_NAME
RUN wget -O  - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh | bash
RUN cd  && \
    sed -i 's/robbyrussell/agnoster/g' .zshrc && \
    echo 'DEFAULT_USER prompt_context(){}' >> .zshrc

CMD ["zsh"]