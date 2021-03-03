FROM google/cloud-sdk:322.0.0-alpine as static-storage

ARG BUCKET_NAME
ARG GOOGLE_APPLICATION_CREDENTIALS

RUN echo $GOOGLE_APPLICATION_CREDENTIALS | base64 -d > credential.json
RUN cat credential.json
RUN gcloud auth activate-service-account --key-file credential.json
