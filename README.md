# Proyecto-de-pruebas-A-B

## Introducción
En el entorno competitivo de las tiendas en línea, la toma de decisiones basada en datos es esencial para mejorar la experiencia del usuario y aumentar las conversiones. Este proyecto se centra en un análisis exhaustivo de datos recopilados de una tienda en línea durante un período específico, con el objetivo de evaluar la efectividad de diferentes estrategias de marketing mediante una prueba A/B.

El análisis se lleva a cabo en varias etapas, comenzando con la Exploración de Datos (EDA), que incluye la limpieza y preparación de los datos, identificación de patrones y tendencias, y la corrección de cualquier peculiaridad que pueda afectar la validez del análisis. Posteriormente, se realiza una prueba A/B para comparar dos variantes de estrategias de marketing implementadas en grupos de usuarios distintos.

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

## Herramientas Usadas
- **Python**:
  - Manipulación y análisis: `Pandas`
  - Visualización: `Matplotlib`, `Seaborn`
  - Pruebas estadísticas: `Scipy.stats`
- **Entorno**:
  - Jupyter Notebook.

## Conclusiones
que la variante aplicada en el grupo A es más efectiva para lograr conversiones.

Estos resultados son prometedores y sugieren que la variante del grupo A podría ser la mejor opción para implementar.

Conclusión
Usuarios Duplicados: Identificamos que había 441 usuarios presentes en ambos grupos de la prueba A/B. Esto podría afectar la independencia de las muestras, por lo que se corrigió excluyendo estos usuarios de ambos grupos.

Picos de Actividad: Se observó un pico significativo de actividad en torno al 22 de diciembre, lo cual se atribuyó a eventos de marketing o promociones. Para mitigar este impacto, se aseguró que estas influencias estuvieran distribuidas equitativamente entre los grupos, o se ajustó el período de la prueba.

Número de Eventos por Día: Se analizó cómo se distribuían los eventos entre los días, identificando patrones y picos de actividad. Esto ayudó a entender mejor el comportamiento de los usuarios y ajustar el análisis para considerar estos factores.

Número de Eventos por Usuario: Se verificó que la distribución del número de eventos por usuario fuera consistente entre los grupos, asegurando que no hubiera sesgos significativos.

Limpieza y Filtrado: Se realizó una limpieza exhaustiva de los datos, eliminando duplicados y asegurando que los datos fueran precisos y confiables.

Homogeneidad de las Muestras: Se verificó que las muestras de los grupos A y B fueran homogéneas en términos de características clave como región y dispositivo, garantizando una comparación justa.

La etapa de EDA permitió identificar y corregir peculiaridades en los datos, asegurando la calidad y precisión del análisis. Los resultados de la prueba A/B mostraron que el grupo A tuvo una tasa de conversión y un compromiso del usuario superiores en comparación con el grupo B. La prueba Z confirmó que estas diferencias eran estadísticamente significativas, lo cual sugiere que la variante del grupo A es más efectiva y podría considerarse para implementación.
