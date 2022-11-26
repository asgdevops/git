FROM centos:7
USER root

ENV DEBIAN_FRONTEND noninteractive
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ARG username

# Install sudo
RUN yum install --nogpgcheck -y sudo 

# Grant custom user to sudoers group
RUN useradd -rm -d /home/$username -s /bin/bash -g root -G wheel -u 1000 $username
RUN echo $username:$username | chpasswd
RUN echo "$username ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

USER $username
WORKDIR /home/$username

CMD ["/bin/bash"]

# ...
# docker build . --build-arg username=$USER -t centos:7-base
# docker run --detach --entrypoint '/bin/bash' --interactive --name centos --rm centos:7-base
