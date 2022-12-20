# 4. SSH GitHub authentication

# Steps
1. Open a local terminal and run the command below.

    ```bash
    ssh-keygen -t ed25519 -C "your.email@ccount" -f ~/.ssh/ed25519
    ```

2. Enter a **passphrase** (_password_) and confirm that.

    ![ssh](images/github_ssh_01.png)

3. Verify a key pair files were created. 
   
   - The private key `~/.ssh/ed25519`
   
   - The public key `~/.ssh/ed25519.pub`

    ```bash
    ls -l ~/.ssh/ed25519*
    ```

    ![ssh](images/github_ssh_02.png)

4. Go to [GitHub](https://github.com/ ) 

5. Open the main menu and select **settings**.

    ![ssh](images/github_ssh_03.png)

5. Select the **SSH and GPG keys** option.

    ![ssh](images/github_ssh_04.png)

6. Click the **New SSH Key** button.

    ![ssh](images/github_ssh_03a.png)

7. Back to your terminal, take the public key from `your terminal`

    ```bash
    cat ~/.ssh/ed25519.pub
    ```

    ![ssh](images/github_ssh_04a.png)

8. Enter the **Title**, **Key type** and **Key**. (_paste the public key_)

    ![ssh](images/github_ssh_05.png)

9. Verify the SSH key was added to GitHub.

    ![ssh](images/github_ssh_06.png)

10. Switch back to your terminal and test the SSH Key connection to GitHub.


    ```bash
    ssh -i ~/.ssh/d25519 -T git@github.com
    ```

    - Where
      - `-i` tells SSH which key you are using.
      - `-T` means test.

    - Type the pasphrase used when the SSH key was created.

        ![ssh](images/github_ssh_07.png)

    - Now you are set.

<br />

# :books: References
- [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

<br />

:arrow_backward: [back](README.md#00-toc)
