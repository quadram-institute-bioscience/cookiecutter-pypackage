FROM debian:testing
MAINTAINER {{ cookiecutter.email }}

RUN apt-get update -qq && apt-get install -y git python3 python3-setuptools python3-biopython python3-pip
RUN pip3 install cython

RUN pip3 install git+git://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.git

WORKDIR /data
