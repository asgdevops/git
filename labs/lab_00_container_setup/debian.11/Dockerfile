FROM debian:11
USER root

ENV DEBIAN_FRONTEND noninteractive
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ARG username

# Install sudo and SSHD
RUN apt update -y && apt install -y sudo 

# Set up custom user
RUN useradd -rm -d /home/$username -s /bin/bash -g root -G sudo -u 1000 $username
RUN echo $username:$username | chpasswd
RUN echo "$username ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

USER $username
WORKDIR /home/$username

CMD ["/bin/bash"]

# ...
# docker build . --build-arg username=$USER -t debian:11-base
# docker run --detach --entrypoint '/bin/bash' --interactive --name debian --rm debian:11-base