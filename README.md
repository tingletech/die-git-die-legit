die-git-die-legit
=================

OK, so I've created a new repo on github, and I've cloned it:

```sh
git clone https://github.com/tingletech/die-git-die-legit.git
cd die-git-die-legit
```
change some files, commit and publish:

```sh
vi README.md
git commit -a -m"Commit."
git publish
```

Now I want to add some github pages for this repo. This is done by
the weird practice of creating a special branch called gh-pages and
then deleting everything on that branch.

Yes, really. Kinda scary. But it shouldn't be a problem, should it?
Because we are using a code revision system, so even if something
gets messed up, it's always possible to go back to an earlier
revision and do it from there.

```sh
cd ..
git clone https://github.com/tingletech/die-git-die-legit.git die-git-die-legit.pages
cd die-git-die-legit.pages/
```

```sh
git checkout --orphan gh-pages
git rm -rf .
echo "<html><body><h1>Die git, die\!</h1></body></html>" > index.html
git add .
git commit -a -m "First pages commit"
git publish gh-pages
```

While doing up these pages, we find some errors in the original
branch and fix them, which we push and commit.

```sh
cd ../die-git-die-legit
git commit -a -m"Commit"
git publish
```


