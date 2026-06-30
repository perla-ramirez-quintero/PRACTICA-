# PORTAFOLIO DE EVIDENCIAS DIGITALES: INNOVACIÓN Y DESARROLLO DE APLICACIONES INTERACTIVAS
**Licenciatura en Educación Preescolar** **Curso:** Tecnologías Digitales en la Práctica Educativa  
**Alumna (Docente en Formación):** Perla Ramírez Quintero  

---

## 1. Datos de Identificación y Acceso al Proyecto

* **Nombre de la Autora:** Perla Ramírez Quintero
* **Perfil de GitHub Central:** [https://github.com/perla-ramirez-quintero](https://github.com/perla-ramirez-quintero)
* **Marco Curricular de Referencia:** Nueva Escuela Mexicana (NEM), Fase 2 (Educación Preescolar, Multigrado 1º, 2º y 3º).

---

## 2. Directorio Técnico del Proyecto (Repositorios y Despliegues)

* **Repositorio Base:** `CREACION-Y-EXPLORACION` (o carpeta de trabajo asociada a planeaciones)
* **Módulo Interactivo ("El Pirata Numerón"):** `pirata_numeron.html`
* **Planeación Didáctica NEM:** `planeacion_pirata_numeron.md`
* **Guía de Interacción (WhatsApp para Padres):** `instrucciones_pirata_numeron.md`

---

## 3. Bitácora de Desarrollo y Ajustes Técnicos (Iteración del Recurso)

La adaptación de la actividad permanente "El Pirata Numerón" (búsqueda y seriación de crayolas numéricas en la arena) requirió un proceso de depuración iterativa para garantizar su correcto funcionamiento didáctico y responsivo en el aula:

1. **Estructuración Modular de la Dinámica (Versión Inicial):**
   * Se concibió un entorno gráfico dividido en 3 niveles de dificultad progresiva:
     * **Nivel 1 (Conteo - 1º):** Búsqueda de crayolas numeradas en la escena pirata con retroalimentación sonora de conteo y animación de desplazamiento hacia la caja.
     * **Nivel 2 (Comparación - 2º):** Desafíos dinámicos de mayor/menor, detección de números secretos y equilibrio de balanza pirata agregando elementos.
     * **Nivel 3 (Seriación - 3º):** Ordenamiento secuencial de crayolas extendido hasta el número 20 (organizado en dos filas de 10 ranuras) para ajustarse al grado superior de preescolar, eliminando la monotonía de la versión 2.
2. **Depuración de Restricción Secuencial (Nivel 1):**
   * *Incidencia:* El sistema permitía inicialmente pulsar las crayolas desordenadamente (ej. presionar el 5 antes del 1), lo cual contravenía el objetivo pedagógico de seriación.
   * *Solución:* Se implementó validación estricta de secuencia numérica. Si se pulsa un número incorrecto, se emite una alerta auditiva, la crayola se amplía como advertencia visual y la voz del pirata guía al alumno sobre el número exacto que debe buscar. La interfaz superior muestra el conteo en tiempo real (ej. "Encontradas: 2 / 5 | Busca la Nº 3").
3. **Optimización de Capas y Colisiones (CSS Pointer Events):**
   * *Incidencia:* Clics en ciertas áreas de la pantalla ("zonas ciegas") no respondían al tacto debido a elementos decorativos transparentes en el plano superior (palmeras, rocas, barriles).
   * *Solución:* Se inyectó la propiedad `pointer-events: none` en la hoja de estilos CSS a todos los elementos decorativos, permitiendo que los toques de los estudiantes atraviesen dichas capas e incidan directamente sobre las crayolas.
4. **Robustez en el Binding de Datos:**
   * Se vinculó el número de orden de cada crayola directamente en los metadatos del DOM (`dataset.num = i`), eliminando problemas de alcance de variables e intermitencias en la respuesta táctil de dispositivos móviles, resolviendo el fallo donde el número 2 no respondía.

---

## 4. Sustento Pedagógico (Alineación NEM - Fase 2)

La actividad digital se encuentra anclada a los Procesos de Desarrollo de Aprendizaje (PDA) de la Nueva Escuela Mexicana:

* **Campo Formativo:** Saberes y Pensamiento Científico.
* **Prioridad Cognitiva:** Construcción del concepto de número y seriación. Mediante la gamificación, los alumnos manipulan de manera gráfica y táctil los números, comprendiendo la cardinalidad y el orden ordinal hasta el 20.
* **Ejes Articuladores:**
  * *Pensamiento Crítico:* Al resolver el acertijo de secuencias y equilibrar la balanza pirata.
  * *Inclusión:* Al proveer apoyos visuales y auditivos que guían al alumno en su propio ritmo de aprendizaje.
* **Metodología:** Aprendizaje Situado. El juego traslada la dinámica física del aula ("la mesa de arena") a un entorno digital accesible, sirviendo también como puente de vinculación con los padres de familia mediante guías de acompañamiento a distancia.

---

## 5. Anexo Técnico: Transcripción Íntegra de la Conversación (Raw Logs)

**8:40, 2/6/2026 - Usuario (Docente en Formación):**
> El dia de hoy quiero hacer un juego sobre EL PIRATA NUMERÓN esto es una actividad permantente que implementé donde los números "se pierden" y los niños los buscan y los ordenan; la forma de los numeros son crayolas y los ordenan en una caja de crayolas. ¿Qué propones que hagamos?

**8:40, 2/6/2026 - IA (Asistente Técnico):**
> ¡Hola! Qué maravillosa actividad. Te propongo llevar esta dinámica al ámbito digital con tres niveles:
> - Nivel 1 (1º): Buscar crayolas escondidas. Al tocarlas, la voz cuenta y viajan a la caja.
> - Nivel 2 (2º): Comparar dos cajas para adivinar cuál tiene más/menos.
> - Nivel 3 (3º): Ordenar crayolas dispersas en la arena secuencialmente en la caja.
> Además, crearemos la planeación didáctica NEM y las instrucciones para padres por WhatsApp.

**8:42, 2/6/2026 - Usuario (Docente en Formación):**
> abre otra cosa (no sé como se llame) pero no trabajes en exploradores numericos

**8:49, 2/6/2026 - Usuario (Docente en Formación):**
> me gusta, pero necesito que se trabaje hasta el 20 en el nivel 3, además el nivel 2 me parece muy repetitivo, cambia eso

**8:49, 2/6/2026 - IA (Asistente Técnico):**
> ¡Excelente! He implementado las mejoras en archivos independientes:
> - Juego: `pirata_numeron.html` (Nivel 3 hasta el 20, con la caja expandida en dos filas de 10. Nivel 2 modificado con retos aleatorios: mayor/menos, número secreto, y equilibrar balanza con un botón dorado +).
> - Planeación Didáctica NEM: `planeacion_pirata_numeron.md` (con actividades físicas en el aula, como uso de balanza en mesa de arena).
> - Instrucciones WhatsApp: `instrucciones_pirata_numeron.md`.

**11:41, 23/6/2026 - Usuario (Docente en Formación):**
> en este juego, el nivel 1 me deja poner cualquier numero no importa el orden, lo cual me afecta porque no corrige a los niños cuando ponen por ejemplo el 5 primero o etc

**11:41, 23/6/2026 - IA (Asistente Técnico):**
> ¡Hola de nuevo! Ya he corregido esto. Ahora, en el Nivel 1:
> - Validación de Secuencia: Exige tocar las crayolas estrictamente en orden (1 al 5).
> - Corrección de Voz y Animación: Si tocan uno equivocado, suena un aviso, la crayola se agranda visualmente y la voz del pirata indica amablemente buscar el número correcto.
> - Indicaciones en Pantalla: Actualicé la barra superior guiando al niño (ej. "Encontradas: 2/5 | Busca la Nº 3"). Archivos actualizados: `pirata_numeron.html`, `planeacion_pirata_numeron.md`, `instrucciones_pirata_numeron.md`.

**11:43, 23/6/2026 - Usuario (Docente en Formación):**
> pasa algo extraño, no me deja tocar el numero dos, no pasa nada

**11:43, 23/6/2026 - IA (Asistente Técnico):**
> Ya descubrí el problema y lo he solucionado:
> 1. Elementos decorativos interceptaban los toques al estar en capas superiores. Se aplicó `pointer-events: none` en CSS a la decoración para que los clics pasen directo a las crayolas.
> 2. Se agregó robustez guardando el número de orden directamente en los metadatos del elemento DOM (`dataset.num = i`) para evitar interferencias de variables al hacer clic. El juego se encuentra actualizado en `pirata_numeron.html`.

**11:45, 23/6/2026 - Usuario (Docente en Formación):**
> bien gracias
