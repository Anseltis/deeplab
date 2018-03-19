FROM tensorflow/tensorflow

RUN apt-get update
RUN apt-get install -y python-pil python-numpy
RUN pip install jupyter
RUN pip install matplotlib
RUN apt-get install -y git

WORKDIR /opt
RUN git clone https://github.com/tensorflow/models.git
WORKDIR /opt/models/research

ENV PYTHONPATH $PYTHONPATH:`pwd`:`pwd`/slim
RUN python deeplab/model_test.py

WORKDIR /opt/models/research/deeplab
RUN apt-get install -y wget vim

RUN echo "dash dash/sh boolean false" | debconf-set-selections
RUN DEBIAN_FRONTEND=noninteractive dpkg-reconfigure dash
