Title:  Lektor
Date:   2018-10-07 07:28:15 +0200
Tags: CMS


<https://headlesscms.org/>

## Lektor

<https://github.com/lektor/lektor>

	$ git clone https://github.com/lektor/lektor
	$ cd lektor
	$ virtualenv venv
	$ . venv/bin/activate
	$ pip install --editable .
	$ make build-js
	$ make install-git-hooks
	$ export LEKTOR_DEV=1
	$ cp -r example example-project
	$ lektor --project example-project server
	
## Coisas

<https://github.com/fiatjaf/coisas>

