```
chrome.exe --ignore-certificate-errors-spki-list=BSQJ0jkQ7wwhR7KvPZ+DSNk2XTZ/MS6xCbo9qu++VdQ= --enable-experimental-web-platform-features --origin-to-force-quic-on=[::1]:443 HTTPS://[::1]/
```





```

./auto/configure --with-http_v2_module --prefix=/media --with-http_ssl_module --with-http_v3_module --with-cc-opt="-I../boringssl-master/include" --with-ld-opt="-L../boringssl-master/build/ssl -L../boringssl-master/build/crypto"


```



```
git clone --depth=1 https://github.com/google/boringssl.git boringssl-master
cd boringssl-master/
mkdir build
cd build
cmake ../
make
```









```
cd nginx-quic/
./auto/configure --prefix=/root/nginx --with-http_ssl_module --with-http_v2_module --with-http_v3_module --with-cc-opt="-I../boringssl-master/include" --with-ld-opt="-L../boringssl-master/build/ssl -L../boringssl-master/build/crypto"
make 
make install
```














```
server {
    listen 443 ssl http2;              # TCP listener for HTTP/2
    listen 443 http3 reuseport;  # UDP listener for QUIC+HTTP/3

    ssl_protocols       TLSv1.3; # QUIC requires TLS 1.3
    ssl_certificate     ssl/www.example.com.crt;
    ssl_certificate_key ssl/www.example.com.key;

    add_header Alt-Svc 'quic=":443"; h3-27=":443";h3-25=":443"; h3-T050=":443"; h3-Q050=":443";h3-Q049=":443";h3-Q048=":443"; h3-Q046=":443"; h3-Q043=":443"'; # Advertise that QUIC is available
}
```



#### https://hg.nginx.org/nginx-quic/archive/quic.zip



```
server_tokens off;
```



```
user root;
```
