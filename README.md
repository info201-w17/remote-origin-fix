# Remote Origin Fix

This is the fix if you get an error that looks similar to this:

```
remote: Permission to info201-w17/module3-markdown.git denied to {YOUR-USERNAME}.
fatal: unable to access 'https://github.com/info201-w17/module3-markdown.git': The requested URL returned error: 403
```

Looks scary, right? However, don't fret! There is a really _**easy**_ fix for this!


But first, let's understand why we're having this problem in the first place. The main reason that you're unable to `push` to this repository is that it is **not** yours! Even though you may have forked the module, you copied the wrong link to clone down from GitHub, leaving your forked repository to not be cloned to your computer. However, this isn't a big deal, since the repository is the same... After all you did fork it directly!

```
Note: if you did not fork the repository, you need to do that now!
```

Take a look at the url:
`https://github.com/info201-w17/module3-markdown.git`

Notice that after `github.com`, the username that is specified is `info201-w17` and not your username. However, if you go to `https://github.com/{YOUR-USERNAME}/module3-markdown.git` a repository should exist!

The fix for this is that we need to change what your computer thinks the `origin` of your repository is.

Run the command `git remote -v` and notice that the url that you were not able to push to is there!

So here are the steps to being able to push to your forked repository:

1. Copy the URL from the GitHub repository as if you were going to `clone` it.

2. Navigate to the repository directory in your terminal. (Chances are, you're already there since you're on this fix page)

3. Confirm that the `remote` pointer is pointing at the wrong place by running `git remote -v` and seeing what GitHub username is in the URL

4. Set your forked repository to the origin by running
```
git remote set-url origin {FORKED-REPO-URL}
```

5. Run `git remote -v` to confirm that `origin` points to your forked repo

6. Run `git push origin master` and it should work!
