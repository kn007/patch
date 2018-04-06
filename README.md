# patches


## nginx.patch
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.13.11


## nginx__1.13.10_http2_hpack.patch
* Add HTTP2 HPACK Encoding Support.

Test pass: 1.13.11


## nginx_auto_using_PRIORITIZE_CHACHA.patch
* Using SSL_OP_PRIORITIZE_CHACHA when support (For Nginx with OpenSSL 1.1.1, [#2](https://github.com/kn007/patch/issues/2))

Test pass: 1.13.11
