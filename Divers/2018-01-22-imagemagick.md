Title:  Image Magick
Tags: Images
Date:   2018-01-22 09:56:34 +0100
Category: Graphisme

# Resize image

	magick .\raspberry-pi-pico.jpg -resize 50%x50% .\raspberry-pi-pico-sm.jpg

# Conversion de multiples jpg vers un pdf

	convert *.jpg foo.pdf
	convert -resize 50%x50% *.jpg attestation-employeur.pdf
	
	magick convert -density 96 -resize 595x842 *.jpg fiches-de-paie.pdf

<https://www.imagemagick.org/Usage/resize/#shrink>

	for i in "Alone Together.png" ; do convert "$i" -resize 850x1100\>  "shrink/$i" ; done 
	for i in *.png; do convert "$i" -level-colors "#c8c8c8,white" "1bit/$i"; done
	for i in *.png; do  convert -chop 0x100 -gravity South "$i" "chop/$i"; done
	python $SCRIPTS/scripts/test/html-test.py > test.html
	wkhtmltopdf.exe -R 0 -B 0 -L 0 -T 0 toc ./test.html "Répertoire Jazz.pdf"	

Création des thumbnails

	mogrify  -format gif -path thumbs -thumbnail 100x100 *.jpg
