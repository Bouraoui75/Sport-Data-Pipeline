# Sport Data Pipeline

Pipeline de données orienté Data Engineering permettant de centraliser, transformer et analyser des données d’activités sportives.

---

## Stack technique

- Python 3.12
- PostgreSQL
- dbt
- Kestra
- Docker
- Power BI
- Slack Webhooks

---

## Fonctionnalités

- Ingestion de données RH et sportives
- Génération d’activités sportives simulées
- Pipeline ELT automatisé
- Transformations SQL avec dbt
- Orchestration quotidienne avec Kestra
- Calcul des indicateurs métier
- Notifications Slack
- Dashboard Power BI

---

## Architecture du projet

```text
.
├── dbt/
├── flows/
├── scripts/
├── src/
├── docker-compose.yml
├── main.py
├── pyproject.toml
└── .env.example
```

---

## Installation

### 1. Configuration

Créer le fichier `.env` à partir du template :

```bash
cp .env.example .env
```

### 2. Démarrage des services

```bash
docker compose up -d --build
```

Services disponibles :

| Service | Port |
|---|---|
| PostgreSQL | 5433 |
| Kestra | 9000 |
| dbt Docs | 4080 |

---

## Kestra

Kestra est utilisé pour orchestrer le pipeline de données :

- ingestion
- transformations dbt
- notifications
- monitoring
- gestion des exécutions

Interface web :

```text
http://localhost:9000
```

---

## Exécution du pipeline

### Initialisation complète

```bash
python main.py --reset
```

### Exécution standard

```bash
python main.py
```

Le pipeline peut également être déclenché manuellement depuis l’interface Kestra.

---

## Architecture technique

- PostgreSQL : stockage des données
- Python : ingestion et logique métier
- dbt : transformations SQL
- Kestra : orchestration des workflows
- Power BI : visualisation des KPIs

---

## Notes

- Pipeline incrémental et relançable
- Gestion des secrets via `.env`
- Séparation des données analytiques et sensibles
- Compatible environnement local Docker

