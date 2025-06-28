# Comparativo Técnico: Motoman MH6 vs ABB IRB 140

Este documento presenta un cuadro comparativo detallado de las características técnicas de los robots industriales **Motoman MH6** y **ABB IRB 140**, incluyendo aspectos como carga máxima, alcance, grados de libertad, velocidad, aplicaciones típicas, entre otros.

## Tabla Comparativa

| Característica                    | Motoman MH6                          | ABB IRB 140                             |
|-----------------------------------|--------------------------------------|-----------------------------------------|
| **Fabricante**                    | Yaskawa Motoman                      | ABB                                     |
| **Carga útil máxima**             | 6 kg                                 | 6 kg                                    |
| **Alcance máximo**                | 1,424 mm                             | 810 mm                                  |
| **Grados de libertad (DOF)**      | 6                                    | 6                                       |
| **Velocidad máxima por eje**      | Eje S: 180°/s  <br> Eje L: 180°/s  <br> Eje U: 180°/s  <br> Eje R: 400°/s  <br> Eje B: 400°/s  <br> Eje T: 610°/s | Eje 1: 150°/s  <br> Eje 2: 150°/s  <br> Eje 3: 150°/s  <br> Eje 4: 330°/s  <br> Eje 5: 330°/s  <br> Eje 6: 660°/s |
| **Repetibilidad**                 | ±0,08 mm                             | ±0,03 mm                                |
| **Peso del robot**                | 130 kg                               | 98 kg                                   |
| **Montaje**                       | Piso, techo, pared                   | Piso, techo, pared                      |
| **Aplicaciones típicas**          | - Manipulación de materiales <br> - Ensamblaje <br> - Pulido <br> - Soldadura por arco <br> - Carga y descarga | - Manipulación de materiales <br> - Ensamblaje <br> - Soldadura <br> - Embalaje <br> - Laboratorios |
| **Protección ambiental**          | IP54 estándar, opción IP65           | IP54 estándar, opción IP67              |
| **Controlador compatible**        | DX100 / DX200                        | IRC5 Compact                            |
| **Consumo energético aproximado** | 1.0 kW                               | 0.58 kW                                 |
| **Ventajas destacadas**           | - Gran alcance <br> - Flexible <br> - Adecuado para trabajo en espacios abiertos | - Alta precisión <br> - Compacto <br> - Ideal para espacios reducidos |

## Resumen

- **Motoman MH6**: Ideal para aplicaciones que requieren un gran **alcance**, flexibilidad de montaje y tareas como soldadura, pulido y manipulación de materiales en espacios amplios.
- **ABB IRB 140**: Excelente opción para aplicaciones en **espacios reducidos** gracias a su tamaño compacto y alta **precisión (repetibilidad de ±0,03 mm)**. Su velocidad y consumo energético más bajos lo hacen eficiente para tareas de ensamblaje fino y aplicaciones de laboratorio.


## 1. Configuraciones Home1 y Home2 del Motoman MH6

# Manual de Operación y Simulación - Robot Motoman

El robot Motoman MH6 permite definir múltiples posiciones de referencia conocidas como "Home1" y "Home2". Estas posiciones son establecidas por el usuario y suelen ser utilizadas para retornar a ubicaciones seguras o estratégicas dentro del espacio de trabajo.
Home1: Posición segura o de reposo

Se configura lejos del área de trabajo.

Útil para inicio y finalización del ciclo, o ante situaciones de emergencia.

Normalmente, todas las articulaciones están en posición neutral.

![Home1](Home%201.jpg)
![Home1.1](Home%201%20fisico.jpg)

Home2: Posición operativa o de transición

Se ubica más cerca del área de trabajo o del primer punto de proceso.

Útil como punto de partida para tareas productivas.

Permite reducir el tiempo de ciclo y evitar movimientos innecesarios.

![Home2](Home%202%20.jpg)
![Home2.2](Home%202%20fisico.jpg)

## 2. Procedimiento para Movimientos Manuales

### Modos de Operación
Los robots Motoman permiten el control manual en **dos modos principales**:
- **Modo de Articulación (Joint Mode):** Permite mover cada articulación de manera independiente.
- **Modo Cartesiano (Rectilinear Mode):** Permite mover el TCP (Tool Center Point) en los ejes X, Y, Z.

