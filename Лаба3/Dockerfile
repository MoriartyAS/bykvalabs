FROM debian
RUN apt-get update && apt-get -y upgrade && apt-get install -y nginx && apt-get clean && \
    cd ./var/www/ && rm -rf ./* && \
    mkdir -p moriartyas.com/img && \
    chmod -R 754 /var/www/moriartyas.com && \
    useradd Ann && groupadd Lyckova && usermod -aG Lyckova Ann && \
    chown -R Ann:Lyckova /var/www/moriartyas.com && \
    sed -i 's/\/var\/www\/html/\/var\/www\/moriartyas.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/www-data/Ann/g' /etc/nginx/nginx.conf
ADD index.html /var/www/moriartyas.com/
ADD img.jpg /var/www/moriartyas.com/img/
CMD ["nginx", "-g", "daemon off;"]