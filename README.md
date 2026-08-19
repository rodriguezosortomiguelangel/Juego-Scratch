# 🍎 Proyecto Scratch: Salvando la Manzana

![Platform](https://img.shields.io/badge/Plataforma-Scratch_3.0-orange?style=for-the-badge)
![Genre](https://img.shields.io/badge/Género-Arcade%2FReflejos-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Estado-Completado-success?style=for-the-badge)

Documentación técnica y lógica de programación para el videojuego interactivo desarrollado en **Scratch**, donde el jugador controla un tazón (*Bowl*) para interceptar manzanas que caen aleatoriamente antes de que toquen el suelo.

---

## 📌 1. Descripción del Juego

El juego sigue una mecánica clásica estilo arcade. Las manzanas caen de forma continua desde la parte superior de la pantalla en posiciones horizontales aleatorias. El objetivo principal es mover el tazón hacia la izquierda y derecha para atajarlas, sumando puntos por cada captura y finalizando la partida si la manzana toca el límite inferior.

### 🎯 Objetivos del Proyecto
* **Lógica Programática:** Aplicar condicionales, bucles infinitos, variables y detección de colisiones.
* **Aleatoriedad:** Implementar la generación de posiciones aleatorias en el eje X para mantener el reto dinámico.
* **Experiencia de Usuario:** Diseñar un sistema de puntuación en tiempo real y condiciones claras de *Game Over*.

---

## 🎮 2. Mecánicas y Controles

| Elemento | Mecánica / Función |
| :--- | :--- |
| 🥣 **Tazón (Bowl)** | Desplazamiento horizontal continuo en el eje X mediante teclado. |
| 🍎 **Manzana (Apple)** | Caída vertical constante desde el eje superior `Y = 180`. |
| 🏆 **Puntuación** | Incremento de `+1` punto por cada colisión exitosa con el tazón. |
| 💀 **Game Over** | Se activa automáticamente al detectar `Y < -170` (contacto con el suelo). |

---

## ⚙️ 3. Lógica de Programación & Bloques

### 🥣 Objeto: Tazón (*Bowl*)
* **Movimiento a la Derecha:**
  * Al presionar la **Tecla Flecha Derecha** ➔ Cambiar X por `10`
* **Movimiento a la Izquierda:**
  * Al presionar la **Tecla Flecha Izquierda** ➔ Cambiar X por `-10`
* **Restricción de Eje:** Fijar la posición vertical en `Y = -140` para evitar desplazamientos accidentales.

### 🍎 Objeto: Manzana (*Apple*)
* **Reinicio de Posición:**
  * Fijar Y a `180`
  * Fijar X a un **Número Aleatorio** entre `-200` y `200`
* **Bucle de Caída:**
  * Por siempre ➔ Cambiar Y por `-7` (Velocidad de caída)
* **Detección de Colisión (Atrapada):**
  * Si toca el objeto `Bowl`:
    * Reproducir sonido `Pop` / `Collect`
    * Sumar `1` a la variable `Puntos`
    * Reaparecer en la parte superior (X aleatorio, Y = 180)
* **Detección de Suelo (Fallo):**
  * Si la posición `Y < -170`:
    * Enviar mensaje `Game Over` y detener los programas.

---

## 📊 4. Variables Utilizadas

* **`Puntos`**: Almacena el número total de manzanas atrapadas. Se reinicia automáticamente a `0` al presionar la bandera verde.
* **`Velocidad`** *(Opcional)*: Permite escalar la dificultad incrementando el ritmo de caída a medida que aumenta la puntuación.

---

## 🚀 5. Flujo de Ejecución
