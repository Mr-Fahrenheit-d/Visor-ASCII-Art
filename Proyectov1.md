```python
AsciiMafalda = '''
                         ,__   _
                         |      `-,
                          ",       '-.
                           '.        `,-,_         ,,-""'`"",
                            ,'        '' ``,_----_''        `
                         -_,'   .,-,---..-.`    ,'       ,-'
                          -'   ,,::::::::..,--.-.,     ,,
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
    ,'    ,      ,    --.::-,--.                `"_ _,-,_ .  ,,
    `'-,. `,    ,'             `_                `""^ ". ": ,''
        `",.    |           ,_,' |                 `., '-.]''
           `.   :       ,--'"   _'                  `,` `"`
           ::,  |.           _,'`,_.                 '. `.
          |:::..' "-_.      `'  _'""`""`--.--,___.    `..`.
          '[:::::;,'`-__"""'  ""'               `""""--',_,''
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

AsciiMafalda2 = """
                         .-'')
            ,.___  __.-'   /
           _;----''.._)_  (--...__
         ,'           `.__(       `-._
        '      __,....,_              \\
       |    ,,'o    o | `.             \\
        `. |    _'  _.'  /              |
       ,.- `>-'( )''    |               |
     ,'  _ /  ____,.--./                |
    |   / )")'         |               /
    `. ( ( (._         _._        __.-'
      `->..___`,-...--' /,--:'''''
       /      ``>/o\\   //    `.
      /       .'/o /`-'|       \\
  ___(      _/  `-'   ,'        \\
 |    `---,'---...._,'--.__     |\\
 | ,-----',       ,',' , _,`----' \\
 | |     \\|       ('`-'-'  (`-.____`.
 | |      `.       \\        )\\______)
 | |        `-----'''------','op||
 | |        `-,oobb.'ibbbbb: ,88||
 | |         d"'''`Y8;"'''`PY8P_)|
 | | -hrr-  `8b___od8boooood8P| ||
 | |          Y8P"'' Y888PP' || ||
"""

AsciiArts = [AsciiMafalda, AsciiMafalda2]

def ConvertirArteALista(arte_ascii):
    return arte_ascii.splitlines()

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

def SeleccionarArte():
    print("\nSeleccione el arte ASCII:")
    for i, art in enumerate(AsciiArts):
        print(f"{i + 1}. Arte {i + 1}")
    seleccion = int(input("Elija una opción (1 o 2): ")) - 1
    return AsciiArts[seleccion]

def MostrarMenu():
    print("\n--- Menú ---")
    print("1. Mostrar el arte ASCII original")
    print("2. Rotar 90 grados en sentido horario")
    print("3. Rotar 90 grados en sentido antihorario")
    print("4. Rotar 180 grados")
    print("0. Salir")
    return input("Elija una opción: ")

def MostrarArteOriginal(ascii_art):
    for linea in ascii_art:
        print(linea)

arte_seleccionado = SeleccionarArte()
arte_seleccionado_lista = ConvertirArteALista(arte_seleccionado)
MatrizAscii = ConvertirYNormalizarMatriz(arte_seleccionado_lista)

opcion = ''
while opcion != '0':
    opcion = MostrarMenu()
    if opcion == '1':
        print("\nArte ASCII original:")
        MostrarArteOriginal(arte_seleccionado_lista)
    elif opcion == '2':
        print("\nRotación 90 grados en sentido horario:")
        MatrizAscii = RotarMatriz90Horario(MatrizAscii)
        MostrarMatriz(MatrizAscii)
    elif opcion == '3':
        print("\nRotación 90 grados en sentido antihorario:")
        MatrizAscii = RotarMatriz90Antihorario(MatrizAscii)
        MostrarMatriz(MatrizAscii)
    elif opcion == '4':
        print("\nRotación 180 grados:")
        MatrizAscii = RotarMatriz180(MatrizAscii)
        MostrarMatriz(MatrizAscii)
    elif opcion == '0':
        print("Saliendo del programa.")
    else:
        print("Opción no válida, intente de nuevo.")

