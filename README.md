__Stuff__

Go see the wiki (click the book icon on the right)

[Installation of Caffe in KUbuntu virtual machine](https://github.com/BVLC/caffe/wiki/Ubuntu-14.04-VirtualBox-VM)

__Git stuff 1:__

You are on a feature branch and you have made an unrelated change that you want to commit to master. Suppose 'git branch' tells you that you just have your feature branch and the master branch in your local repository. Then you switch to the master branch with the command

```
git checkout master
```

This will not delete any of your non-committed changes. Then you commit your unrelated change to the master branch like this:

```
git commit Path/To/File.cpp
```

Then you need to get your master branch up to date before you can push your commit to the server. Like this:

```
git pull
```

Hopefully there are no conflicts. You then push the change to the server (the remote repository).

```
git push
```

Then you go back to your feature branch:

```
git checkout feature/MyCoolFeature
```

And if you want to get all the recent stuff from the master branch on to your feature branch (with risk of conflict), you do:

```
git merge master
```



__Git stuff 2:__

You want to do a 'git pull', but you have made changes to your local repo that are not committable yet. So you do a 'git stash' a 'git pull' and a 'git stash apply'. Unfortunately there are merge conflicts during the stash apply. One of these, in the file toto.txt, doesn't really matter. You would like to ignore your old changes and get a clean copy from the distant repo. So you try:

```
git checkout -- toto.txt
```

but that doesn't work. So you try:

```
git merge --abort toto.txt
```

but obviously that is not the right thing to do either. It seems that what you need to do is:

```
git reset HEAD toto.txt
git checkout -- toto.txt
```

Now wasn't that easy and **intuitive** like the rest of git?
