Convenciones nombres

1.- Apegarse en la medida de lo posible a las reglas PEP-8:

https://peps.python.org/pep-0008/


2.- Paquetes en Python (carpetas con init.py)
    Nombrar en `snake_case`: debe representar la responsabilidad del paquete
    Ejemplos:
    data_ingestion/
    feature_engineering/
    visualizations/
    model_training/
    api_service/

3.- JavaScript(Front-End)
    
    3.1 Archivos de componentes: Usar nomenclatura `PascalCase`
        Ejemplos:
        Header.jsx
        UserCard.jsx
        LoginForm.jsx

    3.2 Archivos Utilitarios; usar nomenclatura `camelCase`
        Ejemplo:
        formatDate.js
        calculateRisk.js

    3.3. Carpetas de componentes: usar `PascalCase`
        components/
            UserProfile/
            DashboardCard/

4.- Archivos UX-UI
    Imágenes / assets:
    -   Usar nomelclatura kebab-case (muy común en diseño/UX)
    -   Palabras separadas por guines
    -   Añadir tamaño si aplica
    logo-primary.png
    background-dark.jpg
    icon-alert-24px.svg

5.- En caso de requerir agregar carpetas al repositorio:
    5.1 para carpetas de trabajo técnico usar nomenclatura `snake_case`
    5.2 para assets gráficos: usar nombres descriptivos, cortos y sin 
        ambigüedades.
        Ejemplos:
        data/
        notebooks/
        design/
        design/assets/
        frontend/
        backend/
        api/
        tests/
        docs/
        scripts/

6.- En caso de requerir agregar mas archivos, preferentemente utilizar prefijos que expliquen su necesidad:
    Ejemplos:
    6.1 Para Data Science:
        etl_*.py
        eda_*.ipynb
        model_*.py
        preprocess_*.py
    
    6.2 Para API backend:
        routes_*.py
        service_*.py
        repository_*.py

    6.3 Para frontend:
        use*.js (hooks)
        *.component.jsx
        *.service.js

7.- En la medida de lo posible, documentar todo.