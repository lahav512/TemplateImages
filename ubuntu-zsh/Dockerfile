# Set base image 
FROM ubuntu:latest

# Install required packages and Zsh
RUN apt-get update && \
    apt-get install -y zsh git wget curl

# Install Oh-My-Zsh
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended
RUN echo 'PROMPT="%d $ "' >> ~/.zshrc
RUN zsh -c 'source ~/.zshrc'

# Set aliases
RUN echo "alias cls=clear" >> ~/.zshrc
RUN zsh -c 'source ~/.zshrc'
