# Nginx-EE

![nginx-ee](https://raw.githubusercontent.com/VirtuBox/nginx-ee/master/nginx-ee.png)

[![Build Status](https://travis-ci.com/VirtuBox/nginx-ee.svg?branch=master)](https://travis-ci.com/VirtuBox/nginx-ee) [![](https://img.shields.io/github/license/VirtuBox/nginx-ee.svg)](https://github.com/VirtuBox/nginx-ee/blob/master/LICENSE) [![](https://img.shields.io/github/stars/VirtuBox/nginx-ee.svg)](https://github.com/VirtuBox/nginx-ee) [![release](https://img.shields.io/github/release/virtubox/nginx-ee.svg?style=flat)](https://github.com/VirtuBox/nginx-ee/releases) ![](https://img.shields.io/github/last-commit/virtubox/nginx-ee/master.svg?style=flat)

Automated Nginx compilation with additional modules for WordOps, EasyEngine v3, Plesk Onyx or from scratch

---

## Features

* Compile the latest Nginx release : stable or mainline
* Install Nginx or replace Nginx package previously installed
* Nginx built-in modules selection
* Nginx Third-party module selection
* Dynamic modules support
* Brotli Support
* TLS v1.3 support (Final)
* Cloudflare HPACK (for Mainline release only)
* Setup a daily cronjob to automated nginx updates

---

## Additional Third-party modules

Nginx current mainline release : **v1.15.8**
Nginx current stable release : **v1.14.2**

* [ngx_cache_purge](https://github.com/FRiCKLE/ngx_cache_purge)
* [headers-more-nginx-module](https://github.com/openresty/headers-more-nginx-module)
* [ngx_brotli](https://github.com/eustas/ngx_brotli)
* [srcache-nginx-module](https://github.com/openresty/srcache-nginx-module)
* [ngx_http_substitutions_filter_module](https://github.com/yaoweibin/ngx_http_substitutions_filter_module)
* [nginx_dynamic_tls_records](https://github.com/nginx-modules/ngx_http_tls_dyn_size)
* [OpenSSL](https://github.com/openssl/openssl)
* [ipscrub](http://www.ipscrub.org/)
* [ngx_http_auth_pam_module](https://github.com/sto/ngx_http_auth_pam_module)
* [virtual-host-traffic-status](https://github.com/vozlt/nginx-module-vts)

Optional modules :

* [ngx_pagespeed](https://github.com/apache/incubator-pagespeed-ngx) (latest-beta or latest-stable)
* [naxsi WAF](https://github.com/nbs-system/naxsi)
* [nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module)

---

## Compatibility

### Operating System

#### Recommended

* Ubuntu 18.04 LTS (Bionic)
* Ubuntu 16.04 LTS (Xenial)

#### Also compatible

* Debian 9 (Stretch)
* Raspbian (Stretch)

### Plesk releases

* 17.5.x
* 17.8.x
* 17.9.x

---

## Usage

<!-- TOC -->
- [Default non-interactive install](#default-non-interactive-install)
- [Interactive install](#interactive-install)
- [Custom installation](#custom-installation)
- [Nginx modules](#nginx-modules)
- [Nginx configurations](#nginx-configurations)
- [Roadmap](#roadmap)

<!-- /TOC -->

### Default non-interactive install

By default, nginx-ee compile Nginx Mainline release without Pagespeed, Naxsi or RTMP

```bash
bash <(wget -O - virtubox.net/nginx-ee || curl -sL virtubox.net/nginx-ee)
```

### Interactive install

Interactive installation is available with arguments `-i` or `--interactive`

```bash
bash <(wget -O - virtubox.net/nginx-ee || curl -sL virtubox.net/nginx-ee) --interactive
```

### Custom installation

Exemple : Nginx stable release with pagespeed and naxsi

```bash
bash <(wget -O - virtubox.net/nginx-ee || curl -sL virtubox.net/nginx-ee) --stable --pagespeed --naxsi
```

#### Options available

Nginx build options :

* `--stable` : compile Nginx stable release
* `--full` : Naxsi + PageSpeed + RTMP
* `--dynamic` : Compile Nginx modules as dynamic modules

Optional third-party modules :

* `--pagespeed`: compile nginx with ngx_pagespeed latest-stable
* `--pagespeed-beta`: compile nginx with ngx_pagespeed latest-beta
* `--naxsi` : compile nginx with naxsi
* `--rtmp` : compile nginx with rtmp module

Extras :

* `--cron` : setup daily cronjob to update nginx each time a new release is available

### Nginx modules

You can choose Nginx built-in and third-party modules you want to compile with Nginx-ee. You can find more informations in the [Wiki](https://github.com/VirtuBox/nginx-ee/wiki/Nginx-modules)

---

## Related repositories & pages

* [Nginx-ee Wiki](https://github.com/VirtuBox/nginx-ee/wiki)
* [Ubuntu-nginx-web-server](https://github.com/VirtuBox/ubuntu-nginx-web-server) : repository with all custom nginx configurations used by VirtuBox
* [Wo-nginx-setup](https://github.com/VirtuBox/wo-nginx-setup) : automated wordops setup script
* [Plesk-nginx-fastcgi-cache-template](https://github.com/VirtuBox/plesk-nginx-fascgi-cache-template) : Plesk Onyx custom hosting templates with fastcgi_cache support
* [Nginx-cloudflare-real-ip](https://github.com/VirtuBox/nginx-cloudflare-real-ip) : Bash script to restore visitor real IP under Cloudflare with Nginx

---

## Roadmap

* [x] Add choice between stable & mainline release
* [x] Add Nginx configuration examples
* [x] Add Cloudflare HPACK patch
* [x] Add support for servers without EasyEngine
* [x] Add non-interactive installation
* [x] Add automated update detection
* [x] Add support for Plesk servers
* [x] Add Nginx modules choice
* [x] Add support for Debian 9
* [x] Add support for Raspbian

## Credits

* [centminmod](https://github.com/centminmod/centminmod) : Nginx, Nginx modules & various other patches
* [hakase](https://github.com/hakasenyang/openssl-patch) : OpenSSL-patch

Published & maintained by <a href="https://virtubox.net" title="VirtuBox">VirtuBox</a>
