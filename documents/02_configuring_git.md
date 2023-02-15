# :book: 2. Configuring Git

> ## _Previous topics_
> - _[About Git](../documents/00_about_git.md)._
> - _[Install Git](../documents/01_installing_git.md) on your local computer._

After installing Git, it is important to configure it on your local machine.

The Git configuration variables control some aspects of Git behavior when working with it.

Git has three scope configuration levels:

1. System. 
   - It affects all the users on the system and their repositories.
   - The configuration variables are saved to the `/etc/gitconfig` file.
   - Only the system superusers can write on the `/etc/gitconfig` file.
   - Issue the `git config --system` option to work with this configuration level.


2. Global.
   - It affects individual users and their repositories. 
   - The configuration variables are saved to the `~/.gitconfig` or the `~/.config/git/config` file.
   - Issue the `git config --global` option to use this configuration level.

3. Local.
   - It affects the current Git directory users are working on.
   - The configuration variables are saved to the `$PWD/.git/config` file.
   - Issue the `git config --local` option to work with this configuration level.


## Basic Git configuration

- Set-up your **identity**.

  ```bash
  git config --global user.name "${your-username}"
  git config --global user.email ${your-email}
  ```

- Configure the default **editor**.

  ```bash
  git config --global core.editor vim
  ```

- Let Git to use colors.

  ```bash
  git config --global color.ui true
  git config --global color.status auto
  git config --global color.branch auto
  git config --global color.interactive auto
  git config --global color.diff auto
  ```

- Set `main` as the default branch name.

  ```bash
  git config --global init.defaultBranch main
  ```

- Verify the configuration.

  ```bash
  git config --list
  ```

- List all the configuration variables and their scope

  ```bash
  git config --list --show-origin
  ```

- Display the config help options

  ```bash
  git help config
  ```

# :alembic: Practice lab

- **Goal**: [Configure Git](../labs/lab_02_configuring_git.md) on your local machine.


# :books: References
- [Getting Started - First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) 

 
<br />

:arrow_backward: [back to index](../README.md)
