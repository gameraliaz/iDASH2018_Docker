FROM ntl

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y \
    m4 \
    libssl-dev

COPY gmp-6.1.2.tar.xz /gmp-6.1.2.tar.xz

RUN tar -xvf /gmp-6.1.2.tar.xz -C / \
    && cd /gmp-6.1.2 \
    && ./configure \
    && make \
    && make install

RUN rm -rf /gmp-6.1.2.tar.xz

CMD ["/bin/bash"]