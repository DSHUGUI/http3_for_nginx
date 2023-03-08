```
chrome.exe --ignore-certificate-errors-spki-list=BSQJ0jkQ7wwhR7KvPZ+DSNk2XTZ/MS6xCbo9qu++VdQ= --enable-experimental-web-platform-features --origin-to-force-quic-on=[::1]:443 HTTPS://[::1]/
```





```
./auto/configure --prefix=/media --with-http_ssl_module --with-http_v3_module --with-cc-opt="-I../boringssl-master/include" --with-ld-opt="-L../boringssl-master/build/ssl -L../boringssl-master/build/crypto"
```
