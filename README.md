# patches


## nginx.patch
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.15.0


## nginx__1.13.10_http2_hpack.patch
* Add HTTP2 HPACK Encoding Support.

Test pass: 1.15.0


## fix_nginx_hpack_push_error.patch
* Fix http2 push & http2 hpack compatibility issues for nginx ([cloudflare/sslconfig#96](https://github.com/cloudflare/sslconfig/issues/96))

Test pass: 1.15.0


## nginx_auto_using_PRIORITIZE_CHACHA.patch
* Using SSL_OP_PRIORITIZE_CHACHA when support (For Nginx with OpenSSL 1.1.1, [#2](https://github.com/kn007/patch/issues/2))

Test pass: 1.15.0
