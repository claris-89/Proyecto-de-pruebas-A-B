# Proyecto-de-pruebas-A-B

### Descripción de la Prueba
- **Nombre de la prueba**: recommender_system_test
- **Grupos**:
  - A: Control
  - B: Nuevo embudo de pago
- **Fechas Importantes**:
  - Fecha de lanzamiento: 2020-12-07
  - Fecha de aceptación final de nuevos usuarios: 2020-12-21
  - Fecha de finalización: 2021-01-01
- **Audiencia**: 15% de nuevos usuarios de la región UE
- **Propósito**: Evaluar el impacto de un nuevo sistema de recomendaciones en la conversión de los usuarios a lo largo del embudo: 
  `product_page → product_cart → purchase`.
- **Resultado Esperado**:
  - Aumento mínimo del 10% en conversión en cada etapa del embudo.
- **Número previsto de participantes**: 6,000 usuarios.

---

## Objetivos del Estudio
1. **Verificar los datos de la prueba**:
   - Validar el cumplimiento de los criterios iniciales.
   - Identificar posibles problemas en los datos.
2. **Explorar los datos**:
   - Determinar si se necesita conversión de tipos de datos.
   - Identificar valores ausentes y duplicados.
   - Analizar la distribución y características de los eventos.
3. **Evaluar los resultados de la prueba A/B**:
   - Comparar las conversiones en cada etapa del embudo para los grupos A y B.
   - Comprobar diferencias estadísticas entre grupos utilizando una prueba z.
4. **Sacar conclusiones**:
   - Determinar la eficacia del nuevo sistema de recomendaciones.
   - Proporcionar observaciones y recomendaciones basadas en los hallazgos.

---

## Exploración Inicial de los Datos

### 1. Carga y Exploración de Datos
#### Archivos incluidos:
- **`ab_project_marketing_events_us.csv`**: Calendario de eventos de marketing.
- **`final_ab_new_users_upd_us.csv`**: Información de los nuevos usuarios registrados durante la prueba.
- **`final_ab_events_upd_us.csv`**: Todos los eventos registrados durante la prueba.
- **`final_ab_participants_upd_us.csv`**: Participantes de la prueba A/B.

#### Tareas:
1. Verificar la estructura de cada dataset (`head()`, `info()`, `describe()`).
2. Revisar tipos de datos y convertirlos, si es necesario.
3. Identificar y analizar valores ausentes (`isnull()`).
4. Detectar y eliminar duplicados (`duplicated()`).

---

## Análisis Exploratorio de Datos (EDA)

### 2. Distribución de Eventos y Usuarios
1. **Eventos por Usuario**:
   - Calcular el número promedio de eventos por usuario.
   - Comparar entre grupos A y B.
2. **Presencia en Ambas Muestras**:
   - Identificar si algún usuario pertenece tanto al grupo A como al B.
3. **Distribución Temporal**:
   - Graficar el número de eventos por día.
   - Identificar patrones o anomalías.

### 3. Conversión a lo Largo del Embudo
1. **Conversión por Etapa**:
   - `product_page → product_cart → purchase`.
   - Calcular las tasas de conversión para cada etapa y por grupo (A y B).
2. **Visualización**:
   - Graficar las tasas de conversión en cada etapa para ambos grupos.

---

## Evaluación de la Prueba A/B

### 4. Prueba de Hipótesis
1. **Estadísticas Iniciales**:
   - Contar el número de usuarios por grupo.
   - Calcular la proporción de conversión en cada etapa.
2. **Prueba Z de Proporciones**:
   - Comparar las proporciones entre los grupos A y B en cada etapa:
     - `product_page → product_cart`
     - `product_cart → purchase`
   - Determinar si las diferencias son estadísticamente significativas.
3. **Nivel de Significancia**:
   - Usar un nivel de significancia estándar (e.g., 0.05).
   - Ajustar si se realizan múltiples pruebas (Bonferroni si es necesario).

---

## Conclusiones

### 5. Resumen de Resultados
1. Describir:
   - Comportamiento de los usuarios en el embudo.
   - Diferencias observadas entre los grupos A y B.
2. Evaluar:
   - Si el nuevo sistema de recomendaciones logró el resultado esperado (10% de mejora en cada etapa).

### 6. Recomendaciones
- Decidir si implementar el nuevo sistema basado en los resultados.
- Sugerir mejoras adicionales para futuros experimentos o análisis.

---

## Herramientas Recomendadas
- **Python**:
  - Manipulación y análisis: `Pandas`
  - Visualización: `Matplotlib`, `Seaborn`
  - Pruebas estadísticas: `Scipy.stats`
- **Entorno**:
  - Jupyter Notebook.
