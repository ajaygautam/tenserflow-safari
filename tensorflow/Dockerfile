FROM continuumio/miniconda:4.0.5

COPY environment.yml /
RUN /bin/bash -c "conda env create -f environment.yml"
RUN rm environment.yml
RUN apt-get update && apt-get install -y fontconfig
RUN mkdir .jupyter
COPY jupyter_notebook_config.py /.jupyter/
COPY course /tensorflow

EXPOSE 8888
CMD /bin/sh -c "LANG=POSIX SHELL=bash /opt/conda/envs/oreillytf/bin/jupyter notebook /tensorflow"
