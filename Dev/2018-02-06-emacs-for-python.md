Title:  Emacs for python
Date:   2018-02-06 18:28:52 +0100
Updated: 2019-07-29 19:20:20 +0200
Tags: Emacs, Editeurs


<https://www.emacswiki.org/emacs/PythonProgrammingInEmacs>

<https://github.com/gabrielelanaro/emacs-for-python>

Fonctionne bien, fournit la complétion (M-/)

<https://github.com/afroisalreadyinu/abl-mode>

flycheck-pychekers

    (global-flycheck-mode 1)
    (with-eval-after-load 'flycheck
    (add-hook 'flycheck-mode-hook #'flycheck-pycheckers-setup))

# [Elpy](https://github.com/jorgenschaefer/elpy)

* Tags fonctionnels
* Checkers fonctionnels
