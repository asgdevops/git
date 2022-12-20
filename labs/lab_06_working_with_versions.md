# Working with versions

## Goal 
- Create a Git repository in Github named `backup` using GitHub CLI.
- Export your browser `bookmarks.html` file to the `backup` repository.
- Sync the local repository with the GitHub remote one.

## Steps


1. Install GitHub CLI.

- Debian/Ubuntu

    ```bash
    sudo apt install -y gh
    ```

- RHEL/CentOS

    ```bash
    yum install -y gh
    ```

2. Login to your gitHub repository using GitHub CLI

    ```bash
    gh auth login -w
    ```

   _Provide the credentials in the web browser._

3. Create the remote repository

    ```bash
    gh repo create backup --public --clone
    ```

4. Rename the master branch to **main**

    ```bash
    cd backup
    git branch -m main
    ```

5. Verify the remote repository was set up

    ```bash
    git remote -v
    ```

6. Export your favorites's browser bookmarks to the "**backup**" repository just cloned. 

    _For standard convention, let us use the `bookmarks.html` as the exported file name._

   - [Exporting bookmarks from **Chrome**](https://support.google.com/chrome/thread/31505914?hl=en)
   
   - [Export **Firefox** bookmarks to an HTML file to back up or transfer bookmarks](https://support.mozilla.org/en-US/kb/export-firefox-bookmarks-to-backup-or-transfer)
   
   - [Exporting Bookmarks and Settings from **Opera** to Other Browsers](https://forums.opera.com/topic/40531/exporting-bookmarks-and-settings-from-opera-to-other-browsers)

    - [How do I EXPORT Bookmarks/Favorites from Microsoft **EDGE** Browser?](https://answers.microsoft.com/en-us/windows/forum/all/how-do-i-export-bookmarksfavorites-from-microsoft/1535cde2-68d5-4a31-9110-2bf334ab5dc6)

7. Create the initial Git `bookmarks.html` version.

   - Locate to the backup cloned directory.

    ```bash
    cd backup
    ```

   - Review the change status.

    ```bash
    git status
    ```

   - Add the changes to the Staging Area.

    ```bash
    git add bookmarks.html
    ```

   - Commit the changes.

    ```bash
    git commit -m 'Initial commit'
    ```

6. Review the changes log.

    ```bash
    git log
    ```

7. Add a new row to the `first.txt` file (new version).

    ```bash
    echo "Now adding a new row." >> first.txt
    ```

8. Verify the status.

    ```bash
    git status
    ```

9. Compare the version differences between the saged file and the commited one.

    ```bash
    git diff --staged
    ```

10. Compare the version differences between the saged file and the commited one.

    ```bash
    git commit -m 'Adding a new row'
    ```