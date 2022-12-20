# :book: 3. Creating a Repository in Git

> ## _Previous topics_
> - _[About Git](../documents/00_about_git.md)._
> - _[Install Git](../documents/01_installing_git.md) on your local computer._
> - _[Configure Git](../documents/02_configuring_git.md) before using it._

## Repositoy creation options

There are different options for creating repositories in Git:
1. Create a **local** repository and synchronize it with a **remote** repository after. 
2. Clone from a **remote** repository already existing in [GitHub](https://github.com/).

## Local repository

The local repository is the Git database, where the metadata gets stored. Git creates the `$PWD/.git` directory to keep its database. In this case, `$PWD` means the current working directory.

## Remote repository

Git offers the possibility to distribute the repositories across the Internet. A powerful feature this option gives is the capability of having a group of people contributing to the same [GitHub](https://github.com/) repository keeping the data integrity.

Remote repositories require creating an account in [GitHub](https://github.com/) and will be covered later.


# Creating a **local** repository in Git 

1. Go to the working directory.

    ```bash
    mkdir -p $HOME/portfolio/markdown
    cd $HOME/portfolio/markdown
    ```

    > This example creates a new repository to initialize Git. However, you could use an existing repository.
    
2. Initialize Git.

    ```bash
    git init
    ```

3. Create the first version of `README` file.

    ```bash
    echo "# :book: Markdown User Guide" > README
    cat README
    ```

    The following diagram shows the status of Git working tree.

    ![](../images/git_recording_0.drawio.png)
    *Diagram 3*

4. Review the <span style="color:red">**Working Directory**</span> status.

    ```bash
    git status
    ```

5. Add the changes to the <span style="color:green">**Staging Area**</span>.

    ```bash
    git add README
    ```
 
    _The command **git add .** (dot), `git add .` adds multiple files or directories in a single pace._

    Now the status of Git working tree looks like.

    ![rec](../images/git_recording_1.drawio.png)
    *Diagram 4*

6. Save the changes to the <span style="color:gold">Git database</span>.

    ```bash
    git commit -m 'Initial commit'
    ```

    _Use `-m` to add comments to the changes[^1]._

    
    ![rec](../images/git_recording_2.drawio.png)
    *Diagram 5*

7. Verify the changes log.

    ```bash
    git log
    ```

# Creating a Remote repository in **GitHub**

1. Go to [GitHub](https://github.com/) and sign in.

2. On the **Top Repositories** section click on the **New** button.

    ![github](../images/github_repo_01.png)

3. Type the **Repository name**, **Description**, whether it is **Public** or **Private**, if you would like to add a **README** or **.gitignore** files.

    ![github](../images/github_repo_02.png)

4. Click on the **Create repository** button.

    ![github](../images/github_repo_03.png)


# **Synchronizing** both **local** and **remote** repositories

1. Open a terminal a go to your local repository

    ```
    cd ~/portfolio/markdown
    ```

2. On GitHub, copy the HTTPS or SSH command line and paste it onto your local terminal.
    ```
    git remote add origin git@github.com:asgdevops/markdown.git
    ```

3. Verify the remote repository has been setup properly.

    ```
    git remote -v
    ```

4. Rename your main branch (optional)

    ```
    git branch -M main
    ```

5. Syncronize any changes

    - Update your Git database (tree)

    ```
    git add
    git commit -m 'Git/GitHub'
    ```

    - Push any changes

    ```
    git push -u origin main
    ```

    - Take the HEAD up to the latest update (edge) on your local repository.

    ```
    git fetch origin main
    git push origin main
    git rebase -i main # save when prompted, [ESC + x]
    ```

<br />

# :alembic: Practice lab

The purpose of the practice is to start building a markdown user guide using Git features.

- [Create a Git (local) repository](../labs/lab_03a_creating_a_git_repository.md)
- [Create a GitHub (remote) repository](../labs/lab_03b_creating_a_github_repository.md)


# :books: References
- [Git Basics - Getting a Git Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository) 
- [GitHub Docs- Create a repo](https://docs.github.com/en/get-started/quickstart/create-a-repo) 

 
<br />

:arrow_backward: [back to index](../README)

[^1]: As a good practice, add clear and specific comments anytime changes happen. Consider other people who could contribute to the work you have done already and want to understand, in detail, what kind of changes they are managing.

