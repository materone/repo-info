## `wordpress:cli-php7.0`

```console
$ docker pull wordpress@sha256:9debe29ac8f8e5094e2ea0257432344abfc879bf1983cf4551e8264c7c4a669c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `wordpress:cli-php7.0` - linux; amd64

```console
$ docker pull wordpress@sha256:6577c9a0d9c7b6157987d02478315786bad49786bc003f1551b93f97bf274683
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **35.8 MB (35806166 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:eddf61a30c1b8e8643c9c43b1b9d89325cf6ce2d5a98d3db736335ad4bfc1807`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["wp","shell"]`

```dockerfile
# Fri, 01 Dec 2017 18:49:44 GMT
ADD file:c05a199f603e2a97ea93d9f6cc210a1c8ab27eda35f3613722bfcf697da36483 in / 
# Fri, 01 Dec 2017 18:49:45 GMT
CMD ["/bin/sh"]
# Fri, 01 Dec 2017 19:13:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Dec 2017 19:13:26 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		openssl
# Fri, 01 Dec 2017 19:13:27 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Dec 2017 19:13:27 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Dec 2017 19:13:28 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Dec 2017 19:13:28 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 19:13:28 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 19:13:28 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Dec 2017 19:38:16 GMT
ENV GPG_KEYS=1A4E8B7277C42E53DBA9C7B9BCAA30EA9C0D5763 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Fri, 01 Dec 2017 19:38:17 GMT
ENV PHP_VERSION=7.0.26
# Fri, 01 Dec 2017 19:38:17 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.0.26.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.0.26.tar.xz.asc/from/this/mirror
# Fri, 01 Dec 2017 19:38:17 GMT
ENV PHP_SHA256=ed5cbb4bbb0ddef8985f100bba2e94002ad22a230b5da2dccfe148915df5f199 PHP_MD5=
# Fri, 01 Dec 2017 22:43:34 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 01 Dec 2017 22:43:37 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Fri, 01 Dec 2017 22:47:26 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		openssl-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Thu, 04 Jan 2018 03:53:47 GMT
COPY multi:0de99b27377ea60c319e566076843370f751e856c1e3a64b2dcd283a35066564 in /usr/local/bin/ 
# Thu, 04 Jan 2018 03:53:47 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 04 Jan 2018 03:53:47 GMT
CMD ["php" "-a"]
# Thu, 04 Jan 2018 07:39:42 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		libjpeg-turbo-dev 		libpng-dev 	; 		docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr; 	docker-php-ext-install gd mysqli opcache; 		runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)"; 	apk add --virtual .wordpress-phpexts-rundeps $runDeps; 	apk del .build-deps
# Thu, 04 Jan 2018 07:39:43 GMT
RUN { 		echo 'opcache.memory_consumption=128'; 		echo 'opcache.interned_strings_buffer=8'; 		echo 'opcache.max_accelerated_files=4000'; 		echo 'opcache.revalidate_freq=2'; 		echo 'opcache.fast_shutdown=1'; 		echo 'opcache.enable_cli=1'; 	} > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Thu, 04 Jan 2018 07:39:46 GMT
RUN apk add --no-cache 		less 		mysql-client
# Thu, 04 Jan 2018 07:39:47 GMT
RUN set -ex; 	mkdir -p /var/www/html; 	chown -R www-data:www-data /var/www/html
# Thu, 04 Jan 2018 07:39:47 GMT
WORKDIR /var/www/html
# Thu, 04 Jan 2018 07:39:47 GMT
VOLUME [/var/www/html]
# Thu, 04 Jan 2018 07:39:47 GMT
ENV WORDPRESS_CLI_GPG_KEY=3B9191625F3B1F1BF5DD3B47673A02042F6B6B7F
# Thu, 04 Jan 2018 07:39:48 GMT
ENV WORDPRESS_CLI_VERSION=1.4.1
# Thu, 04 Jan 2018 07:39:48 GMT
ENV WORDPRESS_CLI_SHA512=f861b5499e0b555a791ab6d76a0f3b1f033ae22aaee63dcdfaf8a0bd44886876690d40c6c95366d60f32d55f6282273e55f8ecdfa8787aec7b435cffe45790e7
# Thu, 04 Jan 2018 07:49:18 GMT
RUN set -ex; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		curl -o /usr/local/bin/wp.gpg -fSL "https://github.com/wp-cli/wp-cli/releases/download/v${WORDPRESS_CLI_VERSION}/wp-cli-${WORDPRESS_CLI_VERSION}.phar.gpg"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$WORDPRESS_CLI_GPG_KEY"; 	gpg --batch --decrypt --output /usr/local/bin/wp /usr/local/bin/wp.gpg; 	rm -rf "$GNUPGHOME" /usr/local/bin/wp.gpg; 		echo "$WORDPRESS_CLI_SHA512 */usr/local/bin/wp" | sha512sum -c -; 	chmod +x /usr/local/bin/wp; 		apk del .fetch-deps; 		wp --allow-root --version
# Thu, 04 Jan 2018 07:49:18 GMT
COPY file:6439ebdee069987b41eac0b67f3829c60f8dc168426dc92872b5e95a5f4d8213 in /usr/local/bin/ 
# Thu, 04 Jan 2018 07:49:19 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 04 Jan 2018 07:49:19 GMT
USER [www-data]
# Thu, 04 Jan 2018 07:49:19 GMT
CMD ["wp" "shell"]
```

-	Layers:
	-	`sha256:ab7e51e37a183df284512426b1cb56d0404532b6011c823f35127c796fb97b13`  
		Last Modified: Fri, 01 Dec 2017 18:58:11 GMT  
		Size: 2.4 MB (2387532 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62f3776db6e11947a5caa37560f77eb1e6e6bd66c4e7cfd7c0f42cdaaac9ef97`  
		Last Modified: Fri, 01 Dec 2017 20:15:06 GMT  
		Size: 1.3 MB (1309099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e4aa03132010eaef600e00cc6d1634547f5d90b60af0ffda897ce78f7c73184`  
		Last Modified: Fri, 01 Dec 2017 20:15:05 GMT  
		Size: 1.3 KB (1273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cb6bf51627dff594ce752437fdc6ecddfef0c70fa4410cf2dd9563426626bb`  
		Last Modified: Fri, 01 Dec 2017 20:15:03 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2bb758cf5fce93b125a053cec94680f4382cb6acfa53bf97bef73dafc07c6a9`  
		Last Modified: Fri, 01 Dec 2017 22:51:03 GMT  
		Size: 12.0 MB (11985545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36071aa6645f74977a74919f1e77925a64ce50896e7781a4a7c0775143e7b8f8`  
		Last Modified: Fri, 01 Dec 2017 22:51:02 GMT  
		Size: 496.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de560b9cee43125c4f82b6bc022eb15bf23848e46135999ee0f8388a3f1a2e19`  
		Last Modified: Fri, 01 Dec 2017 22:51:07 GMT  
		Size: 10.6 MB (10572953 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a898a1c78a47f375e457aee86fa6dfd64fbd313c644d8740c779937b6bbadf1`  
		Last Modified: Thu, 04 Jan 2018 05:08:01 GMT  
		Size: 2.2 KB (2168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1072da8238c0c590780aab18cf84d2b2c380c4ea627c1faa22b7ea3d9517a3a3`  
		Last Modified: Thu, 04 Jan 2018 08:39:26 GMT  
		Size: 744.8 KB (744816 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be1f9495dca5ea9143a2b67f5764a3b2b13035ebd757f55840f70dca8e0c6cf7`  
		Last Modified: Thu, 04 Jan 2018 08:39:24 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcf8df97c04467601bbbb32a32e9ca2bcaeaf529196cd5487e1628789896edd`  
		Last Modified: Thu, 04 Jan 2018 08:39:26 GMT  
		Size: 7.8 MB (7759922 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:043fd9faeb04a9411e326cf21351ae49d87f4b6806db19594613e1e8f9c589ca`  
		Last Modified: Thu, 04 Jan 2018 08:39:23 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d377ebc17e831f2fc36cb97b8c5bc5758facb5e453d3ffda6d1d94549231ceb5`  
		Last Modified: Thu, 04 Jan 2018 08:39:23 GMT  
		Size: 1.0 MB (1041301 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:356234290a4bb894985a2642e9be3cfe2644d9fe14213ff755ac4c67fd514916`  
		Last Modified: Thu, 04 Jan 2018 08:39:23 GMT  
		Size: 418.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
