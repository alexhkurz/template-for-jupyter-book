# README

(under construction)

This is the template I copy if I want to create a new jupyter book. More details and references to jupyter books I keep at [`introduction to jupyter book`]().

```
mkdir myNewFolder
cd myNewFolder
cp -r ../template-for-jupyter-book/* .
```

Adapt the files `README.md`, `_config.yml`, `_toc.yml`, `intro.md`, `contents/section1.md`.

```
git init
git add *
git commit -m "initial commit"
```


```
jb build . ; open _build/html/index.html
```

### publishing

(There is sth missing here.) After installing `ghp-import` with
`pip install ghp-import` publish the book by running 

```
ghp-import -n -p -f _build/html
```

This makes the [book available online](https://alexhkurz.github.io/mathematics-for-philosophers). It also keeps the source files in the `main`-branch separate from the files in `_build` in the `gh-pages` branch (Github knows that it should use the `gh-pages` branch to show the book as a webpage).

### important commands

If, for example, the table of contents in the left-hand pane behaves in a strange way, clean out `_build` by running `jupyter-book clean .`

### references

[Create your first book](https://jupyterbook.org/en/stable/start/your-first-book.html).

[Math and equations](https://jupyterbook.org/en/stable/content/math.html#math-and-equations).

[.gitignore](https://raw.githubusercontent.com/executablebooks/jupyter-book/master/.gitignore).

[Publish your book online](https://jupyterbook.org/en/stable/start/publish.html).

