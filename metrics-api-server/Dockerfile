FROM registry.access.redhat.com/ubi9/python-311@sha256:b5bf20d19a14764626cfc3a695abe1c1af4a38a6d05b7662e23692c7906b5ec0

WORKDIR /app

# Copy the Flask app to the container
COPY app /app

RUN pip install --upgrade pip && \
    pip install --no-cache-dir flask gunicorn

# Expose the port Gunicorn will listen on
EXPOSE 5000

# run the app using Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
