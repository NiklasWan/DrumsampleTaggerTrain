FROM tensorflow/tensorflow:2.5.0-gpu-jupyter

RUN apt-get update

RUN apt-get install python3-pip libsndfile-dev -y

COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp

RUN useradd -ms /bin/bash dockerdev

USER dockerdev
WORKDIR /usr/local/bin/dockerdev

RUN pip3 install pylint 