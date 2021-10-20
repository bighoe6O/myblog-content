Title:  Synchronisation des depots Git
Date:   2018-10-05 23:05:20 +0200
Tags: Git
Slug: tech-git-repo-sync
Category: Tech




```bash
#!/bin/bash
# ~git/bin/git-push-pi0.sh

pushd ~/repositories
#prefix=scans
#prefix="mysensors-"
prefixes="mao- mysensors- pio- arduino roaming myblog outils scripts musique"
for p in ${prefixes}; do
    prefix=$p
    for f in ${prefix}*; do
        if [ -d "$f" ]; then
            pushd $f;
            echo  --- $f ---;
            echo git push --mirror git@pi0:$f
            git push --mirror git@pi0:$f
            echo "ret: $?"
            popd
        fi
    done
done
popd
```

```ruby
# Rakefile

task :mirror do
  Dir.chdir("/home/git/repositories")
  mydirs = Rake::FileList['*.git']
  mydirs.exclude('gitolite-admin.git')
  mydirs.exclude('serveurs.git')

  mydirs.each do |mydir|
    Dir.chdir(mydir) do
      repo_name = mydir.gsub('.git', '')
      sh "git push --mirror git@pi0:#{repo_name}"
    end
  end
end
```

```python
# git-mirror.py
import os
import subprocess

host='stephane-lenovo.local'

os.chdir('~/repositories')
dirs = os.listdir()
for dir in dirs:
    subprocess.run(['git', '-C', mydir, 'push', '--mirror', 'git@{}:{}'.format(host, mydir)], capture_output=True)


Script d'ajout des répertoires manquants à la configuration
```python

with open('liste-todo.txt', 'r') as f:
    myrights = '''repo {prjname}
    RW+ = @priv
'''
    
    lines = f.readlines()
    lines = [l.replace('\n','').replace('.git', '') for l in lines]
    for line in lines:
        print(myrights.format(prjname=line))
```
