#------------------------------------------------------------------------------
# Makefile generique pour c++
#------------------------------------------------------------------------------

# fichiers cpp et hpp dans le dossier src
CPP_FILES := $(wildcard src/*.cpp)

#fichiers objet dans un dossier obj
OBJ_FILES := $(patsubst src/%.cpp, obj/%.o, $(CPP_FILES))

# commandes de compilation
CC_FLAGS = -O1 -Wall -std=c++11 
# -O1 compromis entre rapidite et optimisation de code
# -Wall affichier tous les warnings
# -std=c++11 compiler les classes STL en mode C++11

# commandes d'edition de lien (décommenter pour une utilisation de la SFML)
LD_FLAGS = -lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio


application: $(OBJ_FILES)
	g++ $(LD_FLAGS) -o $@ $^

obj/%.o: src/%.cpp
	g++ $(CC_FLAGS) -c -o $@ $<

clean:
	rm -rf obj/*.o application
