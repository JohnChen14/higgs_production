FROM jupyter/scipy-notebook:python-3.8.8
RUN mkdir /home/jovyan/lhapdf && wget https://lhapdf.hepforge.org/downloads/?f=LHAPDF-6.5.1.tar.gz -O LHAPDF-6.5.1.tar.gz && tar xf LHAPDF-6.5.1.tar.gz && cd LHAPDF-6.5.1 && ./configure --prefix=/home/jovyan/lhapdf && make && make install && wget http://lhapdfsets.web.cern.ch/lhapdfsets/current/CT10nlo.tar.gz -O- | tar xz -C /home/jovyan/lhapdf/share/LHAPDF
COPY start-notebook.sh /usr/local/bin/
