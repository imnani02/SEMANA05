# Semana05-EJERCICIO1
def ordenSeleccion(datos):
    for posicion in range(len(datos)):
        menor = posicion

        for siguiente in range(posicion + 1, len(datos)):
            if datos[siguiente] < datos[menor]:
                menor = siguiente

        datos[posicion], datos[menor] = datos[menor], datos[posicion]

    return datos


def ordenBurbuja(datos):
    for vuelta in range(len(datos) - 1):
        cambio = False

        for actual in range(len(datos) - 1 - vuelta):
            if datos[actual] > datos[actual + 1]:
                datos[actual], datos[actual + 1] = datos[actual + 1], datos[actual]
                cambio = True

        if not cambio:
            break

    return datos


def ordenInsercion(datos):
    for posicion in range(1, len(datos)):
        valor = datos[posicion]
        anterior = posicion - 1

        while anterior >= 0 and datos[anterior] > valor:
            datos[anterior + 1] = datos[anterior]
            anterior -= 1

        datos[anterior + 1] = valor

    return datos


numeros = [2, 8, 5, 3, 9, 4, 1]

print("Lista original:", numeros)

lista1 = numeros.copy()
lista2 = numeros.copy()
lista3 = numeros.copy()

print("Ordenamiento por selección:", ordenSeleccion(lista1))
print("Ordenamiento por burbuja:", ordenBurbuja(lista2))
print("Ordenamiento por inserción:", ordenInsercion(lista3))
