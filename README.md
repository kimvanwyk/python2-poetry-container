# python2-pipenv-container
A Docker container to be used as a base for Python 2 [poetry](https://poetry.eustace.io) based projects.

# Usage

* Use this image as the **FROM** argument in a container.

* Copy all source files to */app/* in the container

* Ensure there is a *pyproject.toml* in the root directory - it will be copied into the directory and all contents **poetry install**ed into the container.

# Example Child Project

## Project Directory

```
- Dockerfile
- pyproject.toml
- app/
     - python_source.py
     - other_python_source.py
```

## Dockerfile

``` docker
FROM python2-poetry-container:latest

COPY app/* /app/

ENTRYPOINT ["python", "main_script.py"]

```
