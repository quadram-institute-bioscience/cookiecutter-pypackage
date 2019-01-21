{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% for _ in cookiecutter.project_name %}={% endfor %}
{{ cookiecutter.project_name }}
{% for _ in cookiecutter.project_name %}={% endfor %}

{% if is_open_source %}
|Linux| |Windows| |Documentation| |pypi| |Coverage| |Code quality| |Docker build|

{%- endif %}

{% if cookiecutter.add_pyup_badge == 'y' %}
.. image:: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg
     :target: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
     :alt: Updates
{% endif %}


{{ cookiecutter.project_short_description }}

{% if is_open_source %}
* Free software: {{ cookiecutter.open_source_license }}
* Documentation: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io.
{% endif %}

Introduction
------------


Quick start
-----------


Installation
------------


Usage
-----

Outputs
-------

License
-------
{% if is_open_source %}
{{ cookiecutter.project_name }} is free software, licensed under {{ cookiecutter.open_source_license }}
{% endif %}

Feedback/Issues
---------------
Please report any issues to the `issues page`_.

Citation
--------
{{ cookiecutter.project_name }} is not formally publsihed. Please cite https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}

This package was created with Cookiecutter_ and the `QI python template`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`QI python template`: https://github.com/happykhan/qi-python-package
.. _`issues page`: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/issues 

{% if is_open_source %}

.. |pypi| image:: https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg
        :target: https://pypi.python.org/pypi/{{ cookiecutter.project_slug }}

.. |Linux| image:: https://img.shields.io/travis/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.svg
        :target: https://travis-ci.org/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}

.. |Documentation| image:: https://readthedocs.org/projects/{{ cookiecutter.project_slug | replace("_", "-") }}/badge/?version=latest
        :target: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status
        
.. |Windows| image:: https://ci.appveyor.com/api/projects/status/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}?branch=master&svg=true
    :target: https://ci.appveyor.com/project/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/branch/master
    :alt: Windows build status on Appveyor

.. |Dependencies| image:: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg
     :target: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
     :alt: Updates

.. |Coverage| image:: https://img.shields.io/coveralls/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/master.svg
     :target: https://coveralls.io/r/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
     :alt: Coverage
     
.. |Code quality| image:: https://img.shields.io/scrutinizer/g/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.svg
     :target: https://scrutinizer-ci.com/g/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/?branch=master
     :alt: Coverage   
     
.. |Code quality| image:: https://img.shields.io/scrutinizer/g/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.svg
     :target: https://scrutinizer-ci.com/g/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/?branch=master
     :alt: Coverage        
     
.. |Docker build| image:: https://img.shields.io/docker/pulls/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.svg     
     :target: https://hub.docker.com/r/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}
     :alt: Docker build status
     
{%- endif %}
