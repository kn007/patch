## Patches

### nginx.patch
* Add SPDY Support.
* Add HTTP2 HPACK Encoding Support.
* Add Dynamic TLS Record support.

Test pass: 1.17.0


### nginx_strict-sni.patch
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


## Other
[我的Nginx编译之旅](https://kn007.net/topics/my-nginx-compilation-tour/) 

[kn007的个人博客](https://kn007.net) 
