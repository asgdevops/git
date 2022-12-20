# :alembic: 2. Configuring Git

## Goal

Configure Git on your local computer.

## Requisites

[Install Git](../documents/01_installing_git.md) on your local computer.

## Steps

1. Set-up your **identity**.

  - Configure your username.

    ```bash
    git config --global user.name $USER
    ```

  - Set up your email address.

    ```bash
    git config --global user.email ${your-email}
    ```

2. Configure the default **editor**.

    ```bash
    git config --global core.editor vim
    ```

3. Set-up Git to use colors.

    ```bash
    git config --global color.ui true
    git config --global color.status auto
    git config --global color.branch auto
    git config --global color.interactive auto
    git config --global color.diff auto
    ```

4. Set `main` as the default branch name.

    ```bash
    git config --global init.defaultBranch main
    ```

5. Verify the configuration.

    ```bash
    git config --list
    ```

6. List all the configuration variables and their scope.

    ```bash
    git config --list --show-origin
    ```

7. Display the help options

    ```bash
    git help config
    ```

# :books: References
- [Getting Started - First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) 

<br />

:arrow_backward: [back to index](../README)
