### Código

```python

def votaciones_estudiantiles() :
 
    ganador = ""

    secciones = [[], [], []]

    candidato_1 = str(input("Ingrese el nombre del candidato 1: "))
    candidato_2 = str(input("Ingrese el nombre del candidato 2: "))
    candidato_3 = str(input("Ingrese el nombre del candidato 3: "))

    votos_candidato_1 = 0
    votos_candidato_2 = 0
    votos_candidato_3 = 0

    for i in range(1, 4):

        i -= 1

        secciones[i].append(int(input(f'Ingrese la cantidad de votos validos para {candidato_1}, en la sección #{i + 1}: ')))

        secciones[i].append(int(input(f'Ingrese la cantidad de votos validos para {candidato_2}, en la sección #{i + 1}: ')))

        secciones[i].append(int(input(f'Ingrese la cantidad de votos validos para {candidato_3}, en la sección #{i + 1}: ')))

        secciones[i].append(int(input(f'Ingrese la cantidad de votos nulos en la sección #{i + 1}: ')))

        secciones[i].append(int(input(f'Ingrese la cantidad de votos en blanco en la sección #{i + 1}: ')))

    for i, seccion in enumerate(secciones):

        votos_validos = seccion[0] + seccion[1] + seccion[2]

        votos_candidato_1 += seccion[0]
        votos_candidato_2 += seccion[1]
        votos_candidato_3 += seccion[2]

        print(f'Total de votos validos, sección #{i + 1}: {votos_validos}')
        print(f'Total de votos en blanco, sección #{i + 1}: {seccion[3]}')
        print(f'Total de votos nulos, sección #{i + 1}: {seccion[4]}')

    # Encontrar al ganador
    if votos_candidato_1 > votos_candidato_2 and votos_candidato_1 > votos_candidato_3:
        ganador = candidato_1

    elif votos_candidato_2 > votos_candidato_1 and votos_candidato_1 > votos_candidato_3:
        ganador = candidato_2
    
    else: 
        ganador = candidato_3
    
    print("Ganador: ", ganador)

votaciones_estudiantiles()

```

### Diagramación
![VOTACIONES(2)](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/87686142-15d3-4464-9a98-e6f1fafdc016)


## Documentación completa: 
https://docs.google.com/document/d/1Yobthu7O4TK3D4R4ET7ntcIvw2IPuHgLtUnSMiUGu8o/edit?usp=sharing
