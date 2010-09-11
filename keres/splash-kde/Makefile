#!/usr/bin/make -f

THEME= aptosid-keres
CONTROLDIR= 1920x1200

all: prepare background letters

prepare:
	$(RM) -r $(THEME)
	mkdir -p $(THEME)/$(CONTROLDIR)
	mkdir -p $(THEME)/1920x1080
	mkdir -p $(THEME)/1600x1200
	mkdir -p $(THEME)/1280x1024
	cp Theme.rc $(THEME)/
	cp Preview.png $(THEME)/
	cp description.txt $(THEME)/$(CONTROLDIR)
	ln -s ../$(CONTROLDIR)/description.txt $(THEME)/1600x1200/description.txt

background:
	ln -s ../1600x1200/$@.png $(THEME)/1280x1024/$@.png
	inkscape --without-gui --export-png="$(THEME)/1600x1200/$@.png" $@.svg
	ln -s ../$(CONTROLDIR)/$@.png $(THEME)/1920x1080/$@.png
	inkscape --without-gui --export-png="$(THEME)/$(CONTROLDIR)/$@.png" $@-wide.svg

letters:
	./make_the_letters

clean:
	$(RM) -r $(THEME)
