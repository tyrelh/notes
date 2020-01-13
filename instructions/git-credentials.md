# Set up Git Credentials

Taken from [StackExchange](https://unix.stackexchange.com/questions/335704/how-to-set-up-username-and-passwords-for-different-git-repos)

Git has its own way of handling credentials using [`gitcredentials`](https://git-scm.com/docs/gitcredentials) (and typically ['git-credential-store'](https://git-scm.com/docs/git-credential-store)).

You specify your username using
```bash
git config credential.${remote}.username yourusername
```
and the credential helper using
```bash
git config credential.helper store
```
Specify `--global` if you would like to use this setting everywhere.

Then the first time you access a repo, git will ask for your password, and it will be stored (by default in `~/.git-credentials`). Subsequent accesses to the repository will use the stored password instead of asking you.

# Tips
Unset globally
```shell
git config --global --unset credentials.helper
```
Unset locally (in each repo)
```shell
git config --unset credentials.helper
```
Create credential file for each repo (in each repo)
```shell
git config credential.helper 'store --file ~/.git_reponame_credentials'
```