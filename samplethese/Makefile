# * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
#
# Make file simple pour LaTeX
#
# 	Compilation simple du document
# 	Compilation complete du document
#
# * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 

# fichier principal
TEX=these_simple

# compilateur latex
CC=pdflatex

# defaut = aide :
help:
	@echo
	@echo " Compilation du rapport, regles :"
	@echo
	@echo " simple  : compilation une seule fois"
	@echo " all     : compile et met la biblio et les references a jour (long)"
	@echo " purge   : effacement des fichiers autres que .tex et .pdf (.aux .log .out .toc ..."
	@echo

# compilation simple
simple: $(TEX).tex
	$(CC) $(TEX)

# compilation complete, on passe plusieurs fois pour les references croisee plus bibtex pour la
# biblio
all: $(TEX).tex
	$(CC) $(TEX)
	$(CC) $(TEX)
	@bibtex $(TEX)
	$(CC) $(TEX)
	$(CC) $(TEX)
	@echo
	@echo 
	@echo "fin ;)"
	@echo


# efface les fichiers .log .aux .toc .bbl .blg 
.PHONY: purge
purge:
	@rm -vf *.aux $(TEX).bbl $(TEX).blg $(TEX).log $(TEX).out $(TEX).toc $(TEX).mtc* $(TEX).lof $(TEX).lot $(TEX).maf
	@echo "done"

