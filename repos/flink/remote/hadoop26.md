## `flink:hadoop26`

```console
$ docker pull flink@sha256:d6ea79be5711130d4770def6b45e0cd4505ea1832f33311e52d05fd538e302be
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `flink:hadoop26` - linux; amd64

```console
$ docker pull flink@sha256:564ae4b0f943c25cb4f6c1e96b79a65b008727d8673a006174255a2f66d04e26
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **445.4 MB (445442596 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3ac878731d1f16e62267d08dc1a11aa641f52b8cde6922079a7f1938ad744a06`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 12 Dec 2017 01:44:20 GMT
ADD file:eb2519421c9794ccc99d483c07f59ba305531bc9b4dc294e74d2ddb7de69e52a in / 
# Tue, 12 Dec 2017 01:44:21 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:54:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:54:15 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 15:16:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 15:16:23 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 15:16:24 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 12 Dec 2017 15:16:25 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 12 Dec 2017 15:16:25 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Dec 2017 15:16:26 GMT
ENV JAVA_VERSION=8u151
# Tue, 12 Dec 2017 15:16:26 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Tue, 12 Dec 2017 15:16:26 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 12 Dec 2017 15:17:32 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Dec 2017 15:17:36 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 12 Dec 2017 17:39:39 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 17:39:39 GMT
ENV GOSU_VERSION=1.7
# Tue, 12 Dec 2017 17:40:47 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Fri, 15 Dec 2017 21:24:21 GMT
ENV FLINK_VERSION=1.4.0 HADOOP_VERSION=26 SCALA_VERSION=2.11
# Fri, 15 Dec 2017 21:24:21 GMT
ENV FLINK_HOME=/opt/flink
# Fri, 15 Dec 2017 21:24:22 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 15 Dec 2017 21:24:23 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Fri, 15 Dec 2017 21:24:24 GMT
WORKDIR /opt/flink
# Fri, 15 Dec 2017 21:24:24 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.4.0/flink-1.4.0-bin-hadoop26-scala_2.11.tgz
# Fri, 15 Dec 2017 21:24:24 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.4.0/flink-1.4.0-bin-hadoop26-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.4.0/flink-1.4.0-bin-hadoop26-scala_2.11.tgz.asc
# Fri, 15 Dec 2017 21:24:25 GMT
COPY file:1b3d6b0de4c8f155f3f310dea96670e1f8dcff77569e00e42b8942faa95df302 in /KEYS 
# Fri, 15 Dec 2017 21:24:51 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Fri, 15 Dec 2017 21:24:52 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Fri, 15 Dec 2017 21:24:52 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Fri, 15 Dec 2017 21:24:52 GMT
EXPOSE 6123/tcp 8081/tcp
# Fri, 15 Dec 2017 21:24:52 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:723254a2c089166d4bcfa917be0181ddbecd94971ebfe85792d96e7e29be9c68`  
		Last Modified: Tue, 12 Dec 2017 01:53:22 GMT  
		Size: 45.1 MB (45121631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abe15a44e12f84b4aac20d4f2b450ec8638cc0b176c9130d1802cb4fed17d953`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 11.1 MB (11107352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:409a28e3cc3de08700c9d37c809a6d3aa43dc076402943919f4a78c286c60a0b`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 4.3 MB (4335420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9511c68044accc89061e19e40356126f629c1e3ace2ef524b0e3f02e64e6b10`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 852.3 KB (852274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d1b16e30bc84a10c110be2c4f0a35dce542c7d55869cf2f99b7753763aabdb1`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fc5a09c924277c26642af87cc8a057633582a6fb462141245d46a638d0f8cf5`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d34976006493631a54114beee079e51dd165df33f8f5ebfc04b0eeb12613bedb`  
		Last Modified: Tue, 12 Dec 2017 16:20:31 GMT  
		Size: 165.4 MB (165393574 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b70003f0c1097e6b4f30f66e223ce759edec1331f5c1a4569e24ce8f4d41632`  
		Last Modified: Tue, 12 Dec 2017 16:19:57 GMT  
		Size: 272.2 KB (272151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:350fe52234882bd4ad4421df1b2192bbe485e858b2af55c96f19849c0782886b`  
		Last Modified: Tue, 12 Dec 2017 18:02:10 GMT  
		Size: 482.7 KB (482741 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09abbf854d924b48f240a053a4132ec48b129ac85279db22f36d9c391beaab5c`  
		Last Modified: Tue, 12 Dec 2017 18:02:10 GMT  
		Size: 819.2 KB (819180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:705c3614e22057df2fc829dbe0b9710f30e92b19f6d74abe7906b87fd30785cb`  
		Last Modified: Fri, 15 Dec 2017 21:38:16 GMT  
		Size: 4.6 KB (4647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7671c516d50dae3b485b28ceb177e78229e2f16f797c929a156bf689e4c0dba7`  
		Last Modified: Fri, 15 Dec 2017 21:38:16 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:460e8ab5be135b53517cbb56e0e2d4677bd64346a761902bc46ae3d9a601ca24`  
		Last Modified: Fri, 15 Dec 2017 21:38:16 GMT  
		Size: 54.7 KB (54699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04cd3ce52cf8f3800beaf4a65b95ff71f144c6dc42aecc97c5ac102d28d6311c`  
		Last Modified: Fri, 15 Dec 2017 21:38:38 GMT  
		Size: 217.0 MB (216997318 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147bfbe8e14bfccefb09582bfa1735f2db08d9ef0c818d1c3f7b52c8845c975e`  
		Last Modified: Fri, 15 Dec 2017 21:38:16 GMT  
		Size: 1.1 KB (1117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
