Analyzing 290a74f42cdf
Docker Version: 18.09.3
GraphDriver: overlay2
Environment Variables
|PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
|MINIO_UPDATE=off
|MINIO_ACCESS_KEY_FILE=access_key
|MINIO_SECRET_KEY_FILE=secret_key
|MINIO_SSE_MASTER_KEY_FILE=sse_master_key

Open Ports
|9000

Image user
|User is root

Potential secrets:
|Found match etc/apk/keys/alpine-devel@lists.alpinelinux.org-4a6a0840.rsa.pub Possible public key \.pub$ b7e513f1782880dddf7b47963f82673b3dbd5c2eeb337d0c96e1ab6d9f3b76bd/layer.tar
|Found match etc/apk/keys/alpine-devel@lists.alpinelinux.org-5243ef4b.rsa.pub Possible public key \.pub$ b7e513f1782880dddf7b47963f82673b3dbd5c2eeb337d0c96e1ab6d9f3b76bd/layer.tar
|Found match etc/apk/keys/alpine-devel@lists.alpinelinux.org-5261cecb.rsa.pub Possible public key \.pub$ b7e513f1782880dddf7b47963f82673b3dbd5c2eeb337d0c96e1ab6d9f3b76bd/layer.tar
|Found match etc/udhcpd.conf DHCP server configs dhcpd[^ ]*.conf b7e513f1782880dddf7b47963f82673b3dbd5c2eeb337d0c96e1ab6d9f3b76bd/layer.tar
Dockerfile:
CMD ["/bin/sh"]
LABEL maintainer=MinIO Inc <dev@min.io>
COPY file:e9913b058365efcf74888730b8d2528d2f8019f1eababf86675d12aaa640c0a5 in /usr/bin/healthcheck
	usr/
	usr/bin/
	usr/bin/healthcheck

COPY file:c0b44056325632e0858dee9b070d9c5a73b7917a883004a88b14316fde62e6e7 in /usr/bin/
	usr/
	usr/bin/
	usr/bin/docker-entrypoint.sh

ENV MINIO_UPDATE=off
ENV MINIO_ACCESS_KEY_FILE=access_key MINIO_SECRET_KEY_FILE=secret_key MINIO_SSE_MASTER_KEY_FILE=sse_master_key
RUN apk add --no-cache ca-certificates 'curl>7.61.0' 'su-exec>=0.2'  \
	&& echo 'hosts: files mdns4_minimal [NOTFOUND=return] dns mdns4' >> /etc/nsswitch.conf  \
	&& curl https://dl.min.io/server/minio/release/linux-amd64/minio > /usr/bin/minio  \
	&& chmod +x /usr/bin/minio  \
	&& chmod +x /usr/bin/docker-entrypoint.sh  \
	&& chmod +x /usr/bin/healthcheck
EXPOSE 9000
ENTRYPOINT ["/usr/bin/docker-entrypoint.sh"]
VOLUME [/data]
HEALTHCHECK &{["CMD-SHELL" "healthcheck"] "1m0s" "0s" "0s" '\x00'}
CMD ["minio"]
COPY file:5a2a8571a5f8157951bb25d7307c0dd2a09de09215d357703ada70bb5e100f11 in /third_party/license.txt

COPY dir:8482345a95bd16052f482de6fe97b0712093ee161d89a68b3461b20c28d06bc8 in /third_party
