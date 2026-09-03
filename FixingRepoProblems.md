## Fixing GitHub Sync Problems on Pitt CRC OnDemand

First, make sure you still have access to the **course repository on GitHub**. If you cannot access it, contact the TA or instructor.

If you are having problems with `git pull` or `git push` between your **local repository on Pitt CRC OnDemand** and your **GitHub fork**, use the following procedure.

### If your local repository is causing problems

1. Find your local repository on CRC OnDemand.

2. **Make a backup before deleting anything.** For example, create a backup folder:
   ```bash
   mkdir -p ~/backup
   ```

3. Copy your entire repository into the backup folder:
   ```bash
   cp -r ~/Git/reponame ~/backup/
   ```

4. Confirm that your files are safely stored in:
   ```text
   ~/backup/reponame
   ```

5. Delete the problematic local repository:
   ```bash
   rm -rf ~/Git/reponame
   ```

   **Be careful with `rm -rf`. Double-check the path before pressing Enter so that you do not accidentally delete the wrong folder.**

6. Go to GitHub, open **your fork**, and copy its clone URL. Then clone a fresh local copy:
   ```bash
   cd ~/Git
   git clone YOUR_GITHUB_REPOSITORY_URL
   ```

7. Enter the newly cloned repository:
   ```bash
   cd reponame
   ```

8. Confirm that Git is working and that your local repository is connected properly:
   ```bash
   git status
   git pull
   ```

   A fresh `git clone` already contains the current files from GitHub, so the `git pull` here is mainly a check that communication with GitHub is working correctly.

9. Copy any files that you changed from your backup into the new repository. **Copy only the files you need rather than replacing the entire newly cloned repository.**

10. Check what has changed:
    ```bash
    git status
    ```

11. Add, commit, and push your changes:
    ```bash
    git add .
    git commit -m "Update work"
    git push
    ```

### If your GitHub fork is not syncing with the course repository

If your GitHub fork is behind the course repository, **do not delete your fork immediately**.

1. Open **your fork** on GitHub.

2. Look for the **Sync fork** button near the top of the repository page.

3. Select **Sync fork → Update branch**.

4. After GitHub updates your fork, return to CRC OnDemand and run:
   ```bash
   cd ~/Git/reponame
   git pull
   ```

5. Check that your files and Git status look correct:
   ```bash
   git status
   ```

If **Sync fork** does not work, ask a TA or instructor for help before deleting anything.

### Last resort: delete and recreate your fork

Use this procedure only if your fork cannot be repaired or synchronized normally.

1. Complete the backup steps above first so that all of your local work is safely stored in:
   ```text
   ~/backup/reponame
   ```

2. On GitHub, delete **your fork** of the course repository.

3. Return to the **course repository** on GitHub and fork it again to your GitHub account.

4. Delete your old local repository if you have not already done so. **Double-check the path before using `rm -rf`.**

5. Clone your newly created fork:
   ```bash
   cd ~/Git
   git clone YOUR_NEW_FORK_URL
   ```

6. Copy your changed files from:
   ```text
   ~/backup/reponame
   ```
   into the newly cloned repository. Copy only the files that contain your work.

7. Check what has changed:
   ```bash
   git status
   ```

8. Add, commit, and push your restored work:
   ```bash
   git add .
   git commit -m "Restore my work"
   git push
   ```

**Important:** Always make a backup of your work before deleting either a local repository or a GitHub fork. Deleting and recreating a fork should be a last resort.
