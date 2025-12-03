Lineamientos de Estilo y Revisión del Proyecto

1.- Convenciones generales de Estilo.

    1.1. Python (Data Science y Backend)
        -   Seguir PEP-8:
            Documentación PEP-8: https://peps.python.org/pep-0008/
        
        -   Longitud máxima por línea: 79 caracteres.
        -   Nombres:
            -   Archivos y módulos: `snake_case`-
            -   Funciones: `snake_case`
            -   Clases: `CamelCase`
            -   Constantes: `UPPER_CASE`
        -   En la medida de lo posible, usar tipado:
            def load_data(path: str) -> pd.DataFrame:
                ...
    
    1.2. JavaScript / React (Frontend).
        -   Usar ES6+
            Documentación ES6+: https://info340.github.io/es6.html
        -   Componentes en`PascalCase`, funciones en `camelCase`
        -   Un componentes por archivo.
        -   Código formateado con Prettier.
        -   Estilos en `styles/` bajo convención consistente.

    1.3. Notebooks (Data Science).
        Cada Notebook debe contener secciones obligatorias:
        1.  Intoducción.
        2.  Descripción de datos.
        3.  Preparación y preprocesamiento.
        4.  Análisis / Modelo.
        5.  Resultados
        6.  Conclusiones
        7.  Notas de reproductibilidad (versión de librerías, seeds, fecha)

    1.4. Documentación.
        -   Redacción cara y concisa.
        -   Uso consistente de títulos y subtítulos.
        -   Diagramas en `docs/architecture` o `docs/api-docs`.
        -   Archivos en formato Markdown.
    
2.- Estándar para mensajes de commit.
    Usar prefijos convencionales.
    -   `feat`: nueva funcionalidad.
    -   `fix`; corrección de error.
    -   `docs`: Cabios de documentación.
    -   `refactor`: mejoras internas sin cambiar funcionalidad.
    -   `test`: inclusión o actualización de test.
    .   `style`: formato, espacios, sangrías sin afectar lógica.

3.- Reglas para Pull Request (PR).
    Todo PR debe incluir:
    1.- Descripción del objeto del cambio.
    2.  Checklist obligatorio:
    3.- Evidencia:
        -   Capturas, logs, métricas, resultados del m odelo, según corresponda.
    4.- Comparación clara con el estado previo.
    5.- Los PR's se rechazan si:
        -   Incluyen código no documentado.
        -   Mezclan cambios no relacionados
        -   Incluyen datos en `data/raw` que no deben subirse.

4.- Revisión por Pares (Peer Review).
    4.1 Reglas Generales.
        -   Obligatorio todo PR hacia `develop` o `main` requeire aprobación de al menos 1 revisor.
        -   Para cambios en modelos de ML o notebooks críticos: 2 revisores.
        -   Los revisores deben ser especialistas del área (Backend, Frontend, Data Science).
    
    4.2 Responsabilidades del Revisor.
        -   Verificar estilo y convenciones.
        -   Validar que el código funciona sin errores.
        -   Verificar limpieza del entorno y rutas.
        -   Confirmar que la documentación esté actualizada.
        -   Evaluar claridad, legibilidad y mantenibilidad.
    
    4.3 Reglas de Branches:
        -   `main`: solo recibe merges desde `develop`.
        -   `develop`: solo mediante PR revisados.
        -   Ramas de trabajo:
            -   `feature/description`
            -   `fix/description`
            -   `docs/description`
            -   `refactor/description`

5.- Protección de Branches
    El repositorio tiene la siguiente política configurada:

|    Rama    | Protección | Revisión requerida |
|------------|------------|--------------------|
|    main    | Bloqueada  |  1 - 2 revisores   |
|   develop  | Bloqueada  |     1 revisor      |
|  feature/* |   Libre    |   No obligatorio   |


6.- Anexos:

    6.1 Checklist para Pull Request (PR)

        Checklist propuesto para Pull Request
        
## Información General
**Título del PR:**
**Autor:**
**Rama de origen:**
**Rama destino:**
**Descripción breve del cambio:**
(Explicar en 3–5 líneas qué se modifica y por qué)

### Calidad del Código
- [ ] El código sigue los lineamientos de estilo del proyecto (PEP-8 / Prettier).
- [ ] Se eliminaron prints, logs innecesarios o código muerto.
- [ ] Las funciones incluyen docstrings cuando aplica.
- [ ] El código es legible y está ordenado.


### Documentación
- [ ] Se actualizó documentación relacionada (README, docs/, api-docs, etc.).
- [ ] Si se modificó un modelo o pipeline, se actualizó la documentación técnica.
- [ ] Si se modificó un notebook, se incluyó introducción, resultados y conclusiones.


### Pruebas
- [ ] Los tests asociados fueron actualizados o creados.
- [ ] Todos los tests pasan correctamente.
- [ ] Se incluyen capturas o evidencias cuando aplica.


### Estructura y Archivos
- [ ] La estructura de carpetas se respetó.
- [ ] No se incluyeron archivos temporales, cachés, `.ipynb_checkpoints`, etc.
- [ ] No se subieron datos nuevos a `data/raw/`.
- [ ] No incluye modelos pesados sin autorización del equipo.

## Revisión Técnica (Responsabilidad del Revisor)
- [ ] Se verificó consistencia, claridad y mantenibilidad del código.
- [ ] El PR está acotado (no mezcla funcionalidades distintas).
- [ ] El PR no rompe partes existentes del proyecto.
- [ ] Existen pruebas suficientes para validar el cambio.

**Revisor asignado:** @usuario
**Aprobación final:**


    6.2 Plantilla de Notebook Estándar

        Plantilla propuesta para Notebook

# Título del Notebook
Autor: Nombre del responsable
Fecha: AAAA-MM-DD
Versión de librerías: listar versiones clave
Seed utilizada: XXXX (si aplica)

## 1. Introducción
Explica brevemente el objetivo del análisis.

## 2. Descripción de los Datos
- Fuente de los datos
- Variables principales
- Breve descripción del dataset

## 3. Preprocesamiento
- Limpieza
- Transformaciones
- Eliminación o imputación de valores
- Sustento técnico de cada paso

## 4. Análisis o Modelado
- Visualizaciones
- Pruebas
- Modelos utilizados
- Justificación técnica

## 5. Resultados
- Métricas
- Gráficas
- Comparaciones

## 6. Conclusiones
- Resumen de hallazgos
- Importancia para el proyecto

## 7. Notas de Reproductibilidad
- Seeds
- Versiones
- Dependencias adicionales