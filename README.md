# nginx with HTTP/3, with QuicTLS and ngx_http_access_module

Similar to [nginx-quictls](https://github.com/ononoki1/nginx-quictls) (which is itself similar to [nginx-http3](https://github.com/ononoki1/nginx-http3), except that it only provides a single binary `nginx` instead of Debian package), except that it uses more modules e.g. `ngx_http_access_module` (added with the `--with-http_gzip_static_module` build flag, see https://stackoverflow.com/questions/46236349/do-i-have-to-turn-on-ngx-http-access-module).

List of added build flags when compared to [nginx-quictls](https://github.com/ononoki1/nginx-quictls):

```
--with-http_stub_status_module \
--with-http_realip_module \
--with-http_auth_request_module \
--with-http_dav_module \
--with-http_slice_module \
--with-threads \
--with-http_addition_module \
--with-http_flv_module \
--with-http_gunzip_module \
--with-http_gzip_static_module \
--with-http_mp4_module \
--with-stream_ssl_module \
--with-stream_ssl_preread_module \
--with-stream_realip_module \
```

List of removed build flags when compared to [nginx-quictls](https://github.com/ononoki1/nginx-quictls):

```
--without-select_module --without-poll_module \
--without-http_access_module --without-http_autoindex_module \
--without-http_browser_module --without-http_charset_module \
--without-http_empty_gif_module --without-http_limit_conn_module \
--without-http_memcached_module --without-http_mirror_module \
--without-http_referer_module --without-http_split_clients_module \
--without-http_scgi_module --without-http_ssi_module \
--without-http_upstream_hash_module --without-http_upstream_ip_hash_module \
--without-http_upstream_keepalive_module --without-http_upstream_least_conn_module \
--without-http_upstream_random_module --without-http_upstream_zone_module \
```

## Distribution switch notice

According to [Debian Wiki](https://wiki.debian.org/DebianReleases), Debian bullseye will reach its end-of-life date in July 2024. Therefore, the project will switch to Debian bookworm as the packaging environment in June 2024.

**Update:** already switched on June 25th.

## Usage

First, install NGINX from [nginx-http3](https://github.com/ononoki1/nginx-http3), [Debian's official package](https://packages.debian.org/bookworm/nginx) or [NGINX's official package](https://nginx.org/en/linux_packages.html#Debian). Then run following commands.

```bash
sudo systemctl stop nginx
sudo wget https://github.com/bolinocroustibat/nginx-http3/releases/latest/download/nginx -O /usr/sbin/nginx
sudo chmod +x /usr/sbin/nginx
sudo systemctl start nginx
```
