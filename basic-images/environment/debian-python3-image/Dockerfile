FROM samhunt/debian-basic-image:latest

WORKDIR /usr/local/python
RUN apt install -y gcc make zlib1g-dev && \
curl -fsSL -o Python-3.8.13.tgz "https://www.python.org/ftp/python/3.8.13/Python-3.8.13.tgz" && \
tar -xf ./Python-3.8.13.tgz && cd ./Python-3.8.13 && \
./configure --prefix=/usr/local/Python --with-openssl=/usr/local/openssl && \
make && make install && \
ln -s /usr/local/python/Python-3.8.13/python /usr/bin/python && \
echo "PATH=/usr/local/python/Python-3.8.13/bin:$PATH" >> /etc/profile && \
python -m pip install pyinstaller -i https://pypi.tuna.tsinghua.edu.cn/simple -U

WORKDIR /home/python