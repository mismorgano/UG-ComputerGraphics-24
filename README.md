# Computer Graphics 

La idea del proyecto es que sea multiplataforma. 
Para ello utilizaremos `CMakeLists.txt` junto con `cmake`
para que configure el proyecto con las herramientas nativas de cada plataforma.

## Prerrequisitos

Tener lo siguiente instalado en el entorno de desarrollo:

- [cmake](https://cmake.org/download/)
- Un compilador de `c++` que soporte `c++20`
- [GLFW](https://www.glfw.org/)

En el caso de **Windows** existe el proyecto [msys2](https://www.msys2.org/).
En el cual se puede instalar `cmake`, `g++` y `glfw`[^1].

[^1]: En el caso de `glfw` estoy suponiendo que está instalado en el entorno de desarrollo.
    También se podrían incluir simplemente los ejecutables o el código fuente para su compilación
    (lo voy a pensar).

## Ejecución 

Una vez instalado lo anterior, basta con ir al directorio del proyecto y ejecutar:
```
cmake -S . -B build
```
Para configurar el proyecto, y
```
cmake --build build
```
para construirlo.

Después simplemente ejecutar:
```
./build/ComputerGraphics
```





