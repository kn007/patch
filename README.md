# Patches

## Nginx

### use_openssl_md5_sha1.patch
* Use the OpenSSL library instead of the Nginx original function.
* Repack it because "patch unexpectedly ends in middle of line".
    - Thanks [@CarterLi](https://github.com/kn007/patch/issues/5)

Test pass: 1.29.2

### nginx_dynamic_tls_records.patch
* Add Dynamic TLS Record Support.

Require: Nginx 1.29.2

Test pass: 1.29.2

### Enable_BoringSSL_OCSP.patch
* For BoringSSL support OCSP stapling.
    - Using "ssl_stapling_file" to support.
    - Only "ssl_stapling_file" with single cert is supported.
    - Auto-rebuild OCSP stapling file with shell and atd(at cron), you can read this [article](https://kn007.net/topics/let-nginx-support-ocsp-stapling-when-using-boringssl/)(Maybe you need a translation tool).
    - Thanks [@CarterLi](https://github.com/kn007/patch/issues/4).

Test pass: 1.25.5

### nginx.patch (Discontinued)
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Require: Nginx 1.25.0 (this version only)

Test pass: 1.25.0

Since `Nginx` 1.25.1, HPACK encoding will not support because the HTTP/2 server push support has been removed.

### nginx_with_quic.patch (Discontinued)
* Add HTTP3(QUIC) Support.
    - For OCSP stapling, maybe you need [this](https://github.com/kn007/patch#enable_boringssl_ocsppatch).
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Require: Nginx 1.21.4 or later.

Test pass: 1.23.3 with [cloudflare/quiche@c9311a1](https://github.com/cloudflare/quiche/tree/c9311a18910c0277867c34c0acc4a9711b50b913)

<b>Check your modules when build failed.</b>

### nginx_for_1.23.4.patch (Deprecated)
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Require: Nginx version below 1.25.0

Test pass: 1.23.4

### nginx_with_quic_for_1.19.7_full.patch (Deprecated)
* Add HTTP3(QUIC) Support.
    - For OCSP stapling, maybe you need [this](https://github.com/kn007/patch#enable_boringssl_ocsppatch).
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Require: Nginx 1.19.7 or later(below 1.21.4).

Test pass: 1.21.3 with [cloudflare/quiche@af1bbc0](https://github.com/cloudflare/quiche/tree/af1bbc03e9992bae516d0b692a481de64bd4e8d9)

`nginx_with_quic_for_1.19.6.patch` is required to support Nginx versions lower than 1.19.7, cause `post_accept_timeout` had been removed by Nginx since 1.19.7.

### nginx_with_quic_for_1.19.6.patch (Deprecated)
* Revert `nginx_with_quic.patch` to support Nginx versions lower than 1.19.7.
* Patch `nginx_with_quic.patch` first, then patch this one.

Test pass: 1.19.6 with [nginx_with_quic.patch@ec8cac4](https://github.com/kn007/patch/blob/ec8cac4fc74b1718e9b005e7533201aec552aa40/nginx_with_quic.patch) & [cloudflare/quiche@fca5e9a](https://github.com/cloudflare/quiche/tree/fca5e9acdfdff9e80c7b9346214c64b393108328)

### nginx_with_spdy.patch (Deprecated)
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Test pass: 1.17.9

### nginx_with_spdy_quic.patch (Deprecated)
* Add SPDY Support.
* Add HTTP3(QUIC) Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record Support.

Test pass: 1.17.9 with [cloudflare/quiche@9a8b3b](https://github.com/cloudflare/quiche/tree/9a8b3b12d007715cd4cc254362db51d5a01de9f2)

## Other

### openssl-1.1.1.patch
* Add TLS 1.3 Support.
* Add BoringSSL's Equal Preference Support.
* Add ChaCha20-Poly1305 Draft Version Support.

Test pass: 1.1.1w

### ffmpeg-let-rtmp-flv-support-hevc-h265-opus.patch
* FLV/RTMP Extensions For FFmpeg.
    - Add FLV Encode/Decode with H.265/HEVC & OPUS Codec Support.
    - Add RTMP Stream Push with H.265/HEVC & OPUS Codec Support.
    - Thanks [@xia-chu](https://github.com/xia-chu/ZLMediaKit/wiki/RTMP%E5%AF%B9H265%E5%92%8COPUS%E7%9A%84%E6%94%AF%E6%8C%81).

Test pass: 4.3.1

### dropbox_fs_fix.patch
* For Dropbox Linux users. This patch could let official python script auto-load `libdropbox_fs_fix.so` library before start dropboxd.
    - Using [Dropbox filesystem fix for Linux Repo](https://github.com/dark/dropbox-filesystem-fix) and make `libdropbox_fs_fix.so`.
    - After compiled, copy `libdropbox_fs_fix.so` to `$HOME/.dropbox-dist/libdropbox_fs_fix.so`.
    - Download Dropbox official python script, put it with patch file together.
    - Patch, enjoy.

Test pass: 2019.02.14 version

## Links
[聊聊Nginx 1.25和HTTP/3](https://kn007.net/topics/talk-about-nginx-1-25-and-http-3/)

[Nginx 1.19.4新特性推荐](https://kn007.net/topics/nginx-1-19-4-new-feature-recommendation/)

[让Nginx使用BoringSSL时支持OCSP Stapling](https://kn007.net/topics/let-nginx-support-ocsp-stapling-when-using-boringssl/)

[博客终止使用TLS 1.0和TLS 1.1协议](https://kn007.net/topics/deprecating-tls-1-0-and-tls-1-1-protocols/)

[小试HTTP3](https://kn007.net/topics/try-http3/)

[我的Nginx编译之旅](https://kn007.net/topics/my-nginx-compilation-tour/)

[解决Dropbox Linux客户端因文件系统导致无法同步问题](https://kn007.net/topics/fix-dropbox-filesystem-sync-problem-for-linux-client/)

[kn007的个人博客](https://kn007.net) 
