# Simulador CSP: Asignación de Tareas con Backtracking y Forward Checking

Aplicación web interactiva y didáctica de un solo archivo (**HTML5**, **Tailwind CSS** y **JavaScript Vanilla**) diseñada para simular y visualizar paso a paso la resolución de un **Problema de Satisfacción de Restricciones (CSP)** mediante el algoritmo de **Backtracking** con inferencia anticipada (**Forward Checking**).

---

## 📌 Formulación del Problema CSP

El escenario modelado es un problema clásico de asignación de tareas a empleados:

* **Variables ($X$):**
  * $X_1 = \text{Ana}$
  * $X_2 = \text{Luis}$
  * $X_3 = \text{Carlos}$

* **Dominios Iniciales ($D$):**
  * $D(\text{Ana}) = \{ T_1, T_2 \}$
  * $D(\text{Luis}) = \{ T_1, T_3 \}$
  * $D(\text{Carlos}) = \{ T_2, T_3 \}$ (o $\{ T_2 \}$ si se activa la restricción opcional)

* **Restricciones ($C$):**
  1. **Unicidad:** Cada empleado realiza exactamente 1 tarea.
  2. **AllDifferent:** Ninguna tarea se repite entre empleados:
     $$\text{AllDifferent}(\text{Ana}, \text{Luis}, \text{Carlos})$$
  3. **Restricción Adicional (Opcional por Toggle):**
     $$\text{Carlos} \neq T_3$$

* **Reglas de Exploración Estrictas:**
  * **Orden de Variables:** $\text{Ana} \rightarrow \text{Luis} \rightarrow \text{Carlos}$
  * **Orden de Valores:** $T_1 \rightarrow T_2 \rightarrow T_3$

---

## 🎯 Características Educativas del Simulador

1. **Panel de Explicación Educativa ("Análisis del Algoritmo"):**
   * Muestra en tiempo real y en lenguaje natural el *por qué* de cada decisión del algoritmo.
   * Acentos temáticos e íconos intuitivos:
     * 🔵 **Evaluando / Asignando:** Selección de variable y prueba de valor tentativo.
     * 🟡 **Reducción de Dominios:** Poda anticipada por *Forward Checking*.
     * 🔴 **Fallo / Backtracking:** Detección de dominio vacío (*Domain Wipeout*) y retroceso cronológico.
     * 🟢 **Solución Encontrada:** Identificación de estado meta consistente.

2. **Árbol de Decisión Gráfico en SVG Dinámico:**
   * Sustituye consolas planas por un lienzo vectorial interactivo.
   * **Código de Colores de Nodos:**
     * 🔘 **Gris:** Nodo actualmente bajo evaluación.
     * 🟢 **Verde:** Nodos que forman parte de una solución consistente válida.
     * 🔴 **Rojo:** Rama inválida podada por conflicto o callejón sin salida.
   * Líneas conectoras automáticas entre nodos padre e hijos.

3. **Sincronización Permanente de Dominios:**
   * Las tareas $T_1, T_2, T_3$ permanecen siempre visibles en cada tarjeta de empleado.
   * Cuando una tarea deja de estar disponible, se visualiza en **gris opaco y tachada (`line-through`)** con su motivo correspondiente (`"Podada"`, `"Restricción"` o `"No inicial"`), permitiendo observar cómo se reduce el espacio de búsqueda.

4. **Controles de Reproducción y Atajos de Teclado:**
   * Paso a Paso (*Siguiente* / *Anterior*).
   * Modo *Autoplay* continuo.
   * Atajos rápidos: `→` (Siguiente), `←` (Anterior) y `Espacio` (Autoplay).

---

## 🚀 Cómo Ejecutar

El proyecto es totalmente autocontenido y no requiere instalación de dependencias, compiladores ni servidores:

1. Clona este repositorio o descarga el archivo `index.html`.
2. Haz doble clic en `index.html` para abrirlo en cualquier navegador web moderno (Chrome, Edge, Firefox, Safari).

---

## 🛠️ Tecnologías Utilizadas

* **HTML5 Semántico**
* **Tailwind CSS v3 (CDN)**
* **JavaScript Vanilla (ES6+)**
* **SVG Vectorial Dinámico**

---

