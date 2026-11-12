# Sidewise

Plataforma de análisis municipal en España para comparar ubicaciones empresariales mediante indicadores de riesgo y atractivo, clustering e IA generativa con fuentes verificables.

## Estado

Estructura inicial del proyecto. Todavía no hay una aplicación funcional, datasets cargados, modelos entrenados ni agente implementado. El nombre del repositorio es **sidewise**; la documentación de partida usaba SiteWise.

## Alcance inicial

Una actividad de principio a fin: seleccionar actividad, consultar municipios, comparar dos o tres opciones, mostrar perfiles similares y explicar resultados con fuentes. Riesgo y atractivo se calculan por separado. Si falta un dato imprescindible, el resultado es no evaluable. La valoración municipal no garantiza la aptitud de una parcela.

## Estructura

```text
sidewise/
├── apps/                 # Aplicaciones ejecutables
│   ├── frontend/         # Mapa, fichas, comparador y asistente
│   └── api/              # API REST y contratos
├── src/sidewise/         # Paquete Python reutilizable
│   ├── data/             # Ingesta, limpieza y cruces municipales
│   ├── scoring/          # Pesos, mínimos y puntuaciones
│   ├── ml/               # Entrenamiento, evaluación y perfiles
│   ├── rag/              # Documentos, índice y recuperación
│   ├── agent/            # Flujo y herramientas del agente
│   ├── db/               # Modelos, conexiones y cargas
│   └── common/           # Configuración y contratos compartidos
├── configs/              # Indicadores, actividades y parámetros
├── data/                 # Archivos de datos
│   ├── sample/           # Muestra pequeña publicable
│   ├── raw/              # Fuentes originales, fuera de Git
│   ├── interim/          # Intermedios, fuera de Git
│   └── processed/        # Dataset final y matriz, fuera de Git
├── notebooks/            # Exploración y experimentos
├── scripts/              # Construcción, entrenamiento y arranque
├── tests/                # Pruebas por área
│   ├── data/             # Calidad de datos
│   ├── scoring/          # Cálculos y mínimos
│   ├── api/              # Endpoints
│   ├── agent/            # Herramientas y fuentes
│   └── integration/      # Recorrido entre módulos
├── docs/                 # Documentación
│   ├── architecture/     # Diseño y contratos
│   ├── data/             # Diccionario, fuentes y calidad
│   ├── methodology/      # Pesos, clustering y model card
│   ├── governance/       # Licencias, sesgos y límites
│   └── planning/         # Reparto, hitos y acuerdos
├── .github/workflows/    # Comprobaciones automáticas
├── .env.example          # Variables sin secretos
├── .gitignore            # Exclusiones
├── pyproject.toml        # Metadatos y dependencias Python
└── docker-compose.yml    # Base de datos local
```

La API expone la lógica de scoring; el agente consulta sus resultados. Los notebooks no sustituyen al pipeline reproducible. Cada carpeta incluye un README para conservarla en Git y explicar su finalidad.

## Preparación local

Requiere Python 3.11 o posterior. Desde la raíz:

```bash
python -m venv .venv
# Linux/macOS:
source .venv/bin/activate
# Windows PowerShell: .venv\\Scripts\\Activate.ps1
python -m pip install -e .
```

El paquete no declara todavía dependencias de aplicación. Añadirlas por módulo al implementar y acordar versiones reproducibles.

Para la base de datos se necesita Docker Compose. Copiar .env.example a .env, completar POSTGRES_PASSWORD y ejecutar:

```bash
docker compose up -d db
```

Este comando solo inicia PostgreSQL/PostGIS local; no inicia API ni frontend. El puerto queda restringido a localhost. No publicar .env ni credenciales.

## Equipo y entregas

Consultar [plan de equipo](docs/planning/plan_equipo.md) y [contrato del dataset](docs/data/contrato_dataset.md). Responsables Persona 1–5 pendientes de asignar. Dataset v0.1: 17 de noviembre de 2026. Cierre de la primera versión: 4 de diciembre de 2026.

## Colaboración

Trabajar en ramas por tarea y abrir pull requests con una explicación de los cambios y su validación. La persona de apoyo revisa el módulo. Mantener main utilizable e integrar pronto. No subir datos pesados ni documentos sin revisar su licencia.

## Licencia

Pendiente de decisión del equipo. La visibilidad pública no equivale a conceder una licencia de reutilización. Las fuentes de datos conservan sus propias condiciones.
