# REPORTE DE CAMBIOS - proyecto_bicicleta.tex

## Período de Revisión
- **Commit inicial:** `1c5487bf2ebaa7c3e28cf09aaacf7f4fe835b62a`
- **Commit final:** `4733d46` (HEAD)
- **Mensaje del commit:** "Update project structure and content in 'proyecto_bicicleta.pdf' and 'proyecto_bicicleta.tex'"

## Resumen de Cambios
- **Archivo principal modificado:** `proyecto_bicicleta.tex`
- **Líneas agregadas:** +119 líneas
- **Tipo de cambio:** Adición de nueva sección completa

---

## Cambios Específicos

### ✅ NUEVA SECCIÓN AGREGADA: "Fase 6: Validación Experimental del Sistema en Condiciones Reales"

**Ubicación:** Después de la línea 1586 (tras las conclusiones de la Fase 5 de simulación)

#### 📋 Contenido agregado:

1. **Introducción a la Fase 6**
   - Objetivo: Validar el sistema físico después de la simulación
   - Verificar filtro complementario y controlador PID en condiciones reales

2. **Subsección: Adquisición y Procesamiento de Señales de los Sensores**
   - Explicación del rol del acelerómetro (MPU9250)
   - Explicación del rol del giroscopio
   - Limitaciones y ventajas de cada sensor

3. **Subsubsección: Señales Individuales de Acelerómetro y Giroscopio**
   - **Figura agregada:** `imagen80.png` (label: `fig:ace_giro_separado`)
   - Caption: Señales de acelerómetro y giroscopio en función del tiempo
   - Análisis de fluctuaciones y deriva temporal

4. **Subsubsección: Comparación entre Sensores y Filtro Complementario**
   - **Figura agregada:** `imagen81.png` (label: `fig:ace_vs_giro_vs_filtro`)
   - Caption: Comparación entre acelerómetro, giroscopio y filtro complementario
   - **TABLA NUEVA:** Análisis estadístico de 4344 muestras (21.72s @ 200Hz)
     - Label: `tab:estadisticas_sensores`
     - Métricas incluidas:
       * Ángulos inicial y final
       * Promedio, mínimo, máximo, rango
       * Desviación estándar
       * Deriva total y deriva por segundo
     - Comparación entre AccelX, GyroX y AngX (filtro)
   - **Análisis de resultados de la tabla:**
     * Menor desviación estándar del filtro (1.41° vs 11.96° y 6.06°)
     * Rango reducido (8.96° vs 94.47°)
     * Baja deriva (0.1059°/s vs -0.8826°/s del giroscopio)
     * Precisión en estado estacionario (-0.52° promedio)

5. **Subsección: Respuesta del Controlador PID en Operación Real**
   
   **Subsubsección 1: Salida del Filtro Complementario y Acción del PID**
   - **Figura agregada:** `imagen82.png` (label: `fig:filtro_pid`)
   - Caption: Filtro complementario vs salida PID
   - Análisis de acción derivativa y proporcional

   **Subsubsección 2: Comparación Temporal entre Medición y Acción de Control**
   - **Figura agregada:** `imagen83.png` (label: `fig:filtro_vs_pid`)
   - Caption: Comparación temporal filtro vs PID
   - Análisis de correlación inversa y lazo de control

6. **Subsección: Análisis de Resultados Experimentales**
   - Conclusiones sobre fusión de sensores
   - Validación de respuesta del PID
   - Confirmación de viabilidad del diseño mecánico

---

## Elementos Visuales Agregados

| Elemento | Archivo | Label | Descripción |
|----------|---------|-------|-------------|
| Figura 1 | imagen80.png | fig:ace_giro_separado | Señales separadas de acelerómetro y giroscopio |
| Figura 2 | imagen81.png | fig:ace_vs_giro_vs_filtro | Comparación de tres señales |
| Figura 3 | imagen82.png | fig:filtro_pid | Filtro vs acción PID |
| Figura 4 | imagen83.png | fig:filtro_vs_pid | Comparación temporal |
| Tabla | - | tab:estadisticas_sensores | Métricas estadísticas de sensores |

---

## Datos Cuantitativos Agregados

### Parámetros de Medición
- **Muestras totales:** 4,344
- **Tiempo de captura:** 21.72 segundos
- **Frecuencia de muestreo:** 200 Hz

### Resultados Clave del Filtro Complementario
- Desviación estándar: **1.41°** (vs 11.96° acelerómetro, 6.06° giroscopio)
- Rango de operación: **8.96°**
- Deriva por segundo: **0.1059°/s**
- Promedio: **-0.52°**

---

## Impacto Estructural

### Antes del cambio:
- El documento terminaba la Fase 5 (Simulación) sin validación experimental
- No había datos cuantitativos de pruebas reales
- Faltaban gráficas de comportamiento del sistema físico

### Después del cambio:
- ✅ Sección completa de validación experimental
- ✅ 4 figuras con datos reales del sistema
- ✅ Tabla con análisis estadístico detallado
- ✅ Justificación cuantitativa de la efectividad del filtro complementario
- ✅ Evidencia visual de la respuesta del PID en operación real
- ✅ Coherencia entre simulación (Fase 5) y experimentación (Fase 6)

---

## Verificación

- [x] Nuevo contenido agregado: **+119 líneas**
- [x] Referencias cruzadas correctas (labels y refs)
- [x] Figuras incluidas con captions descriptivos
- [x] Tabla con formato LaTeX correcto
- [x] Análisis cuantitativo respaldado con datos
- [x] Coherencia con secciones anteriores
- [x] PDF compilado exitosamente (77 páginas)

---

## Notas Adicionales

- Los archivos auxiliares de LaTeX fueron regenerados (`.aux`, `.lof`, `.lot`, `.toc`, `.out`)
- El PDF actualizado tiene **77 páginas totales**
- Tamaño del PDF: ~7.5 MB
- Todas las referencias de figuras se compilaron correctamente (salvo 2 referencias no definidas de secciones anteriores: `fig:sistema_direccion` y `fig:comparacion_desgaste`)

---

**Revisión preparada el:** 18 de abril de 2026
**Autor de cambios:** AndresR
**Estado:** ✅ Completado y compilado
