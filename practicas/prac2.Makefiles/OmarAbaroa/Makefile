# Archivo Makefile simple

PROYECTO=muestreo
DESTDIR=/usr/local/bin
CFLAGS=-Wall
LDFLAGS=-lm
CC=gcc

all: $(PROYECTO)

%.o: %.c
	$(CC) -c $< $(CFLAGS)

#muestreo: muestreo.o procesamiento.o archivos.o
#muestreo: $(OBJECTS)
objects :=  $(patsubst %c,%o,$(wildcard *c))
muestreo: $(objects)
	$(CC) $^ -o $@ $(LDFLAGS)

.PHONY: clean

install: all
	if [ ! -d $(DESTDIR) ]; then \
		sudo mkdir $(DESTDIR); \
	fi; \
	sudo cp $(PROYECTO) $(DESTDIR)

unistall: 
	sudo rm $(DESTDIR)/$(PROYECTO)

clean:
	rm -f *.o $(PROYECTO)

