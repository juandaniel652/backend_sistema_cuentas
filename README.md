# Treasury Management System API

Backend application developed with FastAPI for managing income, deposits, remittances, interests, maintenance fees, and chronological records.

The system is designed using a modular monolithic architecture to keep the codebase simple, maintainable, and scalable.

---

## Main features

### Income management

The system allows the registration of the following income categories:

- World Work (OM)
- Congregation Donations (C)

Each record contains:

- Date
- World Work amount
- Congregation amount

Example:

```json
{
  "date": "2026-08-01",
  "world_work": 2000,
  "congregation": 4000
}
```

---

### Deposit management

The system automatically calculates:

```text
Deposit = World Work + Congregation
```

Each deposit record contains:

- Amount
- Deposit date

Example:

```json
{
  "amount": 6000,
  "deposit_date": "2026-08-07"
}
```

---

### Main account management

The system stores:

- Deposits
- Bank interests
- Maintenance fees
- Remittances

---

### Remittance calculation

The remittance is calculated as follows:

```text
Remittance = World Work + Resolution
```

The resolution value is configurable by the backend administrator.

---

### Timeline endpoint

The system exposes a chronological endpoint containing all registered operations.

Example:

```text
2026-08-01 -> Income registered
2026-08-04 -> Income registered
2026-08-07 -> Deposit registered
2026-08-10 -> Bank interest registered
2026-08-15 -> Remittance registered
```

---

## Technology stack

- Python
- FastAPI
- PostgreSQL
- SQLAlchemy
- Alembic
- Pydantic
- Uvicorn
- Pytest
- Docker
- Render
- Supabase

---

## Architecture

This project follows a modular monolithic architecture.

Main modules:

- Income
- Deposit
- Main account
- Remittance
- Timeline

---

## Local development

Clone the repository:

```bash
git clone <repository-url>
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the environment:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
uvicorn app.main:app --reload
```

---

## Future improvements

- Authentication and authorization.
- Audit logging.
- Report generation.
- Dashboard integration.
- Event-driven architecture.
- Container deployment.

Aclaration: This project was developed in linux mint 22
