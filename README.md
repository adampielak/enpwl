# ENPWL (Easy to use Nginx proxy with Let's Encrypt)

Easy to use Nginx proxy with Let's Encrypt.

Features:

- redirect http to https
- automatic cert renew
- generate 2048-bit dhparam certificate in first run (it may take longer)
- easy to use

Note: you can't use custom nginx conf. If you need it please use other image.

Environmental variables:

ENPWL_DOMAIN -> your domain without www
ENPWL_DOMAIN_WWW -> boolean, if you would like cert with www please set to true (default value is false)
ENPWL_CLIENT_MAX_BODY_SIZE -> Maximim size of body. Useful when setting the file upload size (default value is 1M).
ENPWL_APP_PORT -> yout application port.

docker run \
    -p 80:80 \
    -p 443:443 \
    --env ENPWL_DOMAIN=example.com \
    --env ENPWL_DOMAIN_WWW=true \
    --env ENPWL_CLIENT_MAX_BODY_SIZE=20M \
    --env ENPWL_APP_PORT=8080 \
    dacrhu/enpwl:latest


