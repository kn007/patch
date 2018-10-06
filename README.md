## Patches

### nginx.patch
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.15.5


### nginx_auto_using_PRIORITIZE_CHACHA.patch
* Using SSL_OP_PRIORITIZE_CHACHA when support (For Nginx with OpenSSL 1.1.1, [#2](https://github.com/kn007/patch/issues/2))

Test pass: 1.15.5

### nginx_strict-sni.patch
* Enable Strict-SNI, Protect your site ip without exposing your certificate (From [here](https://github.com/hakasenyang/openssl-patch/issues/1#issuecomment-421551872))

Test pass: 1.15.5


## Other
[我的Nginx编译之旅](https://kn007.net/topics/my-nginx-compilation-tour/) 

[kn007的个人博客](https://kn007.net) 
