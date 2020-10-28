FROM ubuntu:18.04


RUN apt-get update -y && apt-get upgrade -y

RUN apt-get install python3 python3-dev python3-pip python3-setuptools -y
RUN apt-get install git vim wget sudo -y

RUN mkdir /base
WORKDIR /base

RUN pip3 install --upgrade pip

RUN DEBIAN_FRONTEND=noninteractive apt-get install libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev \
    libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python3-tk \
    libharfbuzz-dev libfribidi-dev libxcb1-dev -y

RUN git clone https://github.com/python-pillow/Pillow.git
WORKDIR /base/Pillow/depends
RUN bash install_raqm.sh
WORKDIR /base

RUN pip install -U https://github.com/python-pillow/Pillow/archive/master.zip
RUN pip install jupyter pandas tqdm pyarrow


CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root",  "--port=8888", "--no-browser", "--notebook-dir=./working"]
