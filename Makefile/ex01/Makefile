# Define el nombre del ejecutable
# Define las flags del compilador
# Lista de archivos fuente del proyecto
# Regla principal que compila el programa
# Elimina el archivo ejecutable
# Ejecuta clean y luego all para recompilar todo
# Ejecuta el programa
# Declara las reglas que no generan archivos


# Define el nombre del ejecutable
NAME = program

COMPILER = cc

# Define las flags del compilador
CFLAGS = -Wall -Werror -Wextra

# Lista de archivos fuente del proyecto
SRC = src/main.c src/utils.c

# Regla principal que compila el programa
all: $(NAME)

	$(NAME):
		$(COMPILER) $(CFLAGS) $(SRC) -o $(NAME)

# Elimina el archivo ejecutable
clean:
	rm -f $(NAME)

# Ejecuta clean y luego all para recompilar todo
re: clean all

# Ejecuta el programa
run: $(NAME)

	./$(NAME)

# Declara las reglas que no generan archivos
.PHONY: all clean re run
