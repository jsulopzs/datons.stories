# Use an official Python runtime as a parent image
FROM python:{$VARIANT}-slim-buster


# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
   && rm -rf /tmp/pip-tmp

RUN python -m ipykernel install --user

# Install Jupyter Lab
RUN pip install jupyterlab

# Expose the port the app runs on
EXPOSE 8888

# Command to run the application
CMD ["jupyter", "lab", "--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root"]