# Working with versions

6. Add a new row to the `first.txt` file (new version).

    ```bash
    echo "Now adding a new row." >> first.txt
    ```

7. Verify the status.

    ```bash
    git status
    ```

8. Compare the version differences between the saged file and the commited one.

    ```bash
    git diff --staged
    ```

9. Compare the version differences between the saged file and the commited one.

    ```bash
    git commit -m 'Adding a new row'
    ```