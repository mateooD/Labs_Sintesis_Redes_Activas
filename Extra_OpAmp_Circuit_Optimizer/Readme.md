# 🎛️ Script: Optimizador de Circuitos con LM324

## 📝 Introducción
El archivo `OpAmp_Circuit_Optimizer.ipynb` es una herramienta interactiva desarrollada en Python destinada a automatizar el diseño y optimización de etapas amplificadoras utilizando el amplificador operacional de propósito general **LM324**.

A diferencia de un cálculo puramente teórico, este script contempla las **limitaciones reales** del componente (tales como tensiones de *offset*, corrientes de *bias*, *Slew Rate* y rangos de saturación) para proponer diseños realizables con componentes comerciales.

---

## 🎯 Objetivos y Funcionalidades
El objetivo del script es facilitar la síntesis de circuitos amplificadores, permitiendo al usuario:
- **Seleccionar topologías estándar:** Soporta configuraciones **No Inversora**, **Inversora**, **Sumador Inversor** y **Amplificador Diferencial**.
- **Optimizar componentes:** Busca automáticamente en una base de datos de resistores estándar (series comerciales) para encontrar la mejor combinación que se ajuste a la ganancia deseada.
- **Balancear errores:** Permite al usuario decidir mediante un control deslizante qué es más crítico para su diseño: minimizar el **error de ganancia** o minimizar el **error de DC (Offset)**.
- **Validar el funcionamiento:** Comprueba automáticamente si el diseño propuesto entrará en saturación o si excederá el *Slew Rate* del LM324 para la frecuencia y amplitud dadas.

---

## ⚙️ Interfaz y Parámetros
El script despliega una interfaz gráfica (GUI) basada en *widgets* que permite configurar:

1.  **Configuración del Circuito:** Menú desplegable para elegir entre las 4 topologías soportadas.
2.  **Condiciones de Operación:**
    * Tensiones de fuente ($V_{CC}, V_{SS}$).
    * Temperatura de trabajo (afecta las corrientes de fuga y *drift*).
    * Señal de entrada (Amplitud pico y Frecuencia).
3.  **Requerimientos de Diseño:** Ganancia de tensión objetivo (Av).
4.  **Slider de Prioridad:** Una barra deslizante que ajusta el peso del algoritmo de optimización entre "Menor Error DC" y "Menor Error de Ganancia".

---

## 🛠️ Herramientas utilizadas
Este *notebook* integra varias librerías de Python para su funcionamiento:
- **Ipywidgets:** Para la creación de la interfaz de usuario interactiva (botones, sliders, inputs numéricos) sin necesidad de editar código.
- **NumPy:** Para el cálculo vectorial y búsqueda eficiente de combinaciones de resistencias.
- **Schemdraw:** Para dibujar y renderizar el esquemático eléctrico final con los valores calculados directamente en el navegador.
- **Matplotlib:** Backend gráfico para la visualización.

---

## 📌 Resultados Esperados
Al ejecutar el botón **"CALCULAR Y DIBUJAR"**, el script entrega:
- **Valores de Componentes:** Resistencias comerciales ($R_1, R_f, R_{comp}$) seleccionadas.
- **Análisis de Error:** Cálculo del error porcentual de ganancia y la tensión de *offset* de salida esperada.
- **Esquemático:** Un dibujo del circuito configurado con los valores listos para el armado o simulación en LTSpice.