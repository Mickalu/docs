# Git reset 

Reset permit to not see or delete commit.
If you need to commit changed because of a WIP moment you can do this :

```
git add . 
git commit -m "WIP"
git switch main
work work work
git add . 
git commit -m "fix: fix my bug"
git push 
git switch dev
git reset --soft HEAD^
work work 
git add . 
git commit -m "feature: feature done"
git push 
```

If you merge dev into main you will not have the commit "WIP" but you get all changes
