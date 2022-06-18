# Install Plone 5.2 with pip and mxdev


## Installation

Add your add-ons to `instance.yaml` and `requirements.txt`.

Apply cookiecutter to generate Zope configuration:

```shell
cookiecutter -f --no-input --config-file instance.yaml https://github.com/plone/cookiecutter-zope-instance
```

Install packages with:

```shell
mxdev -c mx.ini
pip install -r requirements-mxdev.txt
```

Run Plone with:

```shell
runwsgi instance/etc/zope.ini
```

Head over to http://localhost:8080/

```{note}
Plone 5.2 needs Python < 3.9
```