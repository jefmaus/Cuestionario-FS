# Senior Fullstack Interview Coach

Plataforma autocontenida de preparación técnica para entrevistas senior fullstack: simulador de exámenes, modo flashcards de repaso y un banco de preguntas con explicaciones arquitecturales profundas.

## Objetivo

El objetivo de la aplicación es servir como **simulador de entrevistas técnicas de nivel Senior** y como **hub de conocimiento** para repasar conceptos avanzados de arquitectura, patrones de diseño y escenarios reales de producción. Permite seleccionar categorías y tecnologías, configurar la cantidad de preguntas y estudiar en dos modos de aprendizaje:

- **Flashcards (Estudio):** muestra la pregunta con un resumen técnico clave y una explicación arquitectural profunda.
- **Examen (Quiz):** modo de opción múltiple con puntuación, precisión y resumen final.

## Características

- **7+ categorías técnicas:** Backend, Frontend, Bases de Datos, Arquitectura, Herramientas y Entornos, IA & LLMs, DevOps, Otros.
- **741 preguntas** con nivel (Junior/Mid/Senior), respuesta corta, explicación detallada y 4 opciones de quiz.
- **Selección flexible:** marcar/desmarcar categorías, cantidad de preguntas (1–100) y modo de estudio.
- **Motor SQLite cliente-side (sql.js):** la base de datos `banco_preguntas_fullstack.db` puede cargarse como fuente externa.
- **Progreso en vivo:** barra de avance, contador de aciertos y resumen final con precisión.
- **100% autocontenido:** un solo archivo HTML sin backend ni instalación (usa Tailwind CDN y Font Awesome).

## Archivos

| Archivo | Descripción |
|---------|-------------|
| `cuestionario_fullstack.html` | Aplicación completa (interfaz + dataset de preguntas embebido) |
| `banco_preguntas_fullstack.db` | Base de datos SQLite con todas las preguntas (categoría, tecnología, nivel, pregunta, respuestas, opciones) |

## Cómo usar

1. Abre `cuestionario_fullstack.html` en cualquier navegador moderno (requiere conexión a internet para CDNs).
2. Selecciona las categorías y tecnologías a evaluar.
3. Ajusta la cantidad de preguntas y el modo (Flashcards o Examen).
4. Pulsa **Iniciar Cuestionario**.
5. Al finalizar, consulta el resumen de la sesión o reinicia.

Opcional: usa el selector *"Cargar Base de Datos .db externa"* para cargar una versión actualizada de la base de preguntas.

## Estructura de la base de datos

Tabla `preguntas`:

| Columna | Descripción |
|---------|-------------|
| `id` | Identificador único |
| `categoria` | Categoría técnica (Backend, Frontend, Arquitectura, ...) |
| `tecnologia` | Tecnología específica (Java / Spring Boot, Angular, ...) |
| `nivel` | Junior, Mid o Senior |
| `pregunta` | Texto de la pregunta |
| `respuesta_corta` | Resumen técnico clave |
| `respuesta_detallada` | Explicación arquitectural profunda |
| `opciones_json` | JSON con 4 opciones de quiz |
| `opcion_correcta` | Índice de la opción correcta (0-3) |
