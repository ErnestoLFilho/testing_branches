# Feature branch test

### *\* I discovered how to merge orphan branch to another! \**

<hr>

### Steps to create orphan branch (commands are in **bold**):

1. **git checkout --orphan FEATURE**
2. **git rm -rf .** *⇒ your branch is clear and ready to work*
3. **git commit --allow-empty -m "ORPHAN FEATURE BRANCH READY!"** *⇒ The `--allow-empty` is needed only if you push it empty.*
4. **git push -u origin FEATURE**

<hr>

### Steps to merge back from orphan FEATURE to TARGET (commands are in **bold**):

1. **git checkout TARGET**
2. **git pull origin TARGET**
3. **git checkout FEATURE**
4. **git pull origin FEATURE** *⇒ By now we have both on your machine.*
5. **git checkout TARGET**
6. **git merge -X theirs FEATURE --allow-unrelated-histories** *⇒ `-X theirs` will overwrite FEATURE stuff onto TARGET if there are collisions. `--allow-unrelated-histories` forces merge to allow orphan to merge.*
7. (commit, if it opens Vim, just do `:qa` and enter)
8. **git push -u origin TARGET**
9. Happy day!

<hr>