# Fundamentos de Graficación por Computadora 

Este repositorio contiene un resumen ejecutivo sobre los pilares de la computación gráfica, desde su evolución histórica hasta la implementación técnica de algoritmos de trazado y modelos de color.

---

##  Índice
1. [Historia y Evolución](#11-historia-y-evolución)
2. [Áreas de Aplicación](#12-áreas-de-aplicación)
3. [Aspectos Matemáticos](#13-aspectos-matemáticos)
4. [Modelos de Color](#14-modelos-de-color)
5. [Tutorial: Iluminación en Blender](#-tutorial-iluminación-de-un-cubo-en-blender)
6. [Trazo de Líneas y Polígonos](#15-representación-y-trazo-de-líneas-y-polígonos)

---

## 1.1. Historia y Evolución
La graficación ha evolucionado de representaciones militares abstractas a simulaciones fotorrealistas:

* **Años 50:** Uso de tubos de rayos catódicos (CRT) para defensa (Proyecto SAGE).
* **Años 60:** **Ivan Sutherland** crea *Sketchpad*, introduciendo la interfaz gráfica de usuario (GUI) y el diseño asistido por computadora.
* **Años 70:** Desarrollo de algoritmos de iluminación y sombreado (*Gouraud*, *Phong*) y mapeo de texturas.
* **Años 80/90:** Explosión del 3D en el cine (Pixar) y nacimiento de las primeras GPUs (Nvidia).
* **Actualidad:** Foco en el *Ray Tracing* en tiempo real e Inteligencia Artificial para la reconstrucción de imágenes.

---

## 1.2. Áreas de Aplicación
La computación gráfica es transversal a múltiples industrias:
* **Entretenimiento:** Videojuegos AAA y efectos visuales (VFX).
* **Medicina:** Modelado de órganos y telecirugía.
* **Ingeniería (CAD):** Diseño de prototipos industriales y arquitectura.
* **Ciencia:** Visualización de grandes volúmenes de datos (Big Data).

---

## 1.3. Aspectos Matemáticos
La base de cualquier motor gráfico reside en el álgebra lineal:

* **Transformaciones Geométricas:** Uso de matrices para traslación, rotación y escalado.
* **Coordenadas Homogéneas:** Permiten unificar todas las transformaciones en una sola operación matricial de $4 \times 4$.
* **Proyecciones:** Transformación de un espacio 3D a un plano 2D (Perspectiva vs. Ortopedical).

---

## 1.4. Modelos de Color


[Image of RGB vs CMYK color space comparison]


| Modelo | Tipo | Uso Común |
| :--- | :--- | :--- |
| **RGB** | Aditivo | Pantallas, sensores digitales. |
| **CMYK** | Sustractivo | Impresión y artes gráficas. |
| **HSV / HSL** | Perceptual | Selección de color y edición fotográfica. |

---

##  Tutorial: Iluminación de un Cubo en Blender
Sigue estos pasos para configurar la escena básica:

1.  **Agregar Luz:** Presiona `Shift + A` > *Light* > *Point* (o *Sun* para luz global).
2.  **Mover la Fuente:** Presiona `G` y arrastra el mouse para posicionarla.
3.  **Configurar Intensidad:**
    * Ve al panel **Object Data Properties** (ícono de foco verde).
    * Ajusta el valor `Power` a **1000 W** para notar el impacto.
4.  **Renderizado en Tiempo Real:** * Presiona la tecla `Z` y selecciona la opción **Rendered**.
5.  **Sombras:** Asegúrate de que la casilla `Shadows` esté activada en las propiedades de la luz para generar profundidad en las caras del cubo.

---

## 1.5. Representación y Trazo de Líneas y Polígonos


Para dibujar en una rejilla de píxeles (discretización), se utilizan algoritmos optimizados:

* **Algoritmo DDA:** Utiliza la pendiente de la recta, pero requiere operaciones de punto flotante (lento).
* **Algoritmo de Bresenham:** Utiliza únicamente aritmética de enteros, lo que lo hace extremadamente eficiente para hardware.
* **Relleno de Polígonos:** Algoritmos como *Scan-line* determinan qué píxeles están "dentro" basándose en las intersecciones con los bordes.

