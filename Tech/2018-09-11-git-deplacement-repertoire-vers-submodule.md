Title:  "git: Déplacement d'un répertoire vers un submodule"
Date:   2018-09-11 21:05:46 +0200
Tags: Git
Category: Développement


Solution utilisée:

<https://stackoverflow.com/questions/17413493/create-a-submodule-repository-from-a-folder-and-keep-its-git-commit-history>

Solution préconsisée par github:

<https://help.github.com/articles/splitting-a-subfolder-out-into-a-new-repository/>

Nettoyage de .git (500M+ pour mao)

<https://stackoverflow.com/questions/5277467/how-can-i-clean-my-git-folder-cleaned-up-my-project-directory-but-git-is-sti>

	 git rev-list --objects --all |     while read sha1 fname;     do          echo -e "$(git cat-file -s $sha1)\t$\t$fname";     done | sort -n > rev-list.out

<https://stackoverflow.com/questions/4515580/how-do-i-remove-the-old-history-from-a-git-repository>

<https://git-scm.com/book/en/v2/Git-Tools-Replace>
