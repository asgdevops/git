<div id='02-configuring-git'/>

# 2. Configuring Git

It is important to configure Git the first time you use it in your local machine.

- Set-up your credentials

  ```bash
  git configure --global user.name "${your-username}"
  git configure --global user.email ${your-email}
  ```

- Configure the default editor

  ```bash
  git configure --global core.editor vim
  git config --global color.ui true
  git config --global color.status auto
  git config --global color.branch auto
  git config --global color.interactive auto
  git config --global color.diff auto
  ```
- Verifying the initial configuration

  ```bash
  git configure --list
  ```

<br />

:arrow_backward: [back](README.md#00-toc)
