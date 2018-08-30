# patches


## nginx.patch
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.15.3


## nginx_auto_using_PRIORITIZE_CHACHA.patch
* Using SSL_OP_PRIORITIZE_CHACHA when support (For Nginx with OpenSSL 1.1.1, [#2](https://github.com/kn007/patch/issues/2))

Test pass: 1.15.3
