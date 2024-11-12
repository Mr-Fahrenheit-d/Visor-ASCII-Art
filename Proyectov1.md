```python
AsciiMafalda = [
    "                   ,--,",
    "                 ,'   :.------.",
    "             ,--;,--=  \\       `.",
    "     ,------;--' -~~\"\"--'        `.",
    "   ,'     ,'                       \\",
    "  /     /'     _,,--'<              \\",
    " +----'-'    ,'       \\              :",
    "   ,'       /      _-' ._            |                      _",
    "  /        :   ,' ..     `--.        |_                    |\"",
    " ;          `-,   ''      / `.       ; )   __             O",
    " |           /        ,--'   |      /  '--~,'|",
    " |          .'\\    ,-'       /    ,'\\  ;._' ,''        .-.",
    " |          |  `--'        ,+----'   \\/   `'_,'        | |",
    " :     _    |            ,'  `.       \\,,.-'          O O",
    "  \\   ( '-+. `-.._,..--'|\\,___\\`-.     \\                 .",
    "  _`---'  | `----  \\    ;|o\\      `.__-'                 |",
    " ((~,/  ~ |       / `--' |o \\   ,,'   `.                 |",
    "  \\\\ ' _,-|      /       '--' ,'       |`.      .--------+-.",
    "   '\"~~   |  _,-',---..__,.,=' \\       /  `-.   | [+++]ooO |",
    "          '\"\" | /      //ooo `-.\\     /....'    |          |",
    "   -hrr-  _.-'/ \\     /|,8888.  \\\\  ,'.....'    | (#)  (#) |",
    "        ---___   `-._/ |`8888P   |_  .-'''     `----------'",
    "              `````` '-..,___,.,`' .-'                 _"
]

def ConvertirYNormalizarMatriz(ascii_art):
    max_longitud = max(len(linea) for linea in ascii_art)
    return [list(linea.ljust(max_longitud)) for linea in ascii_art]

def RotarMatriz90Horario(Matriz):
    Filas, Columnas = len(Matriz), len(Matriz[0])
    NuevaMatriz = [[' ' for _ in range(Filas)] for _ in range(Columnas)]
    for i in range(Filas):
        for j in range(Columnas):
            NuevaMatriz[j][Filas - 1 - i] = Matriz[i][j]
    return NuevaMatriz

def RotarMatriz90Antihorario(Matriz):
    Filas, Columnas = len(Matriz), len(Matriz[0])
    NuevaMatriz = [[' ' for _ in range(Filas)] for _ in range(Columnas)]
    for i in range(Filas):
        for j in range(Columnas):
            NuevaMatriz[Columnas - 1 - j][i] = Matriz[i][j]
    return NuevaMatriz

def RotarMatriz180(Matriz):
    Filas, Columnas = len(Matriz), len(Matriz[0])
    NuevaMatriz = [[' ' for _ in range(Columnas)] for _ in range(Filas)]
    for i in range(Filas):
        for j in range(Columnas):
            NuevaMatriz[Filas - 1 - i][Columnas - 1 - j] = Matriz[i][j]
    return NuevaMatriz

def MostrarMatriz(matriz):
    for fila in matriz:
        print(''.join(fila))

# Convertir y normalizar el arte ASCII
MatrizAscii = ConvertirYNormalizarMatriz(AsciiMafalda)

# Rotar la matriz 90 grados en sentido horario y mostrarla
print("Rotación 90 grados en sentido horario:")
MatrizRotadaHorario = RotarMatriz90Horario(MatrizAscii)
MostrarMatriz(MatrizRotadaHorario)

# Rotar la matriz 90 grados en sentido antihorario y mostrarla
print("\nRotación 90 grados en sentido antihorario:")
MatrizRotadaAntihorario = RotarMatriz90Antihorario(MatrizAscii)
MostrarMatriz(MatrizRotadaAntihorario)

# Rotar la matriz 180 grados y mostrarla
print("\nRotación 180 grados:")
MatrizRotada180 = RotarMatriz180(MatrizAscii)
MostrarMatriz(MatrizRotada180)




