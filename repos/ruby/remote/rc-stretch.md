## `ruby:rc-stretch`

```console
$ docker pull ruby@sha256:771f042f0756cc6e698cc56fce7b0de551ec05122c9157bbd89b86f964b50d3c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `ruby:rc-stretch` - linux; amd64

```console
$ docker pull ruby@sha256:ca8feb07d55c3785ac1c61c6cae3bfb49115a661ab84a207832cb96dcb754ae5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **346.5 MB (346493216 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fb39cb98032a40e6e70de6ccb3965fb2f6bb563e7354049157c79841d648b574`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:33:25 GMT
ADD file:a71e077a42995a68ffe4834d85cfe26af4ea12aa8ed43decc03cc487124b1f70 in / 
# Mon, 09 Oct 2017 21:33:25 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 22:37:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:37:38 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 22:37:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:39:04 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 03:08:53 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 25 Oct 2017 19:06:15 GMT
ENV RUBY_MAJOR=2.5-rc
# Wed, 25 Oct 2017 19:06:15 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Wed, 25 Oct 2017 19:06:16 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Wed, 25 Oct 2017 19:06:16 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Wed, 25 Oct 2017 19:06:16 GMT
ENV BUNDLER_VERSION=1.15.4
# Wed, 25 Oct 2017 19:08:30 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Wed, 25 Oct 2017 19:08:30 GMT
ENV GEM_HOME=/usr/local/bundle
# Wed, 25 Oct 2017 19:08:30 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Wed, 25 Oct 2017 19:08:30 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 25 Oct 2017 19:08:31 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Wed, 25 Oct 2017 19:08:31 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:3e17c6eae66cd23c59751c8d8f5eaf7044e0611dc5cebb12b1273be07cdac242`  
		Last Modified: Mon, 09 Oct 2017 21:41:38 GMT  
		Size: 45.1 MB (45129088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74d44b20f851c8ef0b042070ba8eb018b386f50fdae5c37871d3fe7b4cfb4956`  
		Last Modified: Mon, 09 Oct 2017 23:01:17 GMT  
		Size: 11.1 MB (11106736 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a156217f3fa434b4821b01f0d24be50ead40560053fb5b65982f52507f55bc12`  
		Last Modified: Mon, 09 Oct 2017 23:01:15 GMT  
		Size: 4.6 MB (4633218 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a1ed13b6faa4be7117a973f02c46398e98adfb4a2af34cb279fc5908e37ccba`  
		Last Modified: Mon, 09 Oct 2017 23:02:37 GMT  
		Size: 50.0 MB (50021676 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6defea3d225a067064d5e7c9730c603aad2a0b75199c3af02a22feefd9c5bd1`  
		Last Modified: Mon, 09 Oct 2017 23:03:38 GMT  
		Size: 212.8 MB (212785117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e5e4536768b1cf67f603afe3c3b841c89349c0a04c4aa2cc84ea51c606e302e`  
		Last Modified: Tue, 10 Oct 2017 03:58:07 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba7b9c947d49cfdaf0950f6622a73e76db977c3a009acd98be16bbeb3e25f293`  
		Last Modified: Wed, 25 Oct 2017 19:56:13 GMT  
		Size: 22.8 MB (22817012 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5f281b918412d734fbcbe58f04e9282d19b5efccda3ef57f8fbd0ef9c1997f2`  
		Last Modified: Wed, 25 Oct 2017 19:56:07 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; arm variant v5

```console
$ docker pull ruby@sha256:606efa41c02c31f5fbcad202e0698d384efd137116cf60f099ec00b5e4bddd98
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **330.2 MB (330213521 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e4148ca64b0cc39de056262bd5affec22025385c3aa337fa9c41de9ba5484d5e`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:44:33 GMT
ADD file:faa50a4d3491f148f07964f6b9f9c8e97c0cf64588b20deb10f24e2f4f6c6b87 in / 
# Mon, 09 Oct 2017 21:44:33 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 22:18:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:19:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 22:19:41 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:21:29 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 00:25:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Thu, 26 Oct 2017 01:21:35 GMT
ENV RUBY_MAJOR=2.5-rc
# Thu, 26 Oct 2017 01:21:35 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Thu, 26 Oct 2017 01:21:35 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Thu, 26 Oct 2017 01:21:36 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Thu, 26 Oct 2017 01:21:36 GMT
ENV BUNDLER_VERSION=1.15.4
# Thu, 26 Oct 2017 01:23:57 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Thu, 26 Oct 2017 01:23:57 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 26 Oct 2017 01:23:57 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 26 Oct 2017 01:23:57 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 26 Oct 2017 01:23:58 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 26 Oct 2017 01:23:58 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:3c60e7fc5441d6c90edac385048cfe55b732e74ac7a95ce0f52555d1fdd4777a`  
		Last Modified: Mon, 09 Oct 2017 21:50:32 GMT  
		Size: 43.8 MB (43815910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c0eb374b4a5889510ab6af5360e74f8471d96bbbb4b1585f37be4fbda09d06c`  
		Last Modified: Mon, 09 Oct 2017 22:26:12 GMT  
		Size: 10.2 MB (10205119 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f713ec73030eef0749d2b44c7fce2fabd4c3a5ea319b731b4a5bb22fff47d244`  
		Last Modified: Mon, 09 Oct 2017 22:26:10 GMT  
		Size: 4.5 MB (4450769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:928b1607d21d7f38bc3d880c6604d185f09b8932387d93d11ffebcc62a692bb7`  
		Last Modified: Mon, 09 Oct 2017 22:26:36 GMT  
		Size: 48.2 MB (48225718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8f4e093db83a4274cb0d3b339d9e8b7d4157652e290ad05519bb532457b83ac`  
		Last Modified: Mon, 09 Oct 2017 22:27:37 GMT  
		Size: 201.1 MB (201104019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a8265526b568819ddcea32640fbddd358089d7efd4c020f1cb89f337898b3e0`  
		Last Modified: Tue, 10 Oct 2017 01:12:20 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824f30cd65e975532154cd04bd64ce173f4610bd4a56664e4ea8142cd7edacfc`  
		Last Modified: Thu, 26 Oct 2017 02:10:04 GMT  
		Size: 22.4 MB (22411582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0002eb14e3ca9e2db012df98b73ea76c4adbd9e6cf1699f0a5a69cd995f3476`  
		Last Modified: Thu, 26 Oct 2017 02:09:58 GMT  
		Size: 198.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; arm variant v7

```console
$ docker pull ruby@sha256:a7c819fb2a7b961a572a9a1c2cb6319ed1696e3aa7ee169f9ef98ddbb9ce7990
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **318.1 MB (318148030 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e238eb2ad0ae888d3400de06e4469a869903a567a365c0f9cd1a0735b224a9f2`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:45:23 GMT
ADD file:8b7cf813a113aa20eb7f5eecbb602ff5d306b7586add13ed5e082cd09770edb4 in / 
# Mon, 09 Oct 2017 21:45:23 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 22:23:39 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:23:46 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 22:24:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:25:42 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 00:16:48 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Thu, 26 Oct 2017 01:11:45 GMT
ENV RUBY_MAJOR=2.5-rc
# Thu, 26 Oct 2017 01:11:45 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Thu, 26 Oct 2017 01:11:45 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Thu, 26 Oct 2017 01:11:46 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Thu, 26 Oct 2017 01:11:46 GMT
ENV BUNDLER_VERSION=1.15.4
# Thu, 26 Oct 2017 01:13:54 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Thu, 26 Oct 2017 01:13:55 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 26 Oct 2017 01:13:55 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 26 Oct 2017 01:13:55 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 26 Oct 2017 01:13:56 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 26 Oct 2017 01:13:56 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:0d9fbbfaa2cd8961ae50e51e7388e3a2a1a5ca2c105389b56a3a862dfe76d035`  
		Last Modified: Mon, 09 Oct 2017 21:52:12 GMT  
		Size: 41.8 MB (41841946 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ad02a7a5b212c86cbdd527154a30708eccaa87b89053dd8b63d970bda7eb15c`  
		Last Modified: Mon, 09 Oct 2017 22:33:56 GMT  
		Size: 9.8 MB (9823849 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6bbcce226c5c7c39ae672de36f27124750688da88d920faf7faeda09ffaeb06`  
		Last Modified: Mon, 09 Oct 2017 22:33:55 GMT  
		Size: 4.2 MB (4209823 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbb73448c519a8cf4c670c025515e5cf1507429ab1d441d31d5865ef703aba00`  
		Last Modified: Mon, 09 Oct 2017 22:34:22 GMT  
		Size: 46.3 MB (46342791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f916f3caf61e73ce8e1f8ed37459fce43e1d54013488d8f4e4426c4164c1098b`  
		Last Modified: Mon, 09 Oct 2017 22:35:30 GMT  
		Size: 193.7 MB (193670955 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed526a747ca15303a9588df7c9d0e1659910d0bb05989db119b6446d41b07305`  
		Last Modified: Tue, 10 Oct 2017 01:00:34 GMT  
		Size: 204.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5ce3ff7e6266a25cf41712994c3545f86c1008f964371ffeca43f5cf3f7f5be`  
		Last Modified: Thu, 26 Oct 2017 01:56:11 GMT  
		Size: 22.3 MB (22258266 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38dd9d89b6684c69d6df184b0ff204871f78cbf4181d95492bd437acef7a7507`  
		Last Modified: Thu, 26 Oct 2017 01:56:05 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; arm64 variant v8

```console
$ docker pull ruby@sha256:3f3d42c2f3a968b9deba6647d222fb2940b0e9096402b8373db7c44ab207e418
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **328.2 MB (328219277 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d00f6f62bd7e52e0ee5c94da9e061aa0264f06e8eb6fff806cd90a5a571f6df5`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:47:18 GMT
ADD file:bf097edec8505e5cb1e432319988aeb28a6f918edef706b3c543fa61aaaea4cb in / 
# Mon, 09 Oct 2017 21:47:19 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 23:05:41 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:06:00 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 23:07:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:17:34 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 07:11:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 25 Oct 2017 20:39:18 GMT
ENV RUBY_MAJOR=2.5-rc
# Wed, 25 Oct 2017 20:39:18 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Wed, 25 Oct 2017 20:39:19 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Wed, 25 Oct 2017 20:39:19 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Wed, 25 Oct 2017 20:39:20 GMT
ENV BUNDLER_VERSION=1.15.4
# Wed, 25 Oct 2017 20:43:34 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Wed, 25 Oct 2017 20:43:35 GMT
ENV GEM_HOME=/usr/local/bundle
# Wed, 25 Oct 2017 20:43:35 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Wed, 25 Oct 2017 20:43:36 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 25 Oct 2017 20:43:38 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Wed, 25 Oct 2017 20:43:38 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:0e5a8be23912597ff0d89db096abd4c4383c8cf4ee700d333b86f881ea289875`  
		Last Modified: Mon, 09 Oct 2017 22:01:04 GMT  
		Size: 42.9 MB (42911727 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d7589dd246446eb7fba574b55eeb0810199cb0a935b7d349b8a930f23af9b13`  
		Last Modified: Mon, 09 Oct 2017 23:34:08 GMT  
		Size: 10.1 MB (10066395 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef5f5555283659c080227d6cf1bace5def3d5c3e6d742746e51494849fb4aeb3`  
		Last Modified: Mon, 09 Oct 2017 23:34:05 GMT  
		Size: 4.4 MB (4385243 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50fc460f5f7f70833a25c52d6200ced8a4004784a9dc391c6ea4f0bdca6cd51a`  
		Last Modified: Mon, 09 Oct 2017 23:35:03 GMT  
		Size: 48.0 MB (47973994 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26c91ac7b9fdc4fd9893504b5d1e6211a77ba8286a16d9dce779f8e04abc6894`  
		Last Modified: Mon, 09 Oct 2017 23:37:20 GMT  
		Size: 200.3 MB (200256724 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33d1a3b5463064c41d5b9f784219688229de4c7dff080766b1e1f06fc5dab4af`  
		Last Modified: Tue, 10 Oct 2017 08:34:56 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bef2ae08f35291ed3ce70871b4ce97f3753565c4503f673ddebad8763f4a6fe`  
		Last Modified: Wed, 25 Oct 2017 21:56:10 GMT  
		Size: 22.6 MB (22624825 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60106b76341504542f7b28e0427fc77a6d4028a8fc67556ee72a3c569c46f1b3`  
		Last Modified: Wed, 25 Oct 2017 21:56:01 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; 386

```console
$ docker pull ruby@sha256:ccc51e99b50238838902a264dbd6c5576eb3246239eeeeabdfaa546021dfb0a6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **353.6 MB (353627658 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ec5681243d34c7b3d9f6b7b77ccafe9b4607a707356bba87fe77946363429f45`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:45:21 GMT
ADD file:14ce0e7f11224a3d3ef5a62ece43529a687ada430b8d8ecfa0e0a5d2d1e47467 in / 
# Mon, 09 Oct 2017 21:45:21 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 23:17:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:18:05 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 23:18:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:21:41 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 02:29:05 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Thu, 26 Oct 2017 02:36:40 GMT
ENV RUBY_MAJOR=2.5-rc
# Thu, 26 Oct 2017 02:36:40 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Thu, 26 Oct 2017 02:36:40 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Thu, 26 Oct 2017 02:36:40 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Thu, 26 Oct 2017 02:36:41 GMT
ENV BUNDLER_VERSION=1.15.4
# Thu, 26 Oct 2017 02:39:18 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Thu, 26 Oct 2017 02:39:18 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 26 Oct 2017 02:39:18 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 26 Oct 2017 02:39:18 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 26 Oct 2017 02:39:19 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 26 Oct 2017 02:39:19 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:d1d52bc84c959ce2a6002a4aab897e247f2b7a55c1440de500f57e791c7814f3`  
		Last Modified: Mon, 09 Oct 2017 21:52:48 GMT  
		Size: 45.8 MB (45833677 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49155822b6274da1500beeea1b851fe93477c0f24c9139e66a6b08b28e94947a`  
		Last Modified: Mon, 09 Oct 2017 23:44:19 GMT  
		Size: 11.1 MB (11149763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:612edda692ea6ffd7b7804e0853087b5051708a461f81b600a2eff2391245512`  
		Last Modified: Mon, 09 Oct 2017 23:44:18 GMT  
		Size: 4.9 MB (4852438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0dde6a8931f23491215f28541bcbc153f642dff8f291c5d70cc81b9b93b7a18f`  
		Last Modified: Mon, 09 Oct 2017 23:44:56 GMT  
		Size: 51.5 MB (51547081 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5dce68d732b0454cc6ff7e48854c023a0221ac939160062e3e4463e0e27658a`  
		Last Modified: Mon, 09 Oct 2017 23:45:56 GMT  
		Size: 217.9 MB (217850045 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1586d6d825d2ffba8a0b7ca82b8a2b714f03459d34abed950b4e081c00f725d2`  
		Last Modified: Tue, 10 Oct 2017 03:22:25 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f3ca791062bc5c012271da80fbefc6d4556e263faf41fc12fea6711cfd1e49a`  
		Last Modified: Thu, 26 Oct 2017 03:25:17 GMT  
		Size: 22.4 MB (22394284 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebd963a583379ba98443110fc816304be126e904decc40615ecade48eab342c4`  
		Last Modified: Thu, 26 Oct 2017 03:25:13 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; ppc64le

```console
$ docker pull ruby@sha256:d593d3578bb87657c5af696e3d2a6aaaa1077f22f68824261ba0a656532ccba2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **341.9 MB (341863984 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:11fe9994191b25b21b04004b44f09279cceec5f47219b1fe516bc8ceeabdf877`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:45:33 GMT
ADD file:5217c22b771467c9c3563f1e5b1bbd92eff26c36f0dafc6cfed4ba0664f12a45 in / 
# Mon, 09 Oct 2017 21:45:35 GMT
CMD ["bash"]
# Tue, 10 Oct 2017 00:13:20 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 00:14:12 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 10 Oct 2017 00:19:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 00:49:54 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 10 Oct 2017 05:26:50 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Thu, 26 Oct 2017 00:16:31 GMT
ENV RUBY_MAJOR=2.5-rc
# Thu, 26 Oct 2017 00:16:33 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Thu, 26 Oct 2017 00:16:34 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Thu, 26 Oct 2017 00:16:35 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Thu, 26 Oct 2017 00:16:37 GMT
ENV BUNDLER_VERSION=1.15.4
# Thu, 26 Oct 2017 00:19:44 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Thu, 26 Oct 2017 00:19:45 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 26 Oct 2017 00:19:47 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 26 Oct 2017 00:19:49 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 26 Oct 2017 00:19:53 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 26 Oct 2017 00:19:55 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:f2df583ad5343147c4ed6ea52882355b70e206e1a801cbb0fe3b6fc6c7b0189a`  
		Last Modified: Mon, 09 Oct 2017 21:52:17 GMT  
		Size: 45.4 MB (45378365 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b68ed2fe64e9c2dfe79d5d484b75ed9d17ac5941067e9d69cb194ac257feec3a`  
		Last Modified: Tue, 10 Oct 2017 00:58:01 GMT  
		Size: 10.3 MB (10338918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fcb4b07bc1d76cd1d3e264929d07b103dc8a16ecba513a1d5a03d3b5d54b919`  
		Last Modified: Tue, 10 Oct 2017 00:58:00 GMT  
		Size: 4.6 MB (4587455 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f601576bea3b971a5c48ce185e438f8ef5a459c0af4d71e2a76e2f1614985ff`  
		Last Modified: Tue, 10 Oct 2017 00:58:29 GMT  
		Size: 50.0 MB (50025661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3efe075148e3d0d4a27ec2d484a6af056ef42742fdf117989d299f166f7d56a0`  
		Last Modified: Tue, 10 Oct 2017 00:59:30 GMT  
		Size: 208.5 MB (208478762 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87590c26095709980d1d8d38389a6fe68465b258e927b70b6ffd0fa0e5f99cd0`  
		Last Modified: Tue, 10 Oct 2017 06:47:54 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2fe204eb8cd0fcb91a2747508982c5945c12648554374dda90d9326b0f0f3ee9`  
		Last Modified: Thu, 26 Oct 2017 01:36:00 GMT  
		Size: 23.1 MB (23054422 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0979482a643e91527e7695840be126f2903b02f751d9c0f87d8f958abfda588e`  
		Last Modified: Thu, 26 Oct 2017 01:35:55 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-stretch` - linux; s390x

```console
$ docker pull ruby@sha256:3e10d3e1423e62f50c333d064902b5aecd2d960b535ad43c8bfb1edb12569b0d
```

-	Docker Version: 17.06.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **338.8 MB (338768239 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b82c567fef5b406caeadabc0099d05a538bf21ab79034c01bf1b9641501a5676`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 09 Oct 2017 21:44:19 GMT
ADD file:11704b7d478d6b95a0cfeb557a4a4a03c02fde3849dd3e01da2d1228c6b815f0 in / 
# Mon, 09 Oct 2017 21:44:19 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 22:15:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:15:44 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg2 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Mon, 09 Oct 2017 22:16:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 22:18:00 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		dpkg-dev 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:49:48 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Thu, 26 Oct 2017 08:29:39 GMT
ENV RUBY_MAJOR=2.5-rc
# Thu, 26 Oct 2017 08:29:39 GMT
ENV RUBY_VERSION=2.5.0-preview1
# Thu, 26 Oct 2017 08:29:39 GMT
ENV RUBY_DOWNLOAD_SHA256=c2f518eb04b38bdd562ba5611abd2521248a1608fc466368563dd794ddeddd09
# Thu, 26 Oct 2017 08:29:39 GMT
ENV RUBYGEMS_VERSION=2.6.14
# Thu, 26 Oct 2017 08:29:40 GMT
ENV BUNDLER_VERSION=1.15.4
# Thu, 26 Oct 2017 08:31:42 GMT
RUN set -ex 		&& buildDeps=' 		bison 		dpkg-dev 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force
# Thu, 26 Oct 2017 08:31:42 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 26 Oct 2017 08:31:42 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 26 Oct 2017 08:31:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 26 Oct 2017 08:31:43 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 26 Oct 2017 08:31:43 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:c6630da1278315ced68910beef5ac605807b880918d11d0c02c4d3eac7307008`  
		Last Modified: Mon, 09 Oct 2017 21:48:41 GMT  
		Size: 45.0 MB (44972760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b33b5e0a1749d0366c28b4b88ae0139119ba36640fa31f7ed3d2ec974ae1127b`  
		Last Modified: Mon, 09 Oct 2017 22:21:54 GMT  
		Size: 10.7 MB (10667715 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:049887af1090e55495d4d3f232c2441d3bb8b420366662539c3bfb829e349496`  
		Last Modified: Mon, 09 Oct 2017 22:21:53 GMT  
		Size: 4.7 MB (4664115 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88994e2adeee9dcccd21288a4ca51444bc7374338cac5c49346a4abab141c964`  
		Last Modified: Mon, 09 Oct 2017 22:22:13 GMT  
		Size: 50.4 MB (50441493 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5249ce60b7b29073c1b796adf16879d92802b28cd260b735221576dd86fba543`  
		Last Modified: Mon, 09 Oct 2017 22:22:58 GMT  
		Size: 204.9 MB (204859875 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6958ba5ab9fd2c1e6888fb2671c0d15bf614efbe293d73b30d7ad40085f276a3`  
		Last Modified: Tue, 10 Oct 2017 00:15:10 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2e845e7c26de992cf44740ac752738029d6f9cf06d9cb71564db24abc6bdb63`  
		Last Modified: Thu, 26 Oct 2017 09:05:54 GMT  
		Size: 23.2 MB (23161911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d180411cbcf23804cdd770d8e85827026e8693c0e555470b86d9a9e83abdf3b`  
		Last Modified: Thu, 26 Oct 2017 09:05:50 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip