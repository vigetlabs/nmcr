FROM nginx:1.17.6

RUN apt-get update && apt-get install -y openssl

RUN mkdir /etc/ssl/self-signed

RUN openssl req \
  -x509 \
  -nodes \
  -days 365 \
  -subj "/C=US/ST=DC/O=NMCR/CN=nmcr.test" \
  -addext "subjectAltName=DNS:nmcr.test" \
  -newkey rsa:2048 \
  -keyout /etc/ssl/self-signed/self-signed.key \
  -out /etc/ssl/self-signed/self-signed.crt;

COPY ./.docker-config/nginx/default.conf /etc/nginx/conf.d/default.conf
