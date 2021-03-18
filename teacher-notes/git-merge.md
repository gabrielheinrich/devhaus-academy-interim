# Git Merge

## Steps

1. Create a new repository on github
2. Clone repository locally: git clone git@github.com/gabrielheinrich/recipe-merger
3. Create a first commit: touch README.md && git add . && git commit -m "My first recipe"
4. Publish the commit to github and confirm it's there: git push
5. Invite another developer to the repository by going to the repository settings on github.com under collborators
6. The other developer accepts the invite and is then not only able to clone the repository but also able to publish to it
7. Developer B clones the repository.
8. Developer B may add another commit and push it to the repository
9. Developer A still has the old version. After git fetch you can verify that master and origin/master have divergent changes
10. Developer A can update there local master by running from master: git merge origin/master: Fast Forward Merge
11. Next up both Developer A and Developer B will change something in the README.md file and commit it
12. Only one of them will be able to push their version of the branch (We push branches) the other one will be rejected
13. The rejected developer has to first fetch and merge the new changes into their version of the branch and push those changes (Three Way Merge)
14. Now let's do feature branches: Both Developer A and B create their own branches and add changes and push and add them
15. Then go through merges: First do it through the command line getting Developer B's changes into the master
16. Developer A create a pull request through github (merging should be locked because of merge conflicts)
17. Locally merge in Master into developer A's branch and then merge it
