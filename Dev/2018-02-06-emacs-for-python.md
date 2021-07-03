x1Title:  Emacs for python
Date:   2018-02-06 18:28:52 +0100
Modified: 2019-07-31 16:57:00 +0200
Tags: Emacs, Editeurs


* [Python programming in Emacs](https://www.emacswiki.org/emacs/PythonProgrammingInEmacs)
* [Emacs for Python](https://github.com/gabrielelanaro/emacs-for-python) Fonctionne bien, fournit la complétion (M-/)
* [abl-mode](https://github.com/afroisalreadyinu/abl-mode)
* [Elpy](https://github.com/jorgenschaefer/elpy)

flycheck-pychekers

    (global-flycheck-mode 1)
    (with-eval-after-load 'flycheck
    (add-hook 'flycheck-mode-hook #'flycheck-pycheckers-setup))

# [Elpy](https://github.com/jorgenschaefer/elpy)

* Tags fonctionnels
* Checkers fonctionnels

Problème:

* [Elpy is not using python from my activated virtualenv](https://github.com/jorgenschaefer/elpy/issues/538)
