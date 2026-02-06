Migrating a Git repository involves several steps to ensure data preservation. Here’s a detailed guide:

**Step-by-Step Migration Process**

1.  **Clone the Old Repository:**
    *   Create a local mirror of the repository using:
        ```bash
        git clone --mirror <old-remote-url>
        cd <repository-name>.git
        ```
    *   The `--mirror` flag ensures a complete copy of branches and tags.

2.  **Add the New Remote:**
    *   Configure the new server in your local repository:
        ```bash
        git remote add new-origin <new-remote-url>
        ```

3.  **Push to the New Remote:**
    *   Transfer the entire repository, including history, to the new server:
        ```bash
        git push --mirror new-origin
        ```

4.  **Verify Migration:**
    *   Confirm the migration's success by cloning from the new server:
        ```bash
        cd ..
        git clone <new-remote-url> <new-repository-name>
        cd <new-repository-name>
        git branch -a  # Check branches
        git tag -l    # Check tags
        ```

5.  **Update Local Configurations:**
    *   If other local clones exist, update their remote URLs:
        ```bash
        git remote set-url origin <new-remote-url>
        ```

6.  **Inform Team:**
    *   Notify team members to update their clones with:
        ```bash
        git remote set-url origin <new-remote-url>
        ```

**Summary of Commands**

*   Clone old remote:

    ```bash
    git clone --mirror <old-remote-url>
    cd <repository-name>.git
    ```

*   Add new remote:

    ```bash
    git remote add new-origin <new-remote-url>
    ```

*   Push to new remote:

    ```bash
    git push --mirror new-origin
    ```

*   Verify migration:

    ```bash
    cd ..
    git clone <new-remote-url> <new-repository-name>
    cd <new-repository-name>
    git branch -a
    git tag -l
    ```

*   Update local configs:

    ```bash
    git remote set-url origin <new-remote-url>
    ```

By following these steps, you can successfully migrate your Git repository, preserving its history.
