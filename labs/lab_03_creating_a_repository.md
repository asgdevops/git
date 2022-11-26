# 3. Creating a repository

## Goal 
- Create a Git repository in your local machine.
- Create a new file and add it to the Git database.
- Verify the file version in Git.

## Steps

1. Create a working directory.

    ```bash
    mkdir -p $HOME/git/project1
    cd $HOME/git/project1
    ```

2. Initialize Git.

    ```bash
    git init
    ```

3. Rename the `master` branch to `main`

    ```bash
    git branch -m main
    ```

4. Feed the Git database

   - Create a new file or modify an existing one.

    ```bash
    echo "This is the git first file" > first.txt
    ```

   - Review the change status.

    ```bash
    git status
    ```

   - Add the changes to the Staging Area.

    ```bash
    git add first.txt
    ```

   - Commit the changes.

    ```bash
    git commit -m 'Initial commit'
    ```

5. Review the changes log.

    ```bash
    git log
    ```

<br />

:arrow_backward: [back](../03_creating_repositories.md)
