FROM amd64/odoo:14
USER root
RUN apt-get update && apt-get install -y \
        git \
        ipython
USER odoo
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
