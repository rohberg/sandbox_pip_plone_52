# Install Plone 5.2 with pip and mxdev

pip and [mxdev](https://pypi.org/project/mxdev/) allows to install Plone in a comfortable way. No buildout anymore.

## Installation

Add your add-ons to `instance.yaml` and `requirements.txt`.

Create a Python virtual environment in the current directory. Plone 5.2 needs Python < 3.9

```shell
python3.8 -m venv venv
source venv/bin/activate
```

Update Python package management tools.

```shell
pip install -U pip wheel
```

Install cookiecutter:

```shell
pip install cookiecutter
```

Apply cookiecutter to generate Zope configuration:

```shell
cookiecutter -f --no-input --config-file instance.yaml https://github.com/plone/cookiecutter-zope-instance
```

See your Plone instance in /instance.

Install packages with:

```shell
pip install mxdev
mxdev -c mx.ini
pip install -r requirements-mxdev.txt
```

Run Plone with:

```shell
runwsgi instance/etc/zope.ini
```

Head over to http://localhost:8080/
