## `joomla:fpm`

```console
$ docker pull joomla@sha256:58690ee418f8231873de1de8f2e870ee8389d6c81b8b9322ee5114934be73d93
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `joomla:fpm` - linux; amd64

```console
$ docker pull joomla@sha256:13b9e42492b0db64e7535e0318652929abd959280082ab876766617f15f5c27e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168546907 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c07bf8ef022a514c7ef163b954a8b6a8b73618f193d9e1a47b0f16b267f184de`
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
# Thu, 04 Jan 2018 04:17:39 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Thu, 04 Jan 2018 04:17:39 GMT
ENV PHP_VERSION=5.6.32
# Thu, 04 Jan 2018 04:17:39 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.32.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.32.tar.xz.asc/from/this/mirror
# Thu, 04 Jan 2018 04:17:40 GMT
ENV PHP_SHA256=8c2b4f721c7475fb9eabda2495209e91ea933082e6f34299d11cba88cd76e64b PHP_MD5=
# Thu, 04 Jan 2018 04:17:57 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 04 Jan 2018 04:17:57 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 04 Jan 2018 04:21:34 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 04 Jan 2018 04:23:26 GMT
COPY multi:f9544e5c6b9d1d1292fca43464fe1e77b631547ac2baa8503de318853c0536d0 in /usr/local/bin/ 
# Thu, 04 Jan 2018 04:23:26 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 04 Jan 2018 04:24:54 GMT
WORKDIR /var/www/html
# Thu, 04 Jan 2018 04:24:54 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Thu, 04 Jan 2018 04:24:55 GMT
EXPOSE 9000/tcp
# Thu, 04 Jan 2018 04:25:03 GMT
CMD ["php-fpm"]
# Thu, 04 Jan 2018 07:36:46 GMT
MAINTAINER Michael Babker <michael.babker@joomla.org> (@mbabker)
# Thu, 04 Jan 2018 07:36:47 GMT
ENV JOOMLA_INSTALLATION_DISABLE_LOCALHOST_CHECK=1
# Thu, 04 Jan 2018 07:37:17 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libmcrypt-dev zip unzip && rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd
# Thu, 04 Jan 2018 07:37:52 GMT
RUN docker-php-ext-install mysqli
# Thu, 04 Jan 2018 07:38:01 GMT
RUN docker-php-ext-install mcrypt
# Thu, 04 Jan 2018 07:38:23 GMT
RUN docker-php-ext-install zip
# Thu, 04 Jan 2018 07:38:24 GMT
VOLUME [/var/www/html]
# Thu, 04 Jan 2018 07:38:24 GMT
ENV JOOMLA_VERSION=3.8.2
# Thu, 04 Jan 2018 07:38:24 GMT
ENV JOOMLA_SHA1=e68745d55cc5b1a7bb46f72f4296c6550e088543
# Thu, 04 Jan 2018 07:38:34 GMT
RUN curl -o joomla.zip -SL https://github.com/joomla/joomla-cms/releases/download/${JOOMLA_VERSION}/Joomla_${JOOMLA_VERSION}-Stable-Full_Package.zip 	&& echo "$JOOMLA_SHA1 *joomla.zip" | sha1sum -c - 	&& mkdir /usr/src/joomla 	&& unzip joomla.zip -d /usr/src/joomla 	&& rm joomla.zip 	&& chown -R www-data:www-data /usr/src/joomla
# Thu, 04 Jan 2018 07:38:35 GMT
COPY file:c1e8bebe69e832de6ba85a02864e7d24ff9e6b5232ea62a31e27a5769c662116 in /entrypoint.sh 
# Thu, 04 Jan 2018 07:38:35 GMT
COPY file:7328ebe063e26f7b7716dfd8778bb7d46b90702ea38b23b9147ba2fd837ac2c1 in /makedb.php 
# Thu, 04 Jan 2018 07:38:35 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 04 Jan 2018 07:38:36 GMT
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
	-	`sha256:768019bfa727647dd25967891816d2a2230598ce5e8ec6a43ebae9cbad901c03`  
		Last Modified: Thu, 04 Jan 2018 05:14:04 GMT  
		Size: 12.8 MB (12798744 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1765452576975f8244563af4c932161782ad0f0aa923e1562749c3be63960a0c`  
		Last Modified: Thu, 04 Jan 2018 05:14:00 GMT  
		Size: 501.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85554aba6d66228cd5eb30675c22ff8b6236483fff9e9cd6d6c12d7672020314`  
		Last Modified: Thu, 04 Jan 2018 05:14:04 GMT  
		Size: 10.3 MB (10334778 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d40ba977efd9cf19830f7e735696ff204c2643b64ccbf5b8fefd5b084887125f`  
		Last Modified: Thu, 04 Jan 2018 05:14:00 GMT  
		Size: 2.2 KB (2182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1a7f433be4da4ad991a0310cf9652a58f9646a50b13e028655ef6163f81b841`  
		Last Modified: Thu, 04 Jan 2018 05:14:00 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae13c2bca4cee95f089ebf4653c445181c728204feb3a6f18981abd317fc9b25`  
		Last Modified: Thu, 04 Jan 2018 05:14:00 GMT  
		Size: 7.6 KB (7622 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1345288f77ec28eab357ec2609fa3bd72dc90a271a866746433849112b705ce`  
		Last Modified: Thu, 04 Jan 2018 07:52:44 GMT  
		Size: 3.0 MB (2980951 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b91e2083508f25cedf7e69959f321dc5fba49fc5c28e8d75da6a3828fbd3120`  
		Last Modified: Thu, 04 Jan 2018 07:52:43 GMT  
		Size: 58.0 KB (58002 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ffa5904d0f54e0ace3a1f25cab5eafb5588100c49e0d09c4b95427e88e281f4c`  
		Last Modified: Thu, 04 Jan 2018 07:52:41 GMT  
		Size: 19.7 KB (19716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d4f5b835997ff6bd13a31e36c1b542550ceed99987d0ab7d38181dcec1094ce`  
		Last Modified: Thu, 04 Jan 2018 07:52:41 GMT  
		Size: 63.4 KB (63423 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c8f55c7a1391bec7623997674133f9a02b73cc586820ecdbe3cfe29ab9b0f66`  
		Last Modified: Thu, 04 Jan 2018 07:52:47 GMT  
		Size: 9.4 MB (9433106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90e29b352615889247e6aa14f49892340e1ab05015363fdca97ca4ac69c2af30`  
		Last Modified: Thu, 04 Jan 2018 07:52:41 GMT  
		Size: 1.2 KB (1190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3ce17afb8e00b8d5c70a22cc57879c446e4825412fadf89f86e7c0f27964d22`  
		Last Modified: Thu, 04 Jan 2018 07:52:41 GMT  
		Size: 615.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
