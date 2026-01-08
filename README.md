# MacroBeeSwarm 🐝
Una macro avanzada y modular para **Bee Swarm Simulator** en Roblox.

Esta aplicación automatiza tareas repetitivas en el juego, incluyendo AutoClick, movimientos predefinidos y lógicas inteligentes de bot para farmear en diferentes campos.

---

## ✨ Características Principales

*   **AutoClick**: Clics automáticos configurables.
*   **Movimiento WASD**: Patrones de movimiento automatizados (Zig-Zag por defecto o personalizados).
*   **Smart Bot 🤖**: Bot inteligente que sigue rutas y reacciona a eventos (mochila llena, spawn, etc.).
*   **Multi-Bot 🔄**: Sistema de colas para encadenar tareas en múltiples campos secuencialmente.

---

## ⌨️ Atajos de Teclado (Hotkeys)

| Tecla | Acción | Descripción |
| :---: | :--- | :--- |
| **F1** | AutoClick | Activa o desactiva solo el AutoClick. |
| **F2** | Movimiento | Activa o desactiva solo el movimiento WASD. |
| **F3** | Smart Bot | Inicia o detiene el Smart Bot (Ruta única). |
| **F4** | Multi-Bot | Inicia o detiene el Multi-Bot (Lista de tareas). |
| **F5** | Grabar Ruta | Comienza a grabar una la ruta (caminata) del jugador. |
| **F6** | Grabar Patrón | Comienza a grabar un patrón de movimiento personalizado. |

---

## ⚙️ Guía de Configuración

### 1. AutoClick 🖱️
Configura los parámetros básicos del clic:
*   **Tiempo presionado (ms)**: Tiempo que el clic se mantiene presionado (Recomendado: `5000` ms).
*   **Tiempo entre ciclos (ms)**: Intervalo entre cada clic (Recomendado: `500` ms).
*   **Botón del mouse**: Selecciona el botón a usar (usualmente "Izquierdo").

### 2. Movimiento WASD 🕹️
Controla cómo se mueve el personaje en el campo.
*   **Por defecto (Zig-Zag)**: Usa las teclas W, A, S, D con tiempos configurables. Recomiendo valores bajos (ej: W=0.1, A=0.4, S=0.1, D=0.4) para mantenerse en el centro.
*   **Patrones Personalizados**:
    *   Presiona **F6** para empezar a grabar tu propio movimiento.
    *   Realiza los movimientos deseados.
    *   Presiona **F6** nuevamente para guardar.

### 3. Smart Bot 🤖
El núcleo de la automatización. Selecciona una ruta de la lista y configura los detectores:

*   **Rutas**: Selecciona una ruta predefinida o graba una propia con **F5**.
*   **🎒 Detector Mochila (Reinicio)**:
    *   Haz clic en **"Capturar Mochila (3s)"**.
    *   Mueve el mouse hacia la **zona roja** de la notificación de "Mochila Llena" en el juego.
    *   El bot detectará cuando esta zona se ponga roja y reiniciará el personaje.
*   **👁️ Detector Spawn (Check de Cámara)**:
    *   Es vital para asegurar que el recorrido empiece bien.
    *   Haz clic en **"Capturar Spawn (3s)"**.
    *   Apunta el mouse a un objeto fijo y único en la colmena (ej: un sticker específico) cuando acabas de respawnear.
    *   Si el bot no detecta este color al iniciar, sabrá que la cámara está mal y se reiniciará.
    *   *(Opcional)* **Spawn #2**: Un segundo punto de chequeo para mayor seguridad.
*   **🏃 Anti-Stuck (Movimiento)**:
    *   Detecta si el bot se ha trabado o salido del campo.
    *   Captura una zona que **siempre cambie** mientras farmeas (ej: los números de polen/segundo en la parte superior).
    *   Si esos números no cambian por X segundos (ej: 30s), el bot asume que está atascado y se reinicia.
*   **⏰ Reloj (Cuenta Regresiva)**:
    *   Si se activa, el bot se detendrá y reiniciará cuando el contador llegue a 0.
    *   Útil para recolectar tickets cada hora.

### 4. Multi-Bot 🔄
La versión avanzada para farmear en múltiples campos.
*   Crea una **Cola de Tareas**:
    *   Elige una **Ruta** (Campo).
    *   Define la **Duración** en minutos.
    *   Elige el **Patrón** de movimiento para ese campo.
*   El bot completará la tarea y pasará automáticamente a la siguiente.
*   **Nota**: Hereda todas las configuraciones del Smart Bot (Mochila, Spawn, Anti-Stuck, Reloj).

### 5. Ajustes y Teclas ⚙️
*   **Tecla Automática**: Configura una tecla (ej: `1`) para que se presione cada cierto tiempo (ej: 30s). Útil para poner aspersores (sprinklers) automáticamente.
*   **Reinicio por Tiempo**: Fuerza un reinicio del personaje cada X minutos para prevenir errores acumulados o que el personaje se desvíe demasiado.

---

## ⚠️ Notas Importantes
> [!NOTE]
> Por ahora, cuando la mochila se llena, **el bot siempre reinicia el personaje**. No camina de vuelta a la colmena ni convierte miel automáticamente. Estas funcionalidades podrían llegar en futuras actualizaciones.

> [!TIP]
> Si tienes problemas con el detector de colores, intenta capturarlos nuevamente asegurándote de que nada obstruya la visión (como abejas pasando frente al cursor).
