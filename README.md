# Banking account transaction management

Django project that implement SOAP API using spyne, lxml and Django. the project store elements on database and use ComplexModel to implement ComplexType.

## Tech stack

- Python 3
- Django
- Spyne (SOAP)
- lxml
- suds (SOAP client)
- psycopg2 (PostgreSQL)
- Database: PostgreSQL

## Project structure

- `baking_acoount_transaction_management/`: project settings and root URLs
- `account_app/`: Django app
- Tests: `account_app/tests.py`

## Data model

| Model | App | Fields |
|---|---|---|
| `Client` | `account_app` | cin, name, familyName, email |
| `Bank` | `account_app` | name, address, creationDate |
| `Account` | `account_app` | rib, balance, client, creation_date, accountType |
| `Transaction` | `account_app` | amount, date, transactionType, account, transfer_to_account |

## URL routes

Declared in `urls.py`:

- `/blog/`
- `/bank/`

## How to run

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

`settings.py` is configured for PostgreSQL: create the database and use your own credentials before running `migrate`.

Then open `http://127.0.0.1:8000/`.

---

Author: [Chaouki Bayoudhi](https://github.com/ChaoukiBayoudhi)
