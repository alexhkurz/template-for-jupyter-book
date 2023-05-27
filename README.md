# README

[This](https://github.com/alexhkurz/template-for-jupyter-book) is the template I copy if I want to create a new jupyter book. More details and references to jupyter books I keep at [`introduction-to-jupyter-book`](https://github.com/alexhkurz/introduction-to-jupyter-book.git).

## setting things up

### copy the template

```
mkdir myNewFolder
cd myNewFolder
cp -r ../template-for-jupyter-book/. .
rm -rf .git
ls -a
```

Have a look at all files copied. Make sure this includes a `.gitignore` but not a `.git`.

Adapt the contents of the files `README.md`, `_config.yml`, `_toc.yml`, `intro.md`, `contents/section1.md`. Possibly rename `section1.md` (in which case you also have to change `_toc.yml`).

### make a local git repository

```
git init
git add *
git commit -m "initial commit"
```

### make a copy of the repo "in the cloud"

Make a new [Github repo](https://github.com/). After registering/signing in, click on "+" and "New repository". For this repo, I chose `template-for-jupyter-book` as the name and then clicked the green button "Create repository". Then I copy pasted from the page that Github presented to me to my commandline

```
git branch -M main
git remote add origin https://github.com/alexhkurz/template-for-jupyter-book.git
git push -u origin main
```

Make sure to update `_config.yml` with the address of the Github repository, which for this repository was `https://github.com/alexhkurz/template-for-jupyter-book.git`.

## create the book

To create the book locally and open it in my browser, I run (the `open` command may be specific to a mac)

```
jb build . ; open _build/html/index.html
```

## publish the book

To publish the book, install `ghp-import` with `pip install ghp-import`. Then run 

```
ghp-import -n -p -f _build/html
```

This makes the [book available online](https://alexhkurz.github.io/template-for-jupyter-book). It also keeps the source files in the `main`-branch separate from the files in `_build` in the `gh-pages` branch (Github knows that it should use the `gh-pages` branch to show the book as a webpage).

## important commands

If, for example, the table of contents in the left-hand pane behaves in a strange way, clean out `_build` by running `jb clean .`

