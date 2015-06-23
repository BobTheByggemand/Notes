__Stuff__

Go see the wiki (click the book icon on the right)

[Installation of Caffe in KUbuntu virtual machine](https://github.com/BVLC/caffe/wiki/Ubuntu-14.04-VirtualBox-VM)

Git crap:

You want to du a 'git pull', but you have made changes to your local repo that are not committable yet. So you do a 'git stash' a 'git pull' and a 'git stash apply'. Unfortunately there are merge conflicts during the stash apply. One of these, in the file toto.txt, doesn't really matter. You would like to ignore your old changes and get a clean copy from the distant repo. So you try:

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

Now wasn't that easy and intuitive like the rest of git?
