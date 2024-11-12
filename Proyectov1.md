```python

AsciiMafalda ='''
                         ,__   _
                         |      `-,
                          ",       '-.
                           '.        `,-,_         ,,-""'`"",
                            ,'        '' ``,_----_''        `
                         -_,'   .,-,---..-.`    ,'       ,-'
                          -'   ,,::::::::..,--.-.,     ,,'
                    ,,--:::'  (::::::::::::::::::,.     `
                ,_-,:::::::, ,::::::::::::::::::::(,    ,
               ,::::::::::::::::::::::::::::::::::::,.  '
             _,,::::::::::::::::::::::::::::::::::::.`  ,. -
            ,,:::::::::::::::::::::::::::::::::::::::._,::[..
           -::::::::::::::::::'"`"""'"`""`::::::::::::::::::;_.
          (,::::::::::::::::'               "`:::::::::::::::("
         ',:::::::::::::::::|                  ""::::::::::::::,
        ,'::::::::::::::::::|     -.             `:::::::::::::'.
        `::::::::::::::::::::     :'    ,,.       ::::::::::::::,
        ,::::::::::::::::::::     "'    |:'      ,::::::::::::::.
       |::::::::::::::::::"''     ,-'.. `"      ,::::::::::::::::|
       ":::::::::::::::''        ,    ',       ,:::::::::::::::::.
       |::::::::::::::"         `,    ,|       :::::::::::::::::::.
       ||::::::::::::'  ,        `,. _,        `":::::::::::::::::.
       '|:::::::::::'   `.                      `"::::::::::::::::.
        `'":::::::::'    `"`--__                 `::::::::::::::::|
          `'::::::::|          "``--___        ,  `:::::::::::::::|
            '':::::::              `"""""--,_ -'  ,:::::::::::::[''
  :.__.      `'":::::.                           ,::::::::::::::,
  `(`.` .     ` '"":::,.                         ,:::::::::::::''
   ``',    ,       ``":'._                      ,::::::::::::''
     `.`.   `..   _,,"'' `";,.                 ,::::::::::::"'
      `."`.   `,,',','     ``_"--___       ,_,,:::::::""""""``-,
       `. `.   ``,| ,         "`.__."^^_]:''"''""":'"          ``.
        '`. `.  -`  `,.  ,__.,^"";. """ ,---_'`-.``,             `.
          -. ',  .`,  _____,, `  .|,   |.,''        ",.           .
          ,", ``    "      `" -"",|`, _,'      ,      `,.         ,
          ,  `_|,,,_-----___        '  '    _,''       ``        ,'
         `|   ``,"`_____'""""""----.____-_-]"'          `|       ,
       ,,'|       ''    """,               '_   _,,'     ,      ,'
     ,,'  "      |        _'                 ""`.7        ,    ,'
    ,'    ,      ,    --.::-,--.                `"_ _,-,_ .  ,,'
    `'-,. `,    ,'             `_                `""^ ". ": ,''
        `",.    |           ,_,' |                 `., '-.]''
           `.   :       ,--'"   _'                  `,` ``"
           ::,  |.           _,'`,_.                 '. `.
          |:::..' "-_.      `'  _'""`""`--.--,___.    `..`..
          '[:::::;,'`-__"""'  ""'               `""""--',_,'
           |::::::-.   ``'-.,-.,---------------,..- ---`"
           ,::'  "":..     |'             ,,"'
          ,::'     "":, ,  |.           ,-:.
          |::.      `":,    `--,--,---(__.-,
          |:::,      '::;'",.,.    `      ,'
          `::::     --::,::::::.,"""`""" ||
   -hrr-   ::::.   - ,`'   "`":::-_ -    ,:.
           |::::.._,'          ``"::,. ,,::.
            `:::::::-,.           ""::-:::::
             `::::::::::---________,::::::::
              `'`::::::::::::::::::::""`""'
                '"":::::::::::::'""''
                      `""""'
'''
# Convertir el string de arte ASCII en una lista de líneas
AsciiMafaldaLineas = AsciiMafalda.splitlines()

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
MatrizAscii = ConvertirYNormalizarMatriz(AsciiMafaldaLineas)

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






