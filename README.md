# busqueda_binaria
ejemplo busqueda binaria

#include <iostream>
#include <vector>

using namespace std;

// Función para realizar la búsqueda binaria
int busquedaBinaria(const vector<int>& array, int objetivo) {
    int izquierda = 0;
    int derecha = array.size() - 1;

    while (izquierda <= derecha) {
        // Calcular el punto medio
        int medio = izquierda + (derecha - izquierda) / 2;

        // Verificar si el elemento en el punto medio es igual al objetivo
        if (array[medio] == objetivo) {
            return medio; // Elemento encontrado, devolver índice
        }
        // Si el elemento en el punto medio es mayor, ajustar el rango a la mitad izquierda
        else if (array[medio] > objetivo) {
            derecha = medio - 1;
        }
        // Si el elemento en el punto medio es menor, ajustar el rango a la mitad derecha
        else {
            izquierda = medio + 1;
        }
    }

    return -1; // Elemento no encontrado
}

int main() {
    // Crear un vector ordenado para la búsqueda binaria
    int elementosArray[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	vector<int> arrayOrdenado(elementosArray, elementosArray + sizeof(elementosArray) / sizeof(elementosArray[0]));


    // Elemento a buscar
    int objetivo = 8;

    // Realizar la búsqueda binaria
    int resultado = busquedaBinaria(arrayOrdenado, objetivo);

    // Imprimir el resultado
    if (resultado != -1) {
        cout << "Elemento encontrado en el indice: " << resultado << endl;
    } else {
        cout << "Elemento no encontrado en el vector." << endl;
    }

    return 0;
}
