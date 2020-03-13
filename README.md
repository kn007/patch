## Patches

### nginx.patch
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.17.9

### nginx_with_quic.patch
* Add HTTP3(QUIC) Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.17.9 with [cloudflare/quiche 2f2dfab](https://github.com/cloudflare/quiche/tree/2f2dfab7b156ddc95485025e8c0f7cdb6f655a0d)

### nginx_with_spdy.patch (Deprecated)
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.17.9

### nginx_with_spdy_quic.patch (Deprecated)
* Add SPDY Support.
* Add HTTP3(QUIC) Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.17.9 with [cloudflare/quiche 9a8b3b](https://github.com/cloudflare/quiche/tree/9a8b3b12d007715cd4cc254362db51d5a01de9f2)

### nginx_strict-sni.patch (Deprecated)
* Enable Strict-SNI, Protect your site ip without exposing your certificate (From [here](https://github.com/hakasenyang/openssl-patch/issues/1#issuecomment-421551872))
    - Strict SNI requires at least two ssl server (fake) settings (server { listen 443 ssl }).
    - It does not matter what kind of certificate or duplicate.

Test pass: 1.15.5

### dropbox_fs_fix.patch
* For Dropbox Linux users. This patch could let official python script auto-load `libdropbox_fs_fix.so` library before start dropboxd.
    - Using [Dropbox filesystem fix for Linux Repo](https://github.com/dark/dropbox-filesystem-fix) and make `libdropbox_fs_fix.so`.
    - After compiled, copy `libdropbox_fs_fix.so` to `$HOME/.dropbox-dist/libdropbox_fs_fix.so`.
    - Download Dropbox official python script, put it with patch file together.
    - Patch, enjoy.

Test pass: 2019.02.14 version

### use_openssl_md5_sha1.patch
* Use the OpenSSL library instead of the original function.
* Repack it because "patch unexpectedly ends in middle of line".
    - Thanks [@CarterLi](https://github.com/kn007/patch/issues/5)

Test pass: 1.17.9

## Other
[小试HTTP3](https://kn007.net/topics/try-http3/) 

[我的Nginx编译之旅](https://kn007.net/topics/my-nginx-compilation-tour/) 

[解决Dropbox Linux客户端因文件系统导致无法同步问题](https://kn007.net/topics/fix-dropbox-filesystem-sync-problem-for-linux-client/) 

[kn007的个人博客](https://kn007.net) 
