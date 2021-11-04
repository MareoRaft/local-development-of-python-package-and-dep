Imagine you are developing project A, and project A depends on project B which you are also developing.  How can you locally develop both at the same time?

This repo just shows a very basic example of that in python.

`repo-b` -> This folder is an example of the repo for project B.  It exposes a package called **b**.

`repo-a` -> This folder is an example of the repo for project A.  It imports and uses **b**.

Directions:

1. `cd repo-b`
2. run `python setup.py sdist bdist_wheel` (actually i don't know if this is necessary or not)
3. `cd repo-a`
4. run `pip uninstall --yes b && pip install -e ~/repos/local-development-of-python-package-and-dep/repo-b` or similar
5. run `python main.py` and observe that everything works

So the real secret is the `-e` or `--editable` flag.

References:
* https://stackoverflow.com/questions/15031694/installing-python-packages-from-local-file-system-folder-to-virtualenv-with-pip
* https://www.freecodecamp.org/news/build-your-first-python-package/
