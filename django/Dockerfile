FROM hub.lnxsystems.com/library/python:centos8-1

RUN mkdir /data && mkdir -p /services/web && pip-3 install django
COPY web /services/web/
COPY entrypoint.sh /entrypoint.sh
COPY requirements.txt /services/web/
RUN pip-3 install -r /services/web/requirements.txt

ENTRYPOINT ["/entrypoint.sh"] 
#ENTRYPOINT ["/bin/bash"]
