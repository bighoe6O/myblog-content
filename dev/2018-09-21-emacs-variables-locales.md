Title:  "Emacs: Variables locales"
Date:   2018-09-21 08:56:48 +0200
Category: Dev
Tags: Emacs


<https://emacs.stackexchange.com/questions/24907/how-to-use-dir-locals-el-with-projectile>

<https://www.gnu.org/software/emacs/manual/html_node/emacs/Directory-Variables.html>

```
;; .dir-locals.el
((nil
  (easy-jekyll-basedir . "e:/repo/myblog-dev/")
))
```

# Régénération des tags

<https://stackoverflow.com/questions/2550474/is-it-possible-to-auto-regenerate-and-load-tags-table-in-emacs-rather-than-havin>

```
;; .dir-locals.el
((nil . ((tags-cmd . "etags -R *.py"))))
```

```lisp
;; init.el
;; Regénérer les tags
(defvar tags-cmd "etags -R 2>/dev/null")

(defun regen-tags ()
  "Regenerate the tags file for the current working directory"
  (interactive)
  (let ((tag-file (concat default-directory "TAGS")))
    (shell-command tags-cmd)
    (visit-tags-table tag-file)))

(global-set-key (kbd "C-c t r") 'regen-tags)
```

Rechargement automatique de la table des tags

```lisp
(setq tags-revert-without-query t)
```
