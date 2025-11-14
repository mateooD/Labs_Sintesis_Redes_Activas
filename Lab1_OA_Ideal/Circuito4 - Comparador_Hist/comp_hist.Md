# 🔍 Comparador con Histéresis – LM324  
Circuito Nº4 – Electrónica Analógica / SRA

Este carpeta contiene el circuito y las simulaciones correspondientes a un **comparador con histéresis** implementado con un amplificador operacional LM324.

---

## 📝 Descripción general

Un comparador con histéresis (o **Schmitt Trigger no inversor**) es un circuito que compara una señal de entrada `Vi` contra dos umbrales distintos:

- **V<sub>TH</sub>** — Umbral superior  
- **V<sub>TL</sub>** — Umbral inferior  

La salida `Vout` conmuta entre los niveles de saturación del operacional (**V+** y **V−**) dependiendo de si la entrada supera o cae por debajo de esos umbrales.

La **histeresis** proporciona una región donde la salida no cambia, incluso si la entrada está dentro de ese rango. Esto evita oscilaciones y ruido cuando la señal cruza lentamente el punto de comparación.

---

## 🎯 Objetivo del circuito

- Obtener una salida digital (alto/bajo) a partir de una señal analógica.  
- Evitar falsas conmutaciones debidas al ruido.  
- Definir dos niveles de disparo bien separados.  
- Convertir señales senoidales o ruidosas en ondas cuadradas limpias.
