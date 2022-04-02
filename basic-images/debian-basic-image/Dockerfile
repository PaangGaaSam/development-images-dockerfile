FROM debian:stable

RUN apt update && apt upgrade -y && apt install -y curl perl gcc make && apt remove -y openssl && \
mkdir -p /usr/local/openssl/ && \
curl -L "https://www.openssl.org/source/openssl-1.1.1n.tar.gz" -o /usr/local/openssl/openssl-1.1.1n.tar.gz && \
tar -xf /usr/local/openssl/openssl-1.1.1n.tar.gz -C /usr/local/openssl/ && \
/usr/local/openssl/openssl-1.1.1n/config --prefix=/usr/local/openssl no-zlib && \
make && make install && \
ln -s /usr/local/openssl/include/openssl /usr/include/openssl && \
ln -s /usr/local/openssl/lib/libssl.so.1.1 /usr/local/lib/libssl.so && \
ln -s /usr/local/openssl/bin/openssl /usr/bin/openssl && \
echo "/usr/local/openssl/lib" >> /etc/ld.so.conf && \
ldconfig -v