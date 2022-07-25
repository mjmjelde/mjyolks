FROM nginxproxy/nginx-proxy

RUN apt-get update
RUN apt-get install -y libnginx-mod-http-geoip2 gpg
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DE1997DCDE742AFA
RUN echo 'deb http://ppa.launchpad.net/maxmind/ppa/ubuntu jammy main' | tee -a /etc/apt/sources.list.d/maxmind.list
RUN apt-get update && apt-get install -y geoipupdate libmaxminddb0 libmaxminddb-dev mmdb-bin
RUN apt-get clean all

RUN sed '1 i\load_module /modules/ngx_http_geoip2_module.so;\n' /etc/nginx/nginx.conf

RUN geoipupdate