# Define el nombre del ejecutable
# Define el compilador a utilizar
# Define las flags del compilador
# Define el comando para eliminar archivos
# Define la ubicación de las librerías
# Define la ubicación de la librería printf
# Define el archivo de la librería printf
# Define el comando para llamar al Makefile de printf
# Define los includes para la compilación
# Define la ruta a las librerías
# Define las librerías a enlazar
# Define la carpeta donde están los archivos fuente
# Lista los archivos fuente
# Concatena la ruta con los nombres de archivos
# Genera los nombres de los archivos objeto

# -- RULES -- #
# Regla principal que compila el programa y la librería printf
# Regla patrón para compilar cada archivo .c a .o
# Enlaza los objetos con la librería para crear el ejecutable
# Elimina los archivos objeto y limpia printf
# Limpieza completa: elimina objetos y ejecutable
# Recompila todo desde cero
# Declara reglas que no generan archivos

# -- UTILS -- #
# Ejecuta el programa

# -- LIBRARIES -- #

# Compila la librería printf
# Recompila la librería printf
# Limpia los objetos de printf
# Limpia completamente printf


# Define el nombre del ejecutable
NAME = complex

# Define el compilador a utilizar
COMPILER = cc

# Define las flags del compilador
FLAGS = -Wall -Werror -Wextra

# Define el comando para eliminar archivos
RM = rm -rf

# Define la ubicación de las librerías
LIB_FOLDER = inc

# Define la ubicación de la librería printf
LIB_PRINTF_FOLDER = .$(LIB_FOLDER)/printf

# Define el archivo de la librería printf
LIB_PRINTF = $(LIB_PRINTF_FOLDER)/libftprintf.a

# Define el comando para llamar al Makefile de printf
LIBFT_MAKEFILE = make -C $(LIB_PRINTF_FOLDER)

# Define los includes para la compilación
INCLUDES = -I$(LIB_PRINTF_FOLDER)

# Define la ruta a las librerías
LIBPATH = -L$(LIB_PRINTF_FOLDER)

# Define las librerías a enlazar
LIBS = -lftprintf

# Define la carpeta donde están los archivos fuente
SRC_FOLDER = src/

# Lista los archivos fuente
SRC_FILES = main.c \

# Concatena la ruta con los nombres de archivos
SRCS = $(addprefix $(SRC_FOLDER), $(SRC_FILES))

# Genera los nombres de los archivos objeto
OBJ_FILES = $(SRC_FILES:.c=.o)

# -- RULES -- #
# Regla principal que compila el programa y la librería printf
all: $(NAME) printf-all

# Regla patrón para compilar cada archivo .c a .o
%.o: %.c
	$(COMPILER) $(FLAGS) -c $< -o $@

# Enlaza los objetos con la librería para crear el ejecutable
$(NAME): $(OBJ_FILES) $(LIB_PRINTF)
	$(COMPILER) $(FLAGS) $(INCLUDES) $(LIBPATH) $^ $(LIBS) -o $@

# Elimina los archivos objeto y limpia printf
clean: printf-clean
	$(RM) $(OBJ_FILES)

# Limpieza completa: elimina objetos y ejecutable
fclean: printf-fclean clean
	$(RM) $(NAME)

# Recompila todo desde cero
re: printf-re clean all

# Declara reglas que no generan archivos
run:
	./$(NAME)
# -- UTILS -- #
# Ejecuta el programa
.PHONY: all clean fclean re run

# -- LIBRARIES -- #
# Compila la librería printf
printf-all:
	$(LIBFT_MAKEFILE) all

# Recompila la librería printf
printf-re:
	$(LIBFT_MAKEFILE) re

# Limpia los objetos de printf
printf-clean:
	$(LIBFT_MAKEFILE) clean

# Limpia completamente printf
printf-fclean:
	$(LIBFT_MAKEFILE) fclean
