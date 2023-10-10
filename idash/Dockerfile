FROM gmp

RUN apt-get update && apt-get upgrade -y

COPY HEAAN /home/aliaz/Desktop/Libraries/HEAAN

WORKDIR /home/aliaz/Desktop/Libraries/HEAAN/HEAAN/lib

RUN make all

WORKDIR /home/aliaz/Desktop/Libraries/HEAAN/HEAAN/run

RUN make all

COPY iDash /iDash

WORKDIR /iDash/run

RUN make clean

RUN make all

CMD ./IDASH2018 ../data/covariates.csv ../data/snpMat.txt 17 1500 50 20 30 40 3 4 4 7 0