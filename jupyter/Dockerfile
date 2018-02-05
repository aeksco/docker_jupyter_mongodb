# Extends jupyter/datascience-notebook
FROM jupyter/datascience-notebook

# Copies example Jupyter notebook
COPY MongoDB.ipynb /home/jovyan/MongoDB.ipynb

# Installs pymongo and zipline library, jupyter-c-kernel
RUN pip install pymongo zipline jupyter-c-kernel
# RUN install_c_kernel

