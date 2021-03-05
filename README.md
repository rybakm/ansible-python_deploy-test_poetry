# python_deploy - test_poetry

Simple Python webserwer for testing DebOps role [ansible-python_deploy](https://github.com/scibi/ansible-python_deploy).
Server should be installed using poetry and run as a gunicorn app.

### Installing poetry

```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```

More information can be found in official [docs](https://python-poetry.org/docs/#installation).

### Running application

Commands should be executed from repo directory.

```bash
poetry install --no-dev
poetry run gunicorn -c gunicorn.conf.py wsgi:app
```

`GET http://localhost:8000` should respond with `HTTP 200 "OK"`.
