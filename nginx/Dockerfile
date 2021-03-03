FROM google/cloud-sdk:322.0.0-alpine as static-storage

ARG BUCKET_NAME
ARG GOOGLE_APPLICATION_CREDENTIALS

RUN echo $GOOGLE_APPLICATION_CREDENTIALS > credential.json && \
    gcloud auth activate-service-account --key-file credential.json
