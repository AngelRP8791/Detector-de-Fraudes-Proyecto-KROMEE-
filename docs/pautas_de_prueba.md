Guía de pruebas mínimas para aprobar una tarea.

Este documento establece los requisitos mínimos de pruebas que todo colaborador debe cumplir antes de marcar una tarea como completada dentro del proyecto. Su propósito es garantizar la calidad, consistencia y estabilidad en el código generado por las áreas de Backend, Frontend, Data Science y UX-UI.

1.- Objetivo.
    Definir un estándar común para realizar pruebas unitarias, pruebas de integración básicas y pruebas manuales documentadas, asegurando que todas las funcionalidades agregadas o modificadas dentro del proyecto cumplan con criterios mínimos de calidad antes de integrarse a la rama principal. ESTE ESTÁNDAR DEBE APLICARSE ANTES DE SOLICITAR REVISIÓN O APROBACIÓN DE CUALQUIER TAREA.

2.- Tipos de pruebas obligatorias.

    2.1 Pruebas Unitarias:

        Aplican para:
        -   Backend (Python / API)
        -   Lógica interna del Frontend
        -   Scripts de Data Science (procesamiento, carga, ingeniería de características)
        -   Código relacionado con modelos (entrenamiento, predicción, transformaciones)

        Requisitos mínimos:
        -   Cada módulo nuevo debe incluir al menos una prueba unitaria por función principal.
        -   Todo bug corregido debe incluir un test que valide que el error no vuelve a ocurrir.
        -   La carpeta de pruebas debe usar la estructura:
            
            src/backend/tests/
            src/data/tests/
            src/models/tests/
            src/frontend/src/__tests__/ 
        
        Frameworks recomendados:
        -   Para Python: `pytest`
        -   Para JavaScript: `jest` o `vitest`

    2.2 Pruebas de integración mínimas (cuando apliquen):

        Se requiere al menos una validación en:
        -   Rutas críticas del backend (ejmplo: `/predict`)
        -   Conexión modelo - API (cargar modelo, ejecutar predicción)
        -   Interacción backend - frontend en funciones esenciales.
        
        Estas pruebas pueden ser simples, pero deben demostrar que los componentes se comunican correctamente.

    2.3 Pruebas Manuales documentadas
        Obligatorias para:
        -   Funcionalidad visual y comportamiento del frontend.
        -   Flujos UX-UI
        -   Resultados mostrados por el modelo en notebooks.
        -   Validación en endpoints mediante Postman o cURL
        -   Verificación en archivos generados (CSV procesados, gráficos, predicciones)

        Cada prueba manual debe documentarse sujetándose a la siguiente estructura:
            ### Nombre de la prueba:
            ### Objetivo:
            ### Pasos realizados:
            ### Resultado esperado:
            ### Resultado obtenido:
            ### Evidencia (captura, link, fragmento de salida):
        La evidencia debe agregarse al Pull Request o Issue correspondiente:

3.- Cobertura mínima:
    La cobertura se medirá únicamente en áreas donde aplique el código lógico:
    -   Backend: mínimo 40% de cobertura inicial.
    -   Data Science: cobertura razonable en funciones clave (sin exigir notebooks).
    -   Frontend: Pruebas básicas de renderizado de componentes principales.
    -   Modelos: al menos una prueba que valide consistencia de entrada / salida.

4.- Criterios para aprobar una tarea:
    Una tarea se considera lista para revisión cuando:
    1.  Todo el código nuevo está acompañado de pruebas unitarias.
    2.  Todas las pruebas existentes pasan correctamente.
    3.  Las Pruebas manuales están correctamente documentadas.
    4.  Se incluye evidencia de comportamiento correcto.
    5.  No existen errores de linting o estilo.
    6.  Se respetó la estructura de carpetas del proyecto.

    Sin estos requisitos el Pull Request no podrá aprobarse.

5.- Ejemplo de flujo mínimo de pruebas antes de hacer un Pull Request:

    Cada colaborador debe ejecutar y validar lo siguiente antes de solicitar revisión:
    
    Backend:
        pytest src/backend/tests/
    
    Frontend:
        npm run test

    Data Science:
    -   Ejecutar notebooks de prueba.
    -   Validar que no existan celdas fallidas.
    -   Guardar resultados y capturas.

    Modelo:
        python src/models/predict.py --example_input samples/x.json

    Cada resultado debe incluirse en el Pull Request o en el Issue asociado.