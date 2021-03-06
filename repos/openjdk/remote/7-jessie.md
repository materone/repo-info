## `openjdk:7-jessie`

```console
$ docker pull openjdk@sha256:96dcc3fccf96e8fbf1bf8b4eb3dfd6d536f48763f0289981db8d7402c6beaa23
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `openjdk:7-jessie` - linux; amd64

```console
$ docker pull openjdk@sha256:9e8e61c83372372430822765bceaafd1f26e0038b628dbdb24c16fb8cb5798cc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.9 MB (244873141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:421912beb852f0a631cbf5b904bbdf79e1348089656f908e2f46b1dd53a313fa`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:12 GMT
ADD file:1dd78a123212328bdc72ef7888024ea27fe141a72e24e0ea7c3c92b63b73d8d1 in / 
# Tue, 12 Dec 2017 01:41:12 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:49:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:49:01 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 07:49:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:03:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:03:13 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 15:03:14 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 15:03:16 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 15:03:16 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Dec 2017 15:03:16 GMT
ENV JAVA_VERSION=7u151
# Tue, 12 Dec 2017 15:03:17 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Tue, 12 Dec 2017 15:04:30 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:f49cf87b52c10aa83b4f4405800527a74400fb19ea1821d209293bc4d53966aa`  
		Last Modified: Tue, 12 Dec 2017 01:47:59 GMT  
		Size: 52.6 MB (52599697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b491c575b06601bb07a2d88bfc3ace6c6005edc1b4d8da3ba6e37e04e9592d6`  
		Last Modified: Tue, 12 Dec 2017 08:00:34 GMT  
		Size: 19.3 MB (19266203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b313b08bab3b8bbcf0de4171a2a80a01e67fab094f272819b76a58705d21ab28`  
		Last Modified: Tue, 12 Dec 2017 08:01:02 GMT  
		Size: 43.3 MB (43253338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8cc7f451a527dc5892b61c6ffa31c44df40c1492a08339358c011899af0e528`  
		Last Modified: Tue, 12 Dec 2017 15:46:53 GMT  
		Size: 828.7 KB (828699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bb0332dfffd895bf40582440d05bab7d23ea0dde65e014096cfddad95dbd068`  
		Last Modified: Tue, 12 Dec 2017 15:46:52 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90ee39fddbf814698aafab5993f3657becf3ca19e172d1485bc4e2a3177c27fb`  
		Last Modified: Tue, 12 Dec 2017 15:46:53 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e76d5249a272c1767328f7bc8bafb39b64ed7f65adb348a3d9da17d1064f9728`  
		Last Modified: Tue, 12 Dec 2017 15:47:20 GMT  
		Size: 128.9 MB (128924827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:7-jessie` - linux; arm variant v5

```console
$ docker pull openjdk@sha256:fbd6913fa1e23e7ca236b96e227ea8aec9607ad058133e5275726391e766594d
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **215.9 MB (215912231 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0d70654205535a36e588edae9c1e2de6bd3ba023c4766825bab3ee661b222112`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 20:57:00 GMT
ADD file:2c2c6b8bfbbc9860c0ddd8a2ba3d769171576fc13d5d99fb50a852f6b03618d1 in / 
# Tue, 12 Dec 2017 20:57:00 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 22:52:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 22:52:43 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 22:54:01 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 23:26:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 23:26:09 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 23:26:09 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 23:26:10 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 23:26:11 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Dec 2017 23:26:11 GMT
ENV JAVA_VERSION=7u151
# Tue, 12 Dec 2017 23:26:11 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Tue, 12 Dec 2017 23:27:33 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:fbe67b6ec6f136174afee77eff07fd99e5764d9db2b13d0dc1189bf8203d289b`  
		Last Modified: Tue, 12 Dec 2017 21:06:47 GMT  
		Size: 50.9 MB (50882486 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a20452f83e704c3737bc38610443b6ca94edbe5388fb654b5c4c3c4308150785`  
		Last Modified: Tue, 12 Dec 2017 23:07:02 GMT  
		Size: 18.7 MB (18656894 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85b1e0d12986adcbf53895fa51052184e9f935a6424e8665bfad080be921ffec`  
		Last Modified: Tue, 12 Dec 2017 23:07:28 GMT  
		Size: 41.1 MB (41102373 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4cdf6837da824b0da53d8ca5192f0f4200d0561a1d898a1ba5010f2f5c6d008`  
		Last Modified: Tue, 12 Dec 2017 23:49:48 GMT  
		Size: 822.0 KB (821969 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94172d5fae8ea40f3da6804199d95461aa7fa1207c5d05eae940259689ad8f56`  
		Last Modified: Tue, 12 Dec 2017 23:49:48 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ffe7bddd6ae7af55bbe4b32462af65743001984925d14c1417440dfb988cf03`  
		Last Modified: Tue, 12 Dec 2017 23:49:48 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:041d3dd7f2bf75b291889487662c85a39dd595d875ef70e788cdc9ff395a75c6`  
		Last Modified: Tue, 12 Dec 2017 23:50:14 GMT  
		Size: 104.4 MB (104448131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:7-jessie` - linux; arm variant v7

```console
$ docker pull openjdk@sha256:3c7cad300a3fa808f1bd9c3da9f9a1db1e9c744bd3905858c5134b5ee2c70f54
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **220.4 MB (220389327 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:43ce497ed75b9e76f6cec0af70ca3ced7f367384f35c794e54d517d9df1cb88e`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 13:27:05 GMT
ADD file:aeb57f3a84dc1b93e1d38a80409a407df553344149d5070ed79b656865c90c54 in / 
# Tue, 12 Dec 2017 13:27:06 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 14:14:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 14:14:11 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 14:15:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:06:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:06:51 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 15:06:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 15:06:53 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 15:06:54 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Dec 2017 15:06:54 GMT
ENV JAVA_VERSION=7u151
# Tue, 12 Dec 2017 15:06:54 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Tue, 12 Dec 2017 15:08:03 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:95e140a16c792899abc97cadee0138064dd21346fe51aa332ca4cbbd5563383c`  
		Last Modified: Tue, 12 Dec 2017 13:38:47 GMT  
		Size: 48.7 MB (48691755 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:237499cbbf2c5155fadc128c997700f0c5ec6355ba9704d0ec3f81c29640c9c4`  
		Last Modified: Tue, 12 Dec 2017 14:30:53 GMT  
		Size: 18.3 MB (18265038 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72f718f16c2f9a8213b99fcb49e72dad0036d1426f09c089f1e389b684f26520`  
		Last Modified: Tue, 12 Dec 2017 14:31:23 GMT  
		Size: 39.7 MB (39727713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e763e57fa4c7dcac24b9824a739665cadc1033634a31aadcdb97019c237959a`  
		Last Modified: Tue, 12 Dec 2017 15:29:47 GMT  
		Size: 795.9 KB (795894 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9f5f58f36529073b10509efe37d72d188ffbacfe8bff1ce2e61949cb0f3e67a`  
		Last Modified: Tue, 12 Dec 2017 15:29:47 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:509fe40dc27375b1ffd2891887f60815690d14e583b893309934f2f4359c822e`  
		Last Modified: Tue, 12 Dec 2017 15:29:48 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:870bdac7b4785c0c153cc42262dd9c4172211418ac9e44a6bee16aeb0dab9a80`  
		Last Modified: Tue, 12 Dec 2017 15:30:08 GMT  
		Size: 112.9 MB (112908551 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:7-jessie` - linux; 386

```console
$ docker pull openjdk@sha256:2809d4f36e1e52c158a297a262a76815029fea0b9f8eee0df19f4bc3669f8185
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.3 MB (259290880 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:79babfbed2952b88e331b2fa039a5a14a8d9b5f6660797741d8cf75d4d458377`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 14:19:55 GMT
ADD file:235a40e05b677eb2ae7e7a3cc5cbb0cda242ff15dddb87cb8dc9bb0cd2d6aed8 in / 
# Tue, 12 Dec 2017 14:19:55 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 16:53:52 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 16:53:53 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 16:54:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 18:22:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 18:22:23 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 18:22:24 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 18:22:25 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 18:22:25 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Dec 2017 18:22:25 GMT
ENV JAVA_VERSION=7u151
# Tue, 12 Dec 2017 18:22:25 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Tue, 12 Dec 2017 18:24:03 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:d99577c7ee3d4d82987bedaeb10f3244ff7e19e41c5259bb8cac00568d1c4271`  
		Last Modified: Tue, 12 Dec 2017 14:46:26 GMT  
		Size: 52.8 MB (52777369 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d94aafa6d6f35f82e1fdc93cd4f7f6ab829f6297c8defaaa911dfb2de063bf3d`  
		Last Modified: Tue, 12 Dec 2017 17:27:39 GMT  
		Size: 21.6 MB (21596374 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ddd19391b0ebd36e15e21cb3a6728c5950937634b9c81ecc7e3d1422b1dc25eb`  
		Last Modified: Tue, 12 Dec 2017 17:28:18 GMT  
		Size: 43.9 MB (43918299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31d0ca68cef4e1739c8fbf83f6b26c51cd048e91bbe967fa4d0d37227c8a6b64`  
		Last Modified: Tue, 12 Dec 2017 19:27:34 GMT  
		Size: 831.6 KB (831634 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d1bd24bd2b412e24f2eeeff5306d1ea3af1346a28a41716fd1c4b03342cdc3b`  
		Last Modified: Tue, 12 Dec 2017 19:27:33 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2234134c5bab8e5e8b2b1b1dfb34473ecad7fd48098d4ab538a228e7d74047f7`  
		Last Modified: Tue, 12 Dec 2017 19:27:34 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d034ae42e3dec51cbfb1bd59dbf7706eabe4922b928ded2b8661ed79e1c4df2`  
		Last Modified: Tue, 12 Dec 2017 19:28:06 GMT  
		Size: 140.2 MB (140166825 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:7-jessie` - linux; ppc64le

```console
$ docker pull openjdk@sha256:1c7e5de1acf34c8a151f8144394c84bb6d8f8e16b9fb21978ccb9501d97e30f0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **220.6 MB (220641420 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9dd6ed0a24b8e91e785d073f3ffbc8ab24388f701d3207a345d979369969bf2d`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 01:32:54 GMT
ADD file:a66da0d75afce2da6174648a861b98f8e9999028d4f04a59288ca92a090256e2 in / 
# Tue, 12 Dec 2017 01:32:56 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 02:52:01 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 02:52:05 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 02:55:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 06:12:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 06:12:14 GMT
ENV LANG=C.UTF-8
# Fri, 15 Dec 2017 06:12:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 15 Dec 2017 06:12:24 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Fri, 15 Dec 2017 06:12:25 GMT
ENV JAVA_HOME=/docker-java-home
# Fri, 15 Dec 2017 06:12:27 GMT
ENV JAVA_VERSION=7u151
# Fri, 15 Dec 2017 06:12:30 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Fri, 15 Dec 2017 06:19:29 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:75c28926027fc0404a0d21450475473243a59e8fc55443a62d1d744693ec19e9`  
		Last Modified: Tue, 12 Dec 2017 01:38:17 GMT  
		Size: 51.8 MB (51808999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6994e7d2dd732e57cd3bac94b995dab8a2711f30cf738f70bd4730a512f403ca`  
		Last Modified: Tue, 12 Dec 2017 03:53:30 GMT  
		Size: 19.2 MB (19202627 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb98bd09f482269961d36e59c72c340d0f8f4ba6d9efc5f96665114b216aa443`  
		Last Modified: Tue, 12 Dec 2017 03:53:39 GMT  
		Size: 42.8 MB (42758719 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33e7ba61182add9a8b86f014c521fc173c033eb160228f430f9e2f342b0c61de`  
		Last Modified: Fri, 15 Dec 2017 06:46:25 GMT  
		Size: 824.7 KB (824667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:358aa08ee7001def43c5f7a12654660280d69a975a30949d5366bc6a979cbece`  
		Last Modified: Fri, 15 Dec 2017 06:46:24 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01214b270fd10c2c321cdf0610e1243f63fb617091ca668d71952172a157b215`  
		Last Modified: Fri, 15 Dec 2017 06:46:24 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb508f41ed7e4ec7e2dccb90a5754b4371f1211c4331ebdb2693183215aeca26`  
		Last Modified: Fri, 15 Dec 2017 06:46:47 GMT  
		Size: 106.0 MB (106046029 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:7-jessie` - linux; s390x

```console
$ docker pull openjdk@sha256:8cdd7a8ee2b7456ebe0ce0439e2489f33371b7081209236b3e72197927218a8a
```

-	Docker Version: 17.06.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **221.5 MB (221543472 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e3094fdacdf624809dda7e5a800d8c6495681f68fa9795c485aa1df73f4bffb7`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 12 Dec 2017 06:22:40 GMT
ADD file:f85dc45c68f6f29cc10d6ef236674dedc10522f11b6fa2e8a6b10a4409ca0bc7 in / 
# Tue, 12 Dec 2017 06:22:40 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 06:53:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 06:53:37 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 06:54:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:35:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:35:04 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 07:35:05 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 07:35:05 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 07:35:05 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Dec 2017 07:35:06 GMT
ENV JAVA_VERSION=7u151
# Tue, 12 Dec 2017 07:35:06 GMT
ENV JAVA_DEBIAN_VERSION=7u151-2.6.11-2~deb8u1
# Tue, 12 Dec 2017 07:35:56 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:98cfcbfa76c6d2a42223dc7a44505bdd260000bffd3ecbb983cb33213128499b`  
		Last Modified: Tue, 12 Dec 2017 06:28:05 GMT  
		Size: 52.8 MB (52790322 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5a54c25ad661f258cad7c32f6c27f8a2ff7d463df9cbd8752d4ec4b8b2d8bfd`  
		Last Modified: Tue, 12 Dec 2017 07:02:50 GMT  
		Size: 19.5 MB (19471919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18e5f78145fbef3e222ea15ef8dd488c43ed84acd1a4cf20968bd87c6831b703`  
		Last Modified: Tue, 12 Dec 2017 07:03:23 GMT  
		Size: 43.4 MB (43389257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:032bd978131e74363834353ddcdd2ad901a8c5f29e94703bb79bb9f5a3eb0413`  
		Last Modified: Tue, 12 Dec 2017 07:46:00 GMT  
		Size: 838.0 KB (837959 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5af3f20dc6269ce5a4ff7cf2f8067dc1349b7ad909fed6e61c130823689b3c3`  
		Last Modified: Tue, 12 Dec 2017 07:45:59 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03e69b5657346b14454db06ce6e759e2d65448f85d825f285440a1614fbaa95e`  
		Last Modified: Tue, 12 Dec 2017 07:45:59 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dd17a5c70552f63f5f7107079f11fdb66f536e28a3b0b8f13c17d814e7bfa40c`  
		Last Modified: Tue, 12 Dec 2017 07:46:13 GMT  
		Size: 105.1 MB (105053636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
