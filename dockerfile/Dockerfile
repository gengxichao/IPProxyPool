FROM python

COPY sources.list /etc/apt/
COPY IPProxyPool-master.zip /root/
COPY webpy-py3.zip /root/


RUN apt-get update && apt-get install -y zip && \
    cd root && \
    unzip IPProxyPool-master.zip && \
    pip3 install lxml requests chardet sqlalchemy gevent greenlet -i http://pypi.douban.com/simple --trusted-host pypi.douban.com && \
    unzip webpy-py3.zip && \
    cd webpy-py3 && python3 setup.py install && \
    cd /root && \
    rm IPProxyPool-master.zip && rm -rf web*


CMD ["python3", "/root/IPProxyPool-master/IPProxy.py"]

EXPOSE 8000