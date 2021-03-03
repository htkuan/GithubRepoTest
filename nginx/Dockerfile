FROM google/cloud-sdk:322.0.0-alpine as static-storage

ARG BUCKET_NAME
ENV GOOGLE_APPLICATION_CREDENTIALS=/secrets/mysecret

# https://docs.docker.com/develop/develop-images/build_enhancements/
RUN --mount=type=secret,id=gcp_key,dst=${GOOGLE_APPLICATION_CREDENTIALS}
RUN gcloud auth activate-service-account
# RUN gcloud auth activate-service-account && \
#     gsutil cp -r gs://$BUCKET_NAME .

# FROM nginx:1.19.6-alpine

# ARG BUCKET_NAME
# COPY ./templates /etc/nginx/templates
# COPY --from=static-storage /$BUCKET_NAME /usr/share/nginx/html