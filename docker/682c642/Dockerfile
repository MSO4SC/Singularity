# Singularity & Singularity-Python 2.4 

FROM conda/miniconda3
MAINTAINER Victor Sande <https://github.com/victorsndvg>

RUN apt-get update \
    && apt-get install -y \
        curl git make uuid-dev libssl-dev libarchive-dev autoconf automake libtool  \
        tar gzip bash python e2fsprogs squashfs-tools \
    && cd /tmp \
    && git clone https://github.com/dctrud/singularity.git \
    && cd /tmp/singularity \
    && git checkout 682c642  \
    && ./autogen.sh \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd /tmp \
    && rm -rf /tmp/singularity \
    && apt-get remove --purge -y curl git make autoconf automake libtool 
 
RUN apt-get update \
    && apt-get install -y git \
    && cd /tmp \
    && VERSION=2.4.1 \
    && conda install -y numpy scikit-learn cython pandas \
    && git clone -b v$VERSION https://www.github.com/vsoch/singularity-python \
    && cd /tmp/singularity-python \
    && pip install setuptools \
    && pip install -r requirements.txt \
    && pip install pyasn1==0.4.1 \
    && python setup.py sdist \
    && python setup.py install \
    && cd /tmp \
    && rm -rf /tmp/singularity-python \
    && apt-get autoremove -y \
    && apt-get remove --purge -y git
