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