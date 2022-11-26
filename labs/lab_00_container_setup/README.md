# Lab container setup

The purpose of the laboratory consists of creating a Docker container to execute the practices (hands-on) documented by this repository.

# Creating a Debian 11 (bullseye) container

## Steps

1. Create a `Dockerfile` with **Debian 11** specifications

    ```docker
    FROM debian:11
    USER root

    ENV DEBIAN_FRONTEND noninteractive
    SHELL ["/bin/bash", "-o", "pipefail", "-c"]

    ARG username

    # Install sudo
    RUN apt update -y && apt install -y sudo 

    # Set up custom user granted to sudoers group
    RUN useradd -rm -d /home/$username -s /bin/bash -g root -G sudo -u 1000 $username
    RUN echo $username:$username | chpasswd
    RUN echo "$username ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers

    USER $username
    WORKDIR /home/$username

    CMD ["/bin/bash"]
    ```

2. Build the Docker **image** from the `Dockerfile`.

    ```bash
    docker build . --build-arg username=$USER -t debian:11-base
    ```

3. Create a container from the built image.

    ```bash
    docker run --detach --entrypoint '/bin/bash' --interactive --name debian --rm debian:11-base
    ```

4. Login to the container

    ```bash
    docker exec -it debian bash
    ```

5. Logout, stop and destroy the container.

    - Logout the container.

    ```bash
    exit
    ```

    - Stop the container.

    ```bash
    docker stop debian
    ```

    - Remove the image.

    ```bash
    docker rmi debian:11-base
    ```

<br />

# Installing Git on CentOS 7
## Steps

1. Create a `Dockerfile` with **CentOS 7** specifications

    ```docker
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
    ```

2. Build the Docker **image** from the `Dockerfile`.

    ```bash
    docker build . --build-arg username=$USER -t centos:7-base
    ```

3. Create a container from the built image.

    ```bash
    docker run --detach --entrypoint '/bin/bash' --interactive --name centos --rm centos:7-base
    ```

4. Login to the container

    ```bash
    docker exec -it centos bash
    ```

5. Logout, stop and destroy the container.

    - Logout the container.

    ```bash
    exit
    ```

    - Stop the container.

    ```bash
    docker stop centos
    ```

    - Remove the image.

    ```bash
    docker rmi centos:7-base
    ```

<br />

## Scripts
- [Debian Dockerfile](debian.11/Dockerfile)
- [CentOS Dockerfile](centos.7/Dockerfile)

<br />

:arrow_backward: [back to index](../../README.md)
