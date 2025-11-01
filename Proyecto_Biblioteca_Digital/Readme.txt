Proyecto: Biblioteca Digital de un Equipo de Investigación

I_Objetivo
Este repositorio organiza datos brutos, análisis, informes, referencias y presentaciones de un equipo de investigación para facilitar la navegación, trazabilidad y reutilización.

II_Estructura de directorios (raíz: Proyecto_Biblioteca_Digital)
- 00_config/
- 01_datos/
  - 00_brutos/
    - 00_muestras/
    - 01_exp/
- 02_etl/
- 03_bd/
  - 00_muestras/
- 04_analisis/
  - 00_consultas/
  - 01_graficos/
  - 02_resultados/
- 05_presentaciones/
  - 00_congresos/
- 06_documentacion/
  - 00_diagramas/
  - 01_notas/
  - 02_registros/
- 07_referencias/
  - 00_articulos/
- 09_licencias/
- 10_herramientas/

III_Lógica de la estructura
- Prefijos numéricos (00_, 01_, …): aseguran un orden estable y semántico en el explorador, reflejando el flujo de trabajo de izquierda a derecha (configuración → datos → etl → bd → análisis → difusión → soporte), evitando reordenamientos alfabéticos.
- 00_config/: primero para garantizar reproducibilidad; centraliza parámetros (.ini) que condicionan todo el pipeline.
- 01_datos/: fuentes originales inmutables.
  - 00_brutos/: insumos sin transformar.
    - 00_muestras/: archivos por muestra (granularidad fina).
    - 01_exp/: conjuntos por experimento (granularidad agregada).
- 02_etl/: extracción, transformación y carga que operan sobre 01_datos.
- 03_bd/: almacenamiento persistente/operacional al que carga 02_etl y del que consume 04_analisis.
- 04_analisis/: artefactos derivados organizados por su secuencia típica de trabajo.
  - 00_consultas/: SQL u otros queries reproducibles para extracción/preparación.
  - 01_graficos/: salidas visuales a partir de resultados o consultas.
  - 02_resultados/: tablas/cuadros finales y hojas de cálculo consolidadas.
- 05_presentaciones/
  - 00_congresos/: materiales de difusión por evento (versionados v1, v2…).
- 06_documentacion/: contexto del proyecto.
  - 00_diagramas/: flujos/arquitectura.
  - 01_notas/: notas operativas (con prefijo temporal AAAAMM).
  - 02_registros/: bitácoras/actas de experimento (AAAAMM).
- 07_referencias/
  - 00_articulos/: bibliografía y material externo usado como sustento.
- 09_licencias/: licencias de herramientas/datos (cumplimiento y auditoría).
- 10_herramientas/: ejecutables externos utilizados por el equipo.

IV_Políticas de orden y nomenclatura
- Orden de carpetas en la raíz (fijo y numerado): 00_config, 01_datos, 02_etl, 03_bd, 04_analisis, 05_presentaciones, 06_documentacion, 07_referencias, 09_licencias, 10_herramientas.
- Subcarpetas numeradas: en cada nivel, prefijos 00_, 01_, 02_… para mantener el orden lógico de trabajo.
- Nombres de carpetas: snake_case, minúsculas, sin tildes/ñ, evitar espacios y abreviaturas ambiguas.
- Nombres de archivos: snake_case, minúsculas, ASCII; separador único "_"; longitud sugerida ≤ 80 caracteres, evitar espacios y abreviaturas ambiguas.
- Prefijo temporal: AAAAMM al inicio solo para artefactos derivados (04_analisis, 05_presentaciones, 06_documentacion). No aplicar a 01_datos salvo cortes/snapshots mensuales.
- Evitar redundancias por contexto: no repetir en el nombre lo que ya indica la carpeta (p.ej., no "grafico_" dentro de 01_graficos, ni "etl_" dentro de 02_etl).
- Identificadores: cero a la izquierda para series (exp_001, muestra_001).
- Versionado: sufijos _vN en resultados/presentaciones cuando aplique; no versionar datos brutos.
- Nombres descriptivos y sin redundancias con la extensión (p.ej., muestras.db en lugar de bd_muestras.db).

V_Eliminaciones
No se eliminaron archivos de datos. Solo se eliminó carpeta "adjuntos" por no considerarla necesaria.

VI_Ubicación y renombres aplicados
- datos_exp_001.csv → 01_datos/00_brutos/01_exp/exp_001.csv
- muestra_001_datosbrutos.txt → 01_datos/00_brutos/00_muestras/muestra_001.txt
- resultados_analisis_A.xlsx → 04_analisis/02_resultados/202510_analisis_a.xlsx
- resul_analisisb.xlsx → 04_analisis/02_resultados/202510_analisis_b.xlsx
- grafico.png → 04_analisis/01_graficos/202510_resultados.png
- consulta_exp001.sql → 04_analisis/00_consultas/exp_001.sql
- presentacion_congresov1.pptx → 05_presentaciones/00_congresos/202511_congreso_xxx_v1.pptx
- presentacion_congreso_v2.pptx → 05_presentaciones/00_congresos/202511_congreso_xxx_v2.pptx
- script_procesamiento.py → 02_etl/procesamiento_v1.py
- config_analizador.ini → 00_config/config_analizador.ini
- articulo_referencia_metodologia.pdf → 07_referencias/00_articulos/referencia_metodologia.pdf
- registro_experimento.txt → 06_documentacion/02_registros/202510_registro_experimento_xxx.txt
- notas_de_reunion.docx → 06_documentacion/01_notas/202510_notas_de_reunion_XXXXX.docx
- licenciaanalizador.txt → 09_licencias/licencia_analizador.txt
- bd_muestras.db → 03_bd/00_muestras/00_muestras.db
- adjuntos/diagrama_flujo.png → 06_documentacion/00_diagramas/202510_diagrama_flujo.png (se elimina carpeta adjuntos)
- analizador_datos.exe → 10_herramientas/analizador_datos.exe




