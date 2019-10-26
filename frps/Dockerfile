FROM alpine:latest

ENV FRP_VER 0.29.0
ENV FRP_FULL_VER frp_${FRP_VER}_linux_amd64

ENV TZ=Asia/Shanghai

RUN apk add --no-cache tzdata \
    && cd / \ 
    && wget https://github.com/fatedier/frp/releases/download/v${FRP_VER}/${FRP_FULL_VER}.tar.gz \
    && tar xvzf ${FRP_FULL_VER}.tar.gz \
    && mv ${FRP_FULL_VER}/frps frps \
    && rm -rf ${FRP_FULL_VER}*

WORKDIR /

CMD [ "/frps", "-c", "/etc/frps/frps.ini" ]