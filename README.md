# Maps-ProblemaViajante
Algoritmo que mediante la API de maps busca los locales sugeridos en un radio y localizacion sugerida y mediante un algoritmo para solucionar el problema del viajente los ordena para realizar el minimo recorrido desde un punto de inicio establecido.
Este código es un programa en Python que utiliza la API de Google Maps para encontrar talleres de reparación de automóviles cercanos al centro de Madrid, filtra los talleres que no son específicos para automóviles y calcula la ruta óptima para visitar todos los talleres utilizando el algoritmo del problema del vendedor ambulante (TSP).

Primero, se importan las bibliotecas necesarias y se configuran las credenciales de la API de Google Maps.

Luego, se definen algunas variables y funciones:

moncloa_address, moncloa_location y moncloa_coordinates almacenan información sobre la ubicación de Moncloa en Madrid.
madrid_center_address y madrid_center_location almacenan información sobre la ubicación del centro de Madrid (Puerta del Sol).
madrid_radius define un radio de búsqueda de 20 km.
Las funciones son las siguientes:

get_workshops_nearby(center_location, radius): Encuentra talleres de reparación de automóviles cercanos al centro de Madrid utilizando la API de Google Maps. Devuelve una lista de talleres con su información relevante.

filter_car_workshops(workshops): Filtra talleres que no son específicos para automóviles (por ejemplo, talleres de motocicletas) utilizando palabras clave. Devuelve una lista de talleres específicos para automóviles.

create_distance_matrix(workshops): Crea una matriz de distancias entre todos los talleres utilizando la función haversine para calcular las distancias en kilómetros. Devuelve una matriz cuadrada.

tsp_solution(workshops): Resuelve el problema del vendedor ambulante utilizando la matriz de distancias y la biblioteca OR-Tools de Google. Devuelve la solución, el administrador de índices y el modelo de enrutamiento.

print_solution(solution, manager, routing, workshops): Imprime la solución del problema del vendedor ambulante, mostrando el recorrido total en kilómetros y la lista de talleres en el orden óptimo para visitarlos.

El código principal del programa realiza las siguientes acciones:

Obtiene una lista de talleres cercanos al centro de Madrid.
Filtra la lista de talleres para incluir solo talleres de automóviles.
Ordena la lista de talleres por distancia desde Moncloa.
Agrega la ubicación de Moncloa al comienzo de la lista de talleres.
Calcula la solución óptima del problema del vendedor ambulante para visitar todos los talleres.
Imprime la solución y el recorrido total en kilómetros.
