# Set base image 
FROM ubuntu:latest AS base
# FROM ubuntu:latest
# SHELL ["/bin/sh", "-c"]

# Update repositories
RUN apt-get update
FROM base

# Install required packages and Zsh

# Install Oh-My-Zsh
RUN apt-get install -y zsh git wget curl
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended
SHELL ["/bin/zsh", "-c"]

# # Setup zsh shell preferences
RUN echo 'PROMPT="%d $ "' >> ~/.zshrc
RUN source ~/.zshrc

# other instructions

# Install CUDA toolkit (nvcc)
# RUN apt-get update && apt-get install nvidia-cuda-toolkit -y

# Another way to install CUDA toolkit (nvcc)
# RUN wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
# RUN dpkg -i cuda-keyring_1.1-1_all.deb
# RUN apt-get update && apt-get -y install cuda-toolkit-12-3

# Set aliases
RUN echo "alias cls=clear" >> ~/.zshrc
RUN source ~/.zshrc
