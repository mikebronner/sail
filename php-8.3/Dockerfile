# syntax=docker/dockerfile:1
FROM sail-8.3/app

RUN apt-get update \
	&& apt-get install -y nala zsh

## install minio mc
RUN curl https://dl.min.io/client/mc/release/linux-amd64/mc \
	--create-dirs \
	-o /usr/bin/mc
RUN chmod +x /usr/bin/mc

## configure passwordless sudo
RUN useradd -ms /bin/zsh --no-user-group -g $WWWGROUP -u 1337 sail
RUN adduser sail sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

## set up oh-my-zsh
USER sail
RUN sh -c "$(curl -L https://github.com/deluan/zsh-in-docker/releases/download/v1.1.4/zsh-in-docker.sh)" -- \
	-p git \
	-p https://github.com/jessarcher/zsh-artisan \
	-p https://github.com/zsh-users/zsh-autosuggestions \
	-p https://github.com/MichaelAquilina/zsh-you-should-use \
	-p https://github.com/zsh-users/zsh-syntax-highlighting \
	-p https://github.com/zsh-users/zsh-completions
RUN mv /home/sail/.oh-my-zsh/custom/plugins/zsh-you-should-use /home/sail/.oh-my-zsh/custom/plugins/you-should-use
RUN mv /home/sail/.oh-my-zsh/custom/plugins/zsh-artisan /home/sail/.oh-my-zsh/custom/plugins/artisan
USER root
COPY .zshrc /home/sail/.zshrc
COPY .p10k.zsh /home/sail/.p10k.zsh

## install github flow
RUN cd /home/sail \
	&& git clone https://github.com/datasift/gitflow \
	&& cd gitflow \
	&& ./install.sh
