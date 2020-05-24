This is a git tip in general I think, but since Heroku will auto-deploy your master branch it is especially useful there. Simply use the `:` to direct one branch to another.

```bash
git push -f heroku <branch>:master
```