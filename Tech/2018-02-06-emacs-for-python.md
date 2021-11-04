Title:  Emacs for python
Date:   2018-02-06 18:28:52 +0100
Modified: 2021-07-04 10:47
Tags: Emacs
Category: Développement


* [Python programming in Emacs](https://www.emacswiki.org/emacs/PythonProgrammingInEmacs)
* [Emacs for Python](https://github.com/gabrielelanaro/emacs-for-python) Fonctionne bien, fournit la complétion (M-/)
* [abl-mode](https://github.com/afroisalreadyinu/abl-mode)
* [Elpy](https://github.com/jorgenschaefer/elpy)


# flycheck-pychekers

    (global-flycheck-mode 1)
    (with-eval-after-load 'flycheck
    (add-hook 'flycheck-mode-hook #'flycheck-pycheckers-setup))

Filtrer les messages

## Mypy

    pip install mypy

configuration: 

    # ~/.config/mypy/config
    [mypy]
    ignore_missing_imports = True

## Pylint

Générer .pylinrc pour le projet:

    pylint --generate-rcfile > .pylintrc

Dans .pylintrc du projet modifier init-hook:

    init-hook='import sys; sys.path.append("/home/stephane/.local/share/virtualenvs/pypass--rJIKvrW/lib/python3.9/site-packages*")'

.pylintrc utilisateur

    # ~/.pylintrc
    [MESSAGES CONTROL]
    disable=too-many-ancestors
    disable=missing-function-docstring


# [Elpy](https://github.com/jorgenschaefer/elpy)

* Tags fonctionnels
* Checkers fonctionnels

Problème:

[Elpy is not using python from my activated virtualenv](https://github.com/jorgenschaefer/elpy/issues/538)

## GTags

[GTags for Python in Emacs](https://blade6570.github.io/soumyatripathy/blog_gnuglobal/gnu_global.html)
