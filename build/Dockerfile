FROM odoo:16

USER root

RUN apt-get update && apt-get install -y \
        git \
        ipython

COPY requirements.txt /requirements.txt
RUN pip3 install -r /requirements.txt

USER odoo
