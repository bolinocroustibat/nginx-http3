# nginx-quictls

Similar to [nginx-quictls](https://github.com/ononoki1/nginx-quictls), except that it uses more modules like ngx_http_access_module (added with the http_gzip_static_module flag, see https://stackoverflow.com/questions/46236349/do-i-have-to-turn-on-ngx-http-access-module).

List of added modules:

--with-http_ssl_module  \
--with-http_stub_status_module \
--with-http_realip_module \
--with-http_auth_request_module \
--with-http_v2_module \
--with-http_dav_module \
--with-http_slice_module \
--with-threads \
--with-http_addition_module \
--with-http_flv_module \
--with-http_gunzip_module \
--with-http_gzip_static_module \
--with-http_mp4_module \
--with-http_random_index_module \
--with-http_secure_link_module \
--with-http_sub_module \
--with-mail_ssl_module \
--with-stream_ssl_module \
--with-stream_ssl_preread_module \
--with-stream_realip_module \

## Compare with nginx-http3

- Some OpenSSL-only directives are supported, e.g. `ssl_conf_command`
- OCSP stapling can be enabled directly by using `ssl_stapling on; ssl_stapling_verify on;`

## Usage

First, install NGINX from [nginx-http3](https://github.com/ononoki1/nginx-http3), [Debian's official package](https://packages.debian.org/bullseye/nginx) or [NGINX's official package](https://nginx.org/en/linux_packages.html#Debian). Then run following commands.

```bash
sudo systemctl stop nginx
sudo wget https://github.com/ononoki1/nginx-quictls/releases/latest/download/nginx -O /usr/sbin/nginx
sudo chmod +x /usr/sbin/nginx
sudo systemctl start nginx
```
