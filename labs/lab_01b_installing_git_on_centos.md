# :alembic: Installing Git on CentOS 7

## Goal

Install Git on a CentOS 7 Docker container.

## Requisites

To have [Docker Engine](https://www.docker.com/) already installed and configured on your local computer.

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

5. Install **Git** in the container.

    ```bash
    yum install -y git
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
    docker stop centos
    ```

    - Remove the image.

    ```bash
    docker rmi centos:7-base
    ```

<br />

## Scripts
- [Dockerfile](lab_00_container_setup/centos.7/Dockerfile)

# :books: References
- [Install Docker Engine on CentOS](https://docs.docker.com/engine/install/centos/)

<br />

:arrow_backward: [back to index](../README)

