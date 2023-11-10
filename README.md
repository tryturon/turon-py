<p align="center">
  <p align="center">
    <a href="https://www.turon.io" target="_blank">
      <img src="docs/source/_static/logo.png" alt="Turon" width="250" height="84">
    </a>
  </p>
</p>


[Turon](https://www.turon.io) is a platform that allows developers and data teams to build highly performant APIs on top of their data warehouses.

This is the API documentation for Turon's official Python SDK.

Install
-------

Install our Python SDK using [pip](https://pip.pypa.io/en/stable/):

```shell
pip install --upgrade turon
```

Usage
-----

```python
 from turon import Turon
 from turon.exceptions import APIException

 turon = Turon('TURON_APP_KEY', 'TURON_API_KEY')
 query = turon.get('GetUserById', user_id='582091167')

 try:
    user = query.to_dict()
 except APIException as excinfo:
    if excinfo.code == 404:
       print('User could not be found.')
```

Documentation
-------------

More detailed API documentation can be found [here](https://tryturon.github.io/turon-py/).

