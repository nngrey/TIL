#hg graft

Today, I needed to grab a data migration out of another branch but did not want to merge the entire branch into my branch. First, I had to find out the changeset number. I looked on bitbucket and found the commit number. I checked out the branch that contained the changeset and hit

```hg log | grep 43b6c43```
that gave me

```>changeset: 25970:43b6c43e4f39```

The first number is the id and is valid within the repository so that will work for this [situation](https://www.mercurial-scm.org/wiki/TutorialHistory).

Next, I checked out my branch and hit

```hg graft 25970```

 That's all it took. Single changeset merged. There is a flag to make a commit, but I did not use it. More at [graft](https://selenic.com/hg/help/graft).