#	Para só fazer make uma vez, o nome da etiqueta (Ex: "./bin/test")
# tem de ter o mesmo nome do executável. Isto porque o GCC toma essa 
# etiqueta como sendo o nome do programa, e, se não o encontrar, 	
# faz novo make. 

# 	No all só se podem usar etiquetas.
#	Comandos têm de ser escritos dentro das etiquetas.

all: bin ./bin/gerador ./bin/parque 

bin:
	mkdir -p bin

### Criação dos executáveis
# Para cada ficheiro fazer uma nova etiqueta com o caminho.
#<caminho do executável>: <ficheiros.o>
#	gcc -Wall <ficheiros.o> -o <caminho> -lm -pthread

./bin/gerador: gerador.o 
	gcc -Wall gerador.o -o ./bin/gerador -lm -pthread -lrt 

./bin/parque: parque.o
	gcc -Wall parque.o -o ./bin/parque -lm -pthread -lrt 

### Criação dos ficheiros objeto
#<ficheiro.o>: <ficheiros.c> <ficheiros.h>
#	gcc <ficheiros.c> -c

gerador.o: gerador.c shared.h
	gcc gerador.c -c

parque.o: parque.c shared.h
	gcc parque.c -c 


### Apagar ficheiros objeto

clean: 
	rm *.o
	rm -r bin/*
