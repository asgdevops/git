# Installing Git on Debian 11 (bullseye)

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

5. Install **Git** in the container.

    ```bash
    sudo apt-get install -y git
    ```

6. Verify the installation was successful.

    ```bash
    git --version
    ```

7. Logout, stop and destroy the container.

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

## Scripts
- [Dockerfile](lab_00_container_setup/debian.11/Dockerfile)

<br />

:arrow_backward: [back](../01_installing_git.md)

