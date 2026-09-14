# Práctica 1 - Primeros pasos con OpenCV

Este repositorio contiene la primera práctica de la asignatura Visión por Computador, llamada **Primeros pasos con OpenCV**. El trabajo se ha realizado en el cuaderno `VC_P1.ipynb`, usando Python, OpenCV y las librerías incluidas en el entorno de la práctica para crear y modificar imágenes, además de trabajar con la cámara en tiempo real.

## Autores

- Pablo Llopis Parrilla
- David González Espino

## Contenido del repositorio

- `VC_P1.ipynb`: cuaderno principal de la práctica.
- `ajedrez.jpg`: imagen generada con textura de tablero de ajedrez.
- `mondrian.jpg`: imagen generada con estilo Mondrian.
- `perro_original.jpg`: imagen original usada para la propuesta pop art.
- `pop_art.jpg`: resultado de la propuesta pop art sobre la imagen original.

## Instalación y ejecución

No se necesita instalar nada adicional respecto al entorno indicado en el [README de la práctica original proporcionada por el profesor](https://github.com/otsedom/otsedom.github.io/blob/main/VC/P1/README.md). Con ese entorno es suficiente para ejecutar el cuaderno.

Para las partes que usan la cámara, el equipo debe tener una webcam disponible y permisos para acceder a ella. La salida de cámara se cierra pulsando `ESC`.

## TAREA: textura de tablero de ajedrez

Se genera una imagen de 800 x 800 píxeles con textura de tablero de ajedrez. La imagen se crea en escala de grises usando una matriz de NumPy y asignando manualmente los valores de cada casilla.

Primero se resuelve sin herramientas de IA. En esta versión se recorre la imagen por bloques de 100 x 100 píxeles y se alternan los colores blanco y negro mediante un contador.

Después se incluye una segunda solución generada con ChatGPT 5.6 Sol. Para ello se le pasó directamente el enunciado de la tarea, indicándole que la resolviera a su manera y sin tener en cuenta la solución manual. En esa versión se usa directamente la suma de los índices de fila y columna para decidir el color de cada casilla. La comparación entre ambas soluciones está incluida en el propio cuaderno.

La conversación usada con ChatGPT consistió en pasarle el enunciado de la tarea y pedirle una solución independiente de la nuestra.

## TAREA: imagen estilo Mondrian

Se crea una imagen con estilo Mondrian usando funciones de dibujo de OpenCV. Para ello se parte de una imagen negra y se dibujan rectángulos de distintos tamaños y colores, separados por líneas negras, siguiendo la estética característica de este estilo.

El resultado se guarda en el archivo `mondrian.jpg`.

## TAREA: píxel más claro y más oscuro en cámara

Se captura vídeo desde la cámara y, en cada fotograma, se localizan el píxel más claro y el más oscuro. Para hacerlo, cada fotograma se convierte a escala de grises y se usa `cv2.minMaxLoc`.

Sobre el fotograma original se dibujan círculos en las posiciones detectadas. El resultado se muestra en una ventana de OpenCV en tiempo real.

### Ampliación

Además de la versión pedida con círculos, se añadió una segunda versión más visual. En ella se dibuja una luna sobre la posición más oscura y un sol sobre la más clara, usando elipses, líneas y círculos de OpenCV.

Esta ampliación mantiene la misma lógica de detección, pero cambia la forma de representar los puntos encontrados en la imagen.

## TAREA: propuesta propia de pop art

Se realiza una propuesta propia de pop art a partir de una imagen de un perro. La imagen original se carga desde `perro_original.jpg`, se separan sus canales de color y se crean cuatro versiones distintas modificando o invirtiendo canales RGB.

Finalmente, las cuatro versiones se colocan en una composición 2 x 2 para conseguir un efecto tipo pop art. El resultado se guarda en `pop_art.jpg`.

### Ampliación

También se añadió una versión de pop art aplicada directamente a la cámara. En este caso, cada fotograma se divide en cuatro variantes con diferentes inversiones de canales de color y se muestran juntas en una composición 2 x 2 en tiempo real.

## Fuentes y herramientas utilizadas

- Repositorio de la práctica proporcionado por el profesor, usado como enunciado y referencia principal: https://github.com/otsedom/otsedom.github.io/tree/main/VC/P1
- Ejemplo de referencia sobre Mondrian indicado en el enunciado: https://www3.gobiernodecanarias.org/medusa/ecoescuela/sa/2017/04/17/descubriendo-a-mondrian/
- ChatGPT: se utilizó para generar una solución alternativa de la tarea del tablero de ajedrez, que luego se comparó con la solución manual.
