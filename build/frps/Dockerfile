FROM alpine:latest

ENV FRP_VER 0.20.0
ENV FRP_FULL_VER frp_${FRP_VER}_linux_amd64

RUN cd /root \ 
    && wget https://github.com/fatedier/frp/releases/download/v${FRP_VER}/${FRP_FULL_VER}.tar.gz \
    && tar vxzf ${FRP_FULL_VER}.tar.gz \
    && rm ${FRP_FULL_VER}.tar.gz \
    && mv ${FRP_FULL_VER} frps \
    && rm -rf ./frps/frpc* ./frps/frps.ini

WORKDIR /root/frps

CMD [ "./frps", "-c", "./frps.ini" ]