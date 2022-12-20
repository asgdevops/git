# 8. First document version

Version control in Git is handled by hash algorithms to ensure integrity.
Any changes produces a different hash identifier (checksum SHA-1).
The hash identifier (SHA) has a snapshot with the changes made so far.


The changes workflow has three main **states** for the local repository. Those changes can be stored in a central repository named remote repository in GitHub. As a result, there are other steps for syncronizing the local repository with the remote one. (_sync between Git and GitHub_)

## Git state tree
  
|#|State|Description|Area name|
| --|--|--|--|
|1|Modified|Means the file was modified but not saved in the Git database yet|Working directory|
|2|Staged|The modified file is marked to be commited on the next step (_marked for review before saving it_)|Staging area|
|3|Committed|The modifications are now saved in Git database|Git local repository (_under `.git` directory_)|

## Steps to save a new version in Git database

_In this example we will use a file in JSON format._

1. Initialite Git.

    - Create your working directory
    
    ```bash
    mkdir -p ~/portfolio/git/labs
    ```

    - Create your working directory
    
    ```bash
    mkdir -p ~/portfolio/git/labs
    ```

2. Create an example of a JSON file.

    ```json
    {
        "name": "great_team",
        "description": "This is an example of a great team",
        "active":true,
        "elements":4,
        "members": ["Joe", "Joyce", "Jose", "Juji"],
        "action_items": [
            {
            "action":"grettings",  
            "who":"Joyce", 
            "what": "Says Hi! to everyone in the room"
            }
        ]
    }
    ```

3. Add the file to the Git **Staging area**.

- Verify the current
```bash
git status
```

3. 3. c

<br/>

# Hands-on labs

- [Create a personal access token](labs/lab_05_create_a_token.md)

# :books: References

- [GitHub Docs - Create a personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

<br />

:arrow_backward: [back to index](README.md#00-toc)
