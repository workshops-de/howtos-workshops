# How to updates the solution tags for our Workshops

To reduce work all example solutions in our workshops.de classroom are linked to tags not commits or files. 
So you can rewrite the commit history with `rebase` without touching anything else.
It may feels a bit complecated sometimes but it's way easier then manually updating it in every task ;) 

Please replace %COMMIT-HASH-OF_YOUR-INITAL-COMMIT% with our actual commit hash ;)

1. `git rebase -i %COMMIT-HASH-OF_YOUR-INITAL-COMMIT%`
2. Change `pick` to `edit` at the tasks you want to change
3. Do your changes
4. `git commit --all --amend`
5. `git rebase --continue`
6. Fix possible merge error if needed
7. Repeat on step 3 if you edit more than one commits
8. run `./recreate-tags.sh`
9. `git push -f`
10. `git push --tags -f`
