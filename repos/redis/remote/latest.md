## `redis:latest`

```console
$ docker pull redis@sha256:0e773022cd6572a5153e5013afced0f7191652d3cdf9b1c6785eb13f6b2974b1
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

### `redis:latest` - linux; amd64

```console
$ docker pull redis@sha256:9b1b75fa6364b2ec538a5efdb00c3511adee5b6b2f80d5c64b06c4456ad573f6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **39.4 MB (39388192 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1e70071f4af45af2cc9e1d1300c675c1ce37ee25a8a5cef1f375db5ed461dbab`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:34 GMT
ADD file:e7ac45803c3ab9b7023933b75f5a88eda1f3edca97c7e462401860777cf312f7 in / 
# Tue, 12 Dec 2017 01:41:35 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:11:57 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 07:11:57 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 07:12:20 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 12 Dec 2017 07:15:08 GMT
ENV REDIS_VERSION=4.0.6
# Tue, 12 Dec 2017 07:15:08 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Tue, 12 Dec 2017 07:15:08 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Tue, 12 Dec 2017 07:15:52 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 12 Dec 2017 07:15:57 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 12 Dec 2017 07:15:57 GMT
VOLUME [/data]
# Tue, 12 Dec 2017 07:15:57 GMT
WORKDIR /data
# Tue, 12 Dec 2017 07:15:58 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 12 Dec 2017 07:15:58 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 12 Dec 2017 07:15:58 GMT
EXPOSE 6379/tcp
# Tue, 12 Dec 2017 07:15:58 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:c4bb02b17bb4b034c95a948c99c762cf0486a45f45441a052208d7750f1b413b`  
		Last Modified: Tue, 12 Dec 2017 01:48:52 GMT  
		Size: 30.1 MB (30114519 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58638acf67c5d1d65732b562d5a7f5525b9788155cc10d4cd96c3d5380fadf04`  
		Last Modified: Tue, 12 Dec 2017 07:17:40 GMT  
		Size: 2.1 KB (2086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f98d108cc38bde856021760374435ab87fa2ef7c4317cd18fd7b7ded7af506a3`  
		Last Modified: Tue, 12 Dec 2017 07:17:40 GMT  
		Size: 981.7 KB (981699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83be14fccb07d255f2c1ea091c58d86bf3816d035eee7e2cd918f1c6824b2138`  
		Last Modified: Tue, 12 Dec 2017 07:18:51 GMT  
		Size: 8.3 MB (8289389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d5f41793421633c9f4abb13e20bce43a06f430de39fbb71a78784d813a07669`  
		Last Modified: Tue, 12 Dec 2017 07:18:49 GMT  
		Size: 97.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed89ff0d9eb221cd234f6d002f9a04a253e35af2d7da1263be85bf6ee9b04645`  
		Last Modified: Tue, 12 Dec 2017 07:18:50 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v5

```console
$ docker pull redis@sha256:f296552096465b161049203a4e15b6743783ea32a4b7ebab55cc89a6b6230e61
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.6 MB (37581406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:01bb8ecc8259701922ae6b9867fac9b3ac63d777581967fefe748fbdb11b7c47`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 20:57:33 GMT
ADD file:29d0e44ebcc6f8dc2cfbc86c5034380677d263e9eec27a22ba045e0810836f81 in / 
# Tue, 12 Dec 2017 20:57:34 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 23:14:35 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 23:14:35 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 23:15:21 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 12 Dec 2017 23:16:43 GMT
ENV REDIS_VERSION=4.0.6
# Tue, 12 Dec 2017 23:16:43 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Tue, 12 Dec 2017 23:16:43 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Tue, 12 Dec 2017 23:17:46 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 12 Dec 2017 23:17:47 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 12 Dec 2017 23:17:47 GMT
VOLUME [/data]
# Tue, 12 Dec 2017 23:17:48 GMT
WORKDIR /data
# Tue, 12 Dec 2017 23:17:48 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 12 Dec 2017 23:17:49 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 12 Dec 2017 23:17:49 GMT
EXPOSE 6379/tcp
# Tue, 12 Dec 2017 23:17:49 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:51e696f556166d0e25b3b27c824c4aafbddd5adcfd3f5186c09707f7baa3b312`  
		Last Modified: Tue, 12 Dec 2017 21:07:41 GMT  
		Size: 28.4 MB (28423526 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0206b9cb3a70c21180f01a2532fe2c5a436a48e5fc5d8b939ba69b7d61c80a3a`  
		Last Modified: Tue, 12 Dec 2017 23:18:09 GMT  
		Size: 2.1 KB (2075 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f18f2f5d7b2619f7683612c23f23c54c1f09a9ac9f5714f36e1ff47dffac347`  
		Last Modified: Tue, 12 Dec 2017 23:18:13 GMT  
		Size: 971.2 KB (971228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0074e58b3651c3daae36b9ee59f0048658027f2be986bc02f604fb0f3da7ed4e`  
		Last Modified: Tue, 12 Dec 2017 23:18:47 GMT  
		Size: 8.2 MB (8184040 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5515ebe8ad7b43e8d77c47aa8d35b7ebb52aa6bd3255cf20bef2f0b9d35251b`  
		Last Modified: Tue, 12 Dec 2017 23:18:44 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64faed35017fa0e8ea6e9295527bfb36100834f29f1be6042bf4d0bb66270948`  
		Last Modified: Tue, 12 Dec 2017 23:18:44 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v7

```console
$ docker pull redis@sha256:e045f0cea16550a9bd55384c0e5de81051d16f8b6908d36dc04762e31945d111
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **35.2 MB (35162949 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3e090cd1dc17b4ce92a4be7a7665cb93d325f572fad3b0e1f90bdc831764f1b6`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 13:27:47 GMT
ADD file:1f5de474caa19da14d698a3f9c3d161abfa1e19e258a596d64f3dfc9e2f17686 in / 
# Tue, 12 Dec 2017 13:27:47 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 16:40:56 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 16:40:56 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 16:41:50 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 12 Dec 2017 16:43:28 GMT
ENV REDIS_VERSION=4.0.6
# Tue, 12 Dec 2017 16:43:29 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Tue, 12 Dec 2017 16:43:29 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Tue, 12 Dec 2017 16:44:30 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 12 Dec 2017 16:44:31 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 12 Dec 2017 16:44:31 GMT
VOLUME [/data]
# Tue, 12 Dec 2017 16:44:31 GMT
WORKDIR /data
# Tue, 12 Dec 2017 16:44:32 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 12 Dec 2017 16:44:32 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 12 Dec 2017 16:44:32 GMT
EXPOSE 6379/tcp
# Tue, 12 Dec 2017 16:44:33 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:4b9c0f1a415433a98643bdda391dcf4fe5d9653fc3ed3845c7ac1be99eb43399`  
		Last Modified: Tue, 12 Dec 2017 13:39:52 GMT  
		Size: 26.3 MB (26282714 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d6835fe576543df3c87405f33db99aa1f040e3f241c5e5d72ffb416953902b8`  
		Last Modified: Tue, 12 Dec 2017 16:44:59 GMT  
		Size: 2.1 KB (2076 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a11c10ad12017478481b1755839ece7c69945ee8c04b97bb10909db85e4ed338`  
		Last Modified: Tue, 12 Dec 2017 16:44:59 GMT  
		Size: 956.1 KB (956126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0075b0f5ce2d7ce55e223747f8a39bfff706785c0e7dbf64f6335ba5349a1dc8`  
		Last Modified: Tue, 12 Dec 2017 16:45:49 GMT  
		Size: 7.9 MB (7921495 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efe8e636d1c0d7601640af09e05a985e61dbed3cff18f7ce8a82efea81ee5cf7`  
		Last Modified: Tue, 12 Dec 2017 16:45:47 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b01a2c423f053a3cbe86d05916121aab0edfa588ff85a46d63a571f5f91dd286`  
		Last Modified: Tue, 12 Dec 2017 16:45:46 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm64 variant v8

```console
$ docker pull redis@sha256:772324452dbd139f77cdc302070da973ade16f4037330ec10fa73c142972eeeb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **36.9 MB (36863027 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a8c26a8b3e0dca575485222459b518c7a7e4f7ab53d9c939cff6c510525c5add`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 18:26:03 GMT
ADD file:da6be268a98d89a43438155746ca6d08f474e9aa85c64699f50445352b46c348 in / 
# Tue, 12 Dec 2017 18:26:04 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 13:25:39 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 20 Dec 2017 13:25:40 GMT
ENV GOSU_VERSION=1.10
# Wed, 20 Dec 2017 13:26:36 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 20 Dec 2017 13:28:47 GMT
ENV REDIS_VERSION=4.0.6
# Wed, 20 Dec 2017 13:28:48 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Wed, 20 Dec 2017 13:28:48 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Wed, 20 Dec 2017 13:30:31 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Dec 2017 13:30:32 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 20 Dec 2017 13:30:33 GMT
VOLUME [/data]
# Wed, 20 Dec 2017 13:30:34 GMT
WORKDIR /data
# Wed, 20 Dec 2017 13:30:35 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 20 Dec 2017 13:30:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 20 Dec 2017 13:30:36 GMT
EXPOSE 6379/tcp
# Wed, 20 Dec 2017 13:30:37 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:8e9df51286bbe86a4cb3ffe54327681ab34b9b6d62c3f4e187ffc677125e4780`  
		Last Modified: Tue, 12 Dec 2017 18:41:37 GMT  
		Size: 27.5 MB (27480582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:075c247daad6bb45a002c0a24377355e91aef8e96dbc920ef85b5f95dba5d597`  
		Last Modified: Wed, 20 Dec 2017 13:31:04 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:671b4ef947e36f312884f8d49f560e5191e57a0e583820b56b530e7ff03d771f`  
		Last Modified: Wed, 20 Dec 2017 13:31:04 GMT  
		Size: 948.7 KB (948652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2edff2b39e2645967f81245675eaea1da0ff3904553e75329baef8bbfab1b413`  
		Last Modified: Wed, 20 Dec 2017 13:31:33 GMT  
		Size: 8.4 MB (8431191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9dabcdc71ed6a8ccb39aceda1929016ee677dc6cce81f5bdfa1c0af3730dfbd3`  
		Last Modified: Wed, 20 Dec 2017 13:31:28 GMT  
		Size: 99.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8ac6fe688a6366025e38bbdabd8e78bbe684e20a033dd414e84c6c653d11a00`  
		Last Modified: Wed, 20 Dec 2017 13:31:28 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; 386

```console
$ docker pull redis@sha256:e40d6fa49c73fa791d7cba6ee3518131f1968941415ffe013925e8968b1c6c65
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.7 MB (38731890 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bd9b9afd5acac06f47ee789186dfa0d3554c3dbb1e8826a23df99e8859926a41`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 14:21:05 GMT
ADD file:d31765999b40e32b628f3ec72b762f007f4918b08c507484e425adc990c87c26 in / 
# Tue, 12 Dec 2017 14:21:05 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 21:03:38 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 21:03:38 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 21:04:16 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 12 Dec 2017 21:10:03 GMT
ENV REDIS_VERSION=4.0.6
# Tue, 12 Dec 2017 21:10:04 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Tue, 12 Dec 2017 21:10:04 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Tue, 12 Dec 2017 21:11:11 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 12 Dec 2017 21:11:11 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 12 Dec 2017 21:11:12 GMT
VOLUME [/data]
# Tue, 12 Dec 2017 21:11:12 GMT
WORKDIR /data
# Tue, 12 Dec 2017 21:11:12 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 12 Dec 2017 21:11:12 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 12 Dec 2017 21:11:13 GMT
EXPOSE 6379/tcp
# Tue, 12 Dec 2017 21:11:13 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:6b323e7c684c46ec9e577d3acb692c7e1c0c26ffbea6a4530dbe784a7eedf0f7`  
		Last Modified: Tue, 12 Dec 2017 14:49:35 GMT  
		Size: 30.3 MB (30266257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00b36a22b0f548b632d8bc28aa752a7c776351e3fa3c167b13901a9a648dff0f`  
		Last Modified: Tue, 12 Dec 2017 21:11:34 GMT  
		Size: 2.1 KB (2074 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:625bd220ae9238fdcd1a3e9db810236dc47502995b93d54b4a7bc5f474508112`  
		Last Modified: Tue, 12 Dec 2017 21:11:34 GMT  
		Size: 960.8 KB (960808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07d03559e91129a1767ce1c947568a0f866763262e2b08a9b22005cf8a54b6f7`  
		Last Modified: Tue, 12 Dec 2017 21:12:25 GMT  
		Size: 7.5 MB (7502251 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a227f62b2d1c39ca67c954e4c31d92d9beecf4efa9429b085e2bd98a74eda13a`  
		Last Modified: Tue, 12 Dec 2017 21:12:23 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:467e52a47193ff1ad6e65a498e7e57ce55b2cfd06e89eeb105ad821458c6c76e`  
		Last Modified: Tue, 12 Dec 2017 21:12:24 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; ppc64le

```console
$ docker pull redis@sha256:c22f5854c80dd97cdfed7b68ab37d8b0857d7692cbff2d393e8363e20780a178
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.9 MB (38908637 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:36632c4353fb4fce16c36efaef0a526ecb112143de79125131e7dc1ac5879c47`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 01:33:17 GMT
ADD file:db3712029b01ae02058b528d156cfdf714f7f2b5fc30216a349f13c15ff9fd67 in / 
# Tue, 12 Dec 2017 01:33:18 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 06:40:30 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 06:40:32 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 06:42:22 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 12 Dec 2017 06:45:54 GMT
ENV REDIS_VERSION=4.0.6
# Tue, 12 Dec 2017 06:45:55 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Tue, 12 Dec 2017 06:45:56 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Tue, 12 Dec 2017 06:49:54 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 12 Dec 2017 06:49:58 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 12 Dec 2017 06:50:01 GMT
VOLUME [/data]
# Tue, 12 Dec 2017 06:50:03 GMT
WORKDIR /data
# Tue, 12 Dec 2017 06:50:05 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 12 Dec 2017 06:50:07 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 12 Dec 2017 06:50:10 GMT
EXPOSE 6379/tcp
# Tue, 12 Dec 2017 06:50:12 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:f90148bfa218fdcac96e1ad5dd98070db3f45afdca6148d5d71bb9c4b12e5776`  
		Last Modified: Tue, 12 Dec 2017 01:39:02 GMT  
		Size: 29.3 MB (29306117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f662385d2726c68cbb1dde138126e2577b69f2f75edb031782b33056fcca8e15`  
		Last Modified: Tue, 12 Dec 2017 06:50:31 GMT  
		Size: 2.1 KB (2098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75d4e7f0b93f593fb94ad43d33ba101f2f418b2ce017189138ab2b434f5a6b19`  
		Last Modified: Tue, 12 Dec 2017 06:50:31 GMT  
		Size: 950.7 KB (950658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:995b57ca83fc25dcaa2fa366d3a0c534a004be89beb8ec6fcf1eafa0f3de222a`  
		Last Modified: Tue, 12 Dec 2017 06:50:57 GMT  
		Size: 8.6 MB (8649230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2105c4a7db335500550624b6e48529e8a09884362c45773ca27cba765f7980f`  
		Last Modified: Tue, 12 Dec 2017 06:50:55 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87efefb7310b373f85c699c7a1abaf9621c0ad35af3f9b57cb78b8f7ccaeb671`  
		Last Modified: Tue, 12 Dec 2017 06:50:55 GMT  
		Size: 401.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; s390x

```console
$ docker pull redis@sha256:901d5ba30ab76bf0ae20e96dd128585a6f3165f08f60fd2b9315d6ea00bf9d73
```

-	Docker Version: 17.06.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.2 MB (40188456 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5a8bfc0e1928b3717bd025d03f7203e835b999fce9bdc61b89fbe3ffb0177282`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 06:23:05 GMT
ADD file:68877912183dff16971679b6264399a76d678986d7cf02bbba2e006d91077cf3 in / 
# Tue, 12 Dec 2017 06:23:06 GMT
CMD ["bash"]
# Sun, 07 Jan 2018 09:26:06 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Sun, 07 Jan 2018 09:26:06 GMT
ENV GOSU_VERSION=1.10
# Sun, 07 Jan 2018 09:26:33 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Sun, 07 Jan 2018 09:27:44 GMT
ENV REDIS_VERSION=4.0.6
# Sun, 07 Jan 2018 09:27:45 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.6.tar.gz
# Sun, 07 Jan 2018 09:27:45 GMT
ENV REDIS_DOWNLOAD_SHA=769b5d69ec237c3e0481a262ff5306ce30db9b5c8ceb14d1023491ca7be5f6fa
# Sun, 07 Jan 2018 09:28:27 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Sun, 07 Jan 2018 09:28:28 GMT
RUN mkdir /data && chown redis:redis /data
# Sun, 07 Jan 2018 09:28:28 GMT
VOLUME [/data]
# Sun, 07 Jan 2018 09:28:28 GMT
WORKDIR /data
# Sun, 07 Jan 2018 09:28:28 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Sun, 07 Jan 2018 09:28:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sun, 07 Jan 2018 09:28:29 GMT
EXPOSE 6379/tcp
# Sun, 07 Jan 2018 09:28:29 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:7ef9b5c13de473137c3ae16d379a5f152b59921d4e96887c06f9e1291af84691`  
		Last Modified: Thu, 14 Dec 2017 00:53:34 GMT  
		Size: 30.3 MB (30293639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608e779e09f2eff9338668b6f32d30ad6db5824db6e05a40163baa53af8a4732`  
		Last Modified: Sun, 07 Jan 2018 09:28:52 GMT  
		Size: 2.1 KB (2094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca3bc2bf99d2d3b8b7af50eabf05bcd385693d216437119560e8b76a250123d1`  
		Last Modified: Sun, 07 Jan 2018 09:28:52 GMT  
		Size: 966.9 KB (966920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d93131700fa59795d6ccca30d2f8cdc610658f1422e91583aa027e0843090631`  
		Last Modified: Sun, 07 Jan 2018 09:29:15 GMT  
		Size: 8.9 MB (8925301 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89f3d6362a0162c2ef6791223e5dc5ce9ddc3810980d0fcc5abb80c534702d50`  
		Last Modified: Sun, 07 Jan 2018 09:29:13 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:973e367a80f321379407be8036fadcf12289512a68d9a6e28f2eb30e1266898b`  
		Last Modified: Sun, 07 Jan 2018 09:29:13 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
