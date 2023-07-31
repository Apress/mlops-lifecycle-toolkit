FROM jupyter/scipy-notebook:latest

USER root

# Update the package lists and install any packages required
RUN apt-get update && \
    apt-get install -y 

RUN pip install \
    numpy \
    pandas \
    tensorflow \
    torch \
    jupyterlab==3.2.0 \
    mlflow 

# Switch back to the jovyan user
USER $NB_UID

# Expose the Jupyter Lab port
EXPOSE 8888

# Set the default command to launch Jupyter Lab
CMD ["start.sh", "jupyter", "lab", "--LabApp.token=''", "--ip=0.0.0.0", "--port=8888", "--no-browser"]
