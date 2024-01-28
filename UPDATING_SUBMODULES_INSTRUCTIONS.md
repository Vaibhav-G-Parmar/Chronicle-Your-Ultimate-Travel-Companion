To update a submodule in a Git repository to its latest commit, you can use the following commands:

1. Navigate to the root directory of your main repository.

2. Use the following command to fetch the latest commits from the submodule's remote repository and update the submodule to the latest commit:

   ```bash
   git submodule update --recursive --remote
   ```

   The `--recursive` option ensures that all submodules are updated, and `--remote` fetches the latest commits from the submodule's remote repository.

   If you want to update only a specific submodule, you can use:

   ```bash
   git submodule update --remote path/to/submodule
   ```

3. After updating the submodule, navigate to the submodule's directory:

   ```bash
   cd path/to/submodule
   ```

4. If the submodule has its own branches, you might want to check out the branch that you want to use:

   ```bash
   git checkout master  # Replace 'master' with the desired branch name
   ```

5. Finally, go back to the main repository's root directory:

   ```bash
   cd ..
   ```

Now, your main repository should be updated to the latest commit of the submodule. Don't forget to commit the changes in the main repository to record the new submodule commit hash.

```bash
git add path/to/submodule
git commit -m "Update submodule to latest commit"
git push
```

These commands assume that the submodule is configured properly in your Git repository and that it has a valid remote repository. If the submodule hasn't been initialized or updated before, you may need to run `git submodule init` before updating it.