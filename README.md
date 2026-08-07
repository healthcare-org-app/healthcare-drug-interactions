# drug-interactions-service

drug-interactions-service — domain: pharmacy

- **Port:** 8503
- **Language:** Python 3.11 + Flask
- **Database:** `pharmacy` (Postgres, table `drug_interactions`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/drug_interactions/`          |
| POST      | `/api/drug_interactions/`          |
| GET       | `/api/drug_interactions/<id>`      |
| PUT/PATCH | `/api/drug_interactions/<id>`      |
| DELETE    | `/api/drug_interactions/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
