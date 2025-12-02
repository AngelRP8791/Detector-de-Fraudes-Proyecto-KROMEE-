# Estructura del Proyecto.

│   .gitignore # Exclusión de archivos en el repositorio
│   environment.yml # Definir dependencias para recrear el entorno del proyecto
│   License
│   README.md
│   requirements.txt # Definir dependencias Python (ejecutar con `pip`)
│
├───data # Data Scientist
│   ├───interim # almacena los datos procesados sin ser la data concluida
│   ├───processed # Datos totalmente procesados
│   └───raw # Datos en crudo (no modificar)
├───design # para los diseñadores gráficos
│   ├───assets
│   ├───branding
│   └───logo
├───docs
│   │   estructura_proyecto.md
│   │
│   ├───api-docs # documentación técnica de la API
│   ├───architecture # explicación de la arquitectura
│   ├───proyect-planning # Planeación del proyecto
│   └───UX-UI # documentación del proceso UX-UI
├───notebooks # Data Scientist
│       1. EDA.ipynb # Exploración y limpieza de datos
│       2. feature_engineering.ipynb # pruebas
│       3. Model_training.ipynb # entrenamiento de modelos
│       4. Model_validation.ipynb # evaluación de los resultados de los modelos
│
└───src # código
    ├───backend
    │   │   app.py
    │   │
    │   ├───routes
    │   ├───services
    │   ├───tests
    │   └───utils
    ├───data # Data Scientist
    │       feature_engineering.py
    │       load_data.py
    │       preprocess.py
    │
    ├───frontend
    │   ├───public
    │   └───src
    │       │   package.json
    │       │
    │       ├───api
    │       ├───components
    │       ├───hooks
    │       ├───pages
    │       └───styles
    ├───models # Data Scientist
    │       model.plk # Modelo entrenado
    │       predict.py # Predicciones (resultados que arroje el modelo)
    │       train.py # Proceso de entrenamiento del modelo.
    │
    └───utils
            logger.py


            Flujo de Ramas (Branch Flow)

1.- Ramas principales.

main: Rama estable.
•	Contiene la versión final del proyecto.
•	Solo recibe cambios mediante Pull Request provenientes de develop o ramas release.
•	Todo el código aquí debe estar probado y validado.

develop: Rama de integración.
•	Aquí se integran todos los avances del equipo..
•	Se utiliza para pruebas, revisiones y validación antes de liberar una versión en main.
•	Todas las ramas de desarrollo deben partir desde esta rama..


2.- Ramas de Desarrollo.

Ramas feature: funcionalidades nuevas.

Se utilizan para desarrollar un componente, módulo o tarea específica..

Código:
feature/nombre-descriptivo

Ejemplos:
•	feature/eda-limpieza.
•	feature/backend-auth-service
•	feature/frontend-dashboard-ui
•	feature/model-entrenamiento
•	feature/UX-wireframes

Flujo (reglas):

1.	Se crean a partir de develop.
2.	Al terminar el trabajo, se realiza un Pull Request a develop.
3.	Una vez fusionadas, deben eliminarse.


Ramas bugfix: Corrección de errores..

Para resolver problemas identificados en develop.

Código:
bugfix/nombre-del-bug.

Ejemplos:
•	bugfix/preprocesamiento-nulos.
•	bugfix/api-401
•	bugfix/frontend-navbar


Ramas hotfix: correcciones urgentes.

Para solucionar errores críticos en producción.

Código:
hotfix/descripción-corta

Flujo:

1.	Se crea desde main.
2.	Se fusionan a main y también a develop para mantener sincronización..


Ramas release: Preparación de versiones.

Para cerrar versiones importantes antes de pasarlas a producción.

Código:
release/vX.X

3.- Convenciones de nombres.

Ajustarse al contenido del archivo/documento convenciones_nombres.md.

Ubicación: docs\convenciones_nombres.md


4.- Reglas de colaboración.

•	Nadie trabaja directamente en main.
•	Todo cambio debe pasar por un Pull Request.
•	Toda rama debe incluir:
	Descripción del objetivo.
	Cambios realizados.
	Evidencia de pruebas (si aplica).
•	Las ramas deben eliminarse después de fusionarse.


5.- Diagramas ASCII del fujo de Ramas.

                     +------------------------+
                     |        main (prod)     |
                     +------------------------+
                               ^
                               |   (PR desde release o hotfix)
                  +------------+-------------+
                  |                          |
                  |                          |
        +-------------------+        +-------------------+
        |   release/vX.X    | <-----+    hotfix/...     |
        +-------------------+        +-------------------+
                  ^                          ^
                  |                          |
                  | (PR desde develop)        | (creada desde main)
                  |                          |
        +-------------------+                |
        |     develop       |----------------+
        +-------------------+
                  ^
       (PR desde feature o bugfix)
                  |
    +-------------------+
    |  feature/...      |
    +-------------------+
                  |
    +-------------------+
    |  bugfix/...       |
    +-------------------+

4.- Reglas de Colaboración.

•	No se permite commits directos en main.
•	Todo cambio debe pasar por Pull Request, revisión y aprobación.
•	Cada tarea debe manejarse en una rama independiente.
•	Las ramas deben eliminarse tras fusionarse.
•	Documentar en cada Pull Request:
	Objetivo
	Cambios realizados.
	Evidencia de pruebas (cuando aplique).
