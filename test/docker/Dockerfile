
# FROM nginx:1.18.0 AS build
# WORKDIR /src
# RUN apt-get update && apt-get install -y git wget build-essential libssl-dev libpcre3-dev zlib1g-dev
# RUN CONFARGS=$(nginx -V 2>&1 | sed -n -e 's/^.*arguments: //p') \
#     git clone https://github.com/google/ngx_brotli.git && \
#     cd ngx_brotli && git submodule update --init && cd .. && \
#     wget -nv http://nginx.org/download/nginx-1.18.0.tar.gz -O - | tar -xz && \
#     cd nginx-1.18.0 && \ 
#     ./configure --with-compat $CONFARGS --add-dynamic-module=../ngx_brotli

FROM nginx:1.18.0 AS final
# COPY --from=build /src/nginx-1.18.0/objs/ngx_http_brotli_filter_module.so /usr/lib/nginx/modules/
# COPY --from=build /src/nginx-1.18.0/objs/ngx_http_brotli_static_module.so /usr/lib/nginx/modules/
COPY docker/rootfs /
WORKDIR /usr/share/nginx/html
COPY pkg .
COPY web .
