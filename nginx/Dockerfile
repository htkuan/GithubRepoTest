FROM google/cloud-sdk:322.0.0-alpine as static-storage

ARG BUCKET_NAME
ARG GOOGLE_APPLICATION_CREDENTIALS

RUN echo $GOOGLE_APPLICATION_CREDENTIALS > credential.json && \
    gcloud auth activate-service-account --key-file credential.json && \
    gsutil cp -r gs://$BUCKET_NAME .

FROM nginx:1.19.6-alpine

ARG BUCKET_NAME
COPY ./templates /etc/nginx/templates
COPY --from=static-storage /$BUCKET_NAME /usr/share/nginx/html