### Procedimiento Paso a Paso
1. Encender el robot y activar el Teach Pendant.
2. Seleccionar el modo manual usando el interruptor de operación.
3. Liberar el freno de los motores si el modelo lo requiere.
4. Cambiar el modo de movimiento presionando la tecla `COORD` o `MODE`:
   - **Joint:** Movimiento por articulaciones.
   - **Rectilinear (XYZ):** Movimiento cartesiano.
5. Seleccionar el sistema de coordenadas: **WORLD**, **USER**, **TOOL** u **ORIGIN**.
6. Realizar movimientos manuales:
   - **Modo Articulación:** Cada botón mueve una articulación específica.
   - **Modo Cartesiano:**
     - Traslaciones: Movimiento en los ejes X, Y, Z.
     - Rotaciones: Giros alrededor de los ejes X, Y, Z (Rx, Ry, Rz).
7. Confirmar la posición y realizar ajustes si es necesario.

---

## 3. Niveles de Velocidad para Movimientos Manuales

### Niveles Disponibles
- **Baja Velocidad (LOW):** Aproximación segura y precisa.
- **Media Velocidad (MEDIUM):** Desplazamientos moderados.
- **Alta Velocidad (HIGH):** Velocidad máxima permitida en modo manual.

### Cambio de Velocidad
- Presionar la tecla `Speed` o `Vel` para alternar entre los niveles.
- La velocidad actual se muestra en pantalla:
  - **L:** Baja velocidad.
  - **M:** Velocidad media.
  - **H:** Alta velocidad.
  - Puede mostrarse también como porcentaje (ej. 10%, 50%, 100%).

### Consideraciones
- Algunos robots permiten ajuste fino del porcentaje de velocidad.
- El nivel de velocidad afecta todos los modos de movimiento manual.
- Las velocidades están limitadas por los parámetros de seguridad.

---

## 4. RoboDK - Funcionalidades y Comunicación con Motoman

### Principales Funcionalidades
- **Programación Offline:** Crear y simular trayectorias sin afectar la operación real.
- **Simulación 3D:** Visualización en tiempo real de movimientos y posibles colisiones.
- **Post-Procesadores:** Generación de código específico para el robot (lenguaje INFORM para Motoman).
- **Interfaz Gráfica Intuitiva:** Programación mediante bloques o importación desde CAD/CAM.
- **Compatibilidad Multimarca:** Compatible con Motoman, FANUC, ABB, KUKA, Universal Robots, entre otros.
- **Cálculo de Cinemática Inversa:** Solución automática de posiciones articulares.

### Comunicación con Robot Motoman
- Conexión a través de **Ethernet/IP o FTP** para transferencia de programas.
- **Control Remoto:** RoboDK permite controlar el robot en tiempo real desde la interfaz.
- **Integración con MotoSim:** Complementa la simulación con herramientas específicas de Motoman.

### Flujo de Trabajo
1. Crear trayectorias en RoboDK.
2. Seleccionar post-procesador Motoman.
3. Exportar el programa al robot mediante red o USB.
4. Cargar el programa en el Teach Pendant.
5. Ejecutar los movimientos en el robot físico.
6. Alternativamente, RoboDK puede enviar comandos en tiempo real al robot.

## 5. RoboDK - Robotstudio 

RoboDK:

Software multimarcas.

Intuitivo y educativo.

Usado para simulación, programación offline y automatización por scripts.

RobotStudio:

Exclusivo para robots ABB.

Altamente preciso gracias al controlador virtual.

Permite programar en RAPID y simular con fidelidad exacta al comportamiento físico del robot.

RoboDK es ideal para aprender y experimentar con distintas marcas de robots. RobotStudio, por su parte, es perfecto para desarrollos avanzados en entornos ABB donde la precisión y validación previa al despliegue son cruciales.
---
Video: https://youtu.be/uwRJfNl4Qbc

### Referencias
- Yaskawa Motoman Robot Manuals.
- RoboDK Documentation.
- MotoSim EG-VRC User Guide.



> ✅ Este README proporciona una guía práctica para operadores, programadores y estudiantes que deseen trabajar con robots Motoman y RoboDK.
