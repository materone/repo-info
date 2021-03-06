## `joomla:3-fpm-php7`

```console
$ docker pull joomla@sha256:e3671c8a3d8d096f8052577ab41ae208cadc0e9372237d9a36bdce7ef63ce64c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `joomla:3-fpm-php7` - linux; amd64

```console
$ docker pull joomla@sha256:a478a867d7d7189d76eff51a438e67df48b9b699d9f1378a4affa916c84627be
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **172.2 MB (172240193 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:025d7586267de29e746d095be38201ece1164697e74677621ef82e2c17da0f24`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:12 GMT
ADD file:1dd78a123212328bdc72ef7888024ea27fe141a72e24e0ea7c3c92b63b73d8d1 in / 
# Tue, 12 Dec 2017 01:41:12 GMT
CMD ["bash"]
# Tue, 19 Dec 2017 20:02:28 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 19 Dec 2017 20:02:29 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 02:17:45 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 02:17:45 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 02:17:46 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 02:40:56 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Thu, 04 Jan 2018 02:40:57 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 02:40:57 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 02:40:57 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 04 Jan 2018 03:32:56 GMT
ENV GPG_KEYS=1A4E8B7277C42E53DBA9C7B9BCAA30EA9C0D5763 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Thu, 04 Jan 2018 03:32:57 GMT
ENV PHP_VERSION=7.0.26
# Thu, 04 Jan 2018 03:32:57 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.0.26.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.0.26.tar.xz.asc/from/this/mirror
# Thu, 04 Jan 2018 03:32:57 GMT
ENV PHP_SHA256=ed5cbb4bbb0ddef8985f100bba2e94002ad22a230b5da2dccfe148915df5f199 PHP_MD5=
# Thu, 04 Jan 2018 03:33:15 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 04 Jan 2018 03:33:20 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 04 Jan 2018 03:37:19 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 04 Jan 2018 03:43:28 GMT
COPY multi:f9544e5c6b9d1d1292fca43464fe1e77b631547ac2baa8503de318853c0536d0 in /usr/local/bin/ 
# Thu, 04 Jan 2018 03:43:29 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 04 Jan 2018 03:43:29 GMT
WORKDIR /var/www/html
# Thu, 04 Jan 2018 03:43:30 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Thu, 04 Jan 2018 03:43:30 GMT
EXPOSE 9000/tcp
# Thu, 04 Jan 2018 03:43:30 GMT
CMD ["php-fpm"]
# Thu, 04 Jan 2018 07:38:54 GMT
MAINTAINER Michael Babker <michael.babker@joomla.org> (@mbabker)
# Thu, 04 Jan 2018 07:39:03 GMT
ENV JOOMLA_INSTALLATION_DISABLE_LOCALHOST_CHECK=1
# Thu, 04 Jan 2018 07:39:33 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libmcrypt-dev zip unzip && rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd
# Thu, 04 Jan 2018 07:39:43 GMT
RUN docker-php-ext-install mysqli
# Thu, 04 Jan 2018 07:39:49 GMT
RUN docker-php-ext-install mcrypt
# Thu, 04 Jan 2018 07:40:08 GMT
RUN docker-php-ext-install zip
# Thu, 04 Jan 2018 07:49:05 GMT
VOLUME [/var/www/html]
# Thu, 04 Jan 2018 07:49:05 GMT
ENV JOOMLA_VERSION=3.8.2
# Thu, 04 Jan 2018 07:49:06 GMT
ENV JOOMLA_SHA1=e68745d55cc5b1a7bb46f72f4296c6550e088543
# Thu, 04 Jan 2018 07:49:12 GMT
RUN curl -o joomla.zip -SL https://github.com/joomla/joomla-cms/releases/download/${JOOMLA_VERSION}/Joomla_${JOOMLA_VERSION}-Stable-Full_Package.zip 	&& echo "$JOOMLA_SHA1 *joomla.zip" | sha1sum -c - 	&& mkdir /usr/src/joomla 	&& unzip joomla.zip -d /usr/src/joomla 	&& rm joomla.zip 	&& chown -R www-data:www-data /usr/src/joomla
# Thu, 04 Jan 2018 07:49:12 GMT
COPY file:c1e8bebe69e832de6ba85a02864e7d24ff9e6b5232ea62a31e27a5769c662116 in /entrypoint.sh 
# Thu, 04 Jan 2018 07:49:12 GMT
COPY file:7328ebe063e26f7b7716dfd8778bb7d46b90702ea38b23b9147ba2fd837ac2c1 in /makedb.php 
# Thu, 04 Jan 2018 07:49:13 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 04 Jan 2018 07:49:13 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:f49cf87b52c10aa83b4f4405800527a74400fb19ea1821d209293bc4d53966aa`  
		Last Modified: Tue, 12 Dec 2017 01:47:59 GMT  
		Size: 52.6 MB (52599697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:185616061386b6fbf50284203b0bfdefaca12fc92bbb65d2f65c3d51dd942ad9`  
		Last Modified: Tue, 19 Dec 2017 21:56:59 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fc132db2e0d4529b0f1ecce1b0208d1415551c378edbbf72912b2da05b161b1`  
		Last Modified: Thu, 04 Jan 2018 04:57:51 GMT  
		Size: 80.2 MB (80245843 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00c1c323341aeccc9c187d1704349390ffbf8437718af11841e34591ff13d47f`  
		Last Modified: Thu, 04 Jan 2018 04:57:30 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba06e712ed55bbf0451a8178c93fe2739eda1d6e1a9869c42528a58df627189f`  
		Last Modified: Thu, 04 Jan 2018 05:06:32 GMT  
		Size: 12.3 MB (12301230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c1df2154ca6e1b5871932bf2280d592c91cfc9683ee74dff94cd2e09255a832`  
		Last Modified: Thu, 04 Jan 2018 05:06:29 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab9d725db0ad2717656bf905e0af88d83aaf879b7a92f2e914e83049c553b972`  
		Last Modified: Thu, 04 Jan 2018 05:06:33 GMT  
		Size: 14.5 MB (14524052 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01ee010f4bc688e6a219cab048d823e33a2eba8da1e6503021c49f4fcdd85f73`  
		Last Modified: Thu, 04 Jan 2018 05:06:29 GMT  
		Size: 2.2 KB (2179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ef1a3bbe6ea4920d8d5131e3b10392ab4f55ae1905be45e35b3f1286a35bc65`  
		Last Modified: Thu, 04 Jan 2018 05:06:29 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a36f03a4c5a464f06927d3bd10f0087f23b7c96639901c3e27a8e85c5f4214f8`  
		Last Modified: Thu, 04 Jan 2018 05:06:29 GMT  
		Size: 7.7 KB (7682 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09c7cd2ef1287684a4567e014febc5fc9061c90622d3c8722708c1fc5bb561e8`  
		Last Modified: Thu, 04 Jan 2018 07:53:54 GMT  
		Size: 3.0 MB (2976095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c30bef285cc9ca5490c62c8c0f6a53a597fccb5c8dd5cf0309e3bc7764e31dce`  
		Last Modified: Thu, 04 Jan 2018 07:53:54 GMT  
		Size: 56.4 KB (56412 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74bbda4608f6d445512c34255c2a8f0b87a615a8391f50f4efacb5adc00035c5`  
		Last Modified: Thu, 04 Jan 2018 07:53:51 GMT  
		Size: 18.3 KB (18286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9444cdf2ca9a5c026cab3f14f2ea7650dd0986c2af3b87815b02d4b81a74656`  
		Last Modified: Thu, 04 Jan 2018 07:53:52 GMT  
		Size: 72.8 KB (72773 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78ace1c91b30c2b7c936bdbb1532bdf95fa715cfc37b548e8f01b1bd129616f5`  
		Last Modified: Thu, 04 Jan 2018 07:53:58 GMT  
		Size: 9.4 MB (9433099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61486c2d52f1c500e6b38c65fed46d9d0ac9eedddc31a6adda505d5912ace6be`  
		Last Modified: Thu, 04 Jan 2018 07:53:52 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a48ac3529d93ebae32441ff8b069370f09113708f8d8fe9dc9681328b6e3318`  
		Last Modified: Thu, 04 Jan 2018 07:53:51 GMT  
		Size: 614.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
