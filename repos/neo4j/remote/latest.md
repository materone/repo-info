## `neo4j:latest`

```console
$ docker pull neo4j@sha256:baeb76f0d4785817c2a3608796ff0104a8f87ed89fe3391ef467eb6f0a1fc40e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `neo4j:latest` - linux; amd64

```console
$ docker pull neo4j@sha256:a828bedd0e45b65197e2f2e4150e89418f51a79960751c398d87638183f2c85c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **149.1 MB (149101568 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b70b7d1aeddb4d8f31ac561536c1fef1393169c3e9c8f016b79e2a93cfb21f74`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["neo4j"]`

```dockerfile
# Fri, 01 Dec 2017 18:48:48 GMT
ADD file:2b00f26f6004576e2f8faeb3fb0517a14f79ea89a059fe096b54cbecf5da512e in / 
# Fri, 01 Dec 2017 18:48:48 GMT
CMD ["/bin/sh"]
# Tue, 05 Dec 2017 03:42:44 GMT
ENV LANG=C.UTF-8
# Tue, 05 Dec 2017 03:42:45 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 05 Dec 2017 03:43:45 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Tue, 05 Dec 2017 03:43:46 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 05 Dec 2017 03:43:46 GMT
ENV JAVA_VERSION=8u151
# Tue, 05 Dec 2017 03:43:46 GMT
ENV JAVA_ALPINE_VERSION=8.151.12-r0
# Tue, 05 Dec 2017 03:43:51 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 05 Dec 2017 04:58:02 GMT
RUN apk add --no-cache --quiet     bash     curl
# Tue, 05 Dec 2017 04:58:07 GMT
ENV NEO4J_SHA256=0e5c6492cd274edf06c5f10d2b64711bd559aaff37c646e03bfa65e613994174 NEO4J_TARBALL=neo4j-community-3.3.1-unix.tar.gz NEO4J_EDITION=community
# Tue, 05 Dec 2017 04:58:07 GMT
ARG NEO4J_URI=http://dist.neo4j.org/neo4j-community-3.3.1-unix.tar.gz
# Tue, 05 Dec 2017 04:58:07 GMT
COPY file:2e411d607fa15f91ae6f4b515dde6bf3e158d34c0036556e00553ed1c50cd63d in /tmp/ 
# Tue, 05 Dec 2017 04:58:25 GMT
# ARGS: NEO4J_URI=http://dist.neo4j.org/neo4j-community-3.3.1-unix.tar.gz
RUN curl --fail --silent --show-error --location --remote-name ${NEO4J_URI}     && echo "${NEO4J_SHA256}  ${NEO4J_TARBALL}" | sha256sum -csw -     && tar --extract --file ${NEO4J_TARBALL} --directory /var/lib     && mv /var/lib/neo4j-* /var/lib/neo4j     && rm ${NEO4J_TARBALL}     && mv /var/lib/neo4j/data /data     && ln -s /data /var/lib/neo4j/data     && apk del curl
# Tue, 05 Dec 2017 04:58:25 GMT
ENV PATH=/var/lib/neo4j/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 05 Dec 2017 04:58:26 GMT
WORKDIR /var/lib/neo4j
# Tue, 05 Dec 2017 04:58:26 GMT
VOLUME [/data]
# Tue, 05 Dec 2017 04:58:26 GMT
COPY file:b1f08b121281604fe08edf206463959271aee1f21c800af2c0f2a52d70db0f3e in /docker-entrypoint.sh 
# Tue, 05 Dec 2017 04:58:27 GMT
EXPOSE 7473/tcp 7474/tcp 7687/tcp
# Tue, 05 Dec 2017 04:58:27 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 05 Dec 2017 04:58:27 GMT
CMD ["neo4j"]
```

-	Layers:
	-	`sha256:2fdfe1cd78c20d05774f0919be19bc1a3e4729bce219968e4188e7e0f1af679d`  
		Last Modified: Fri, 01 Dec 2017 18:50:32 GMT  
		Size: 2.1 MB (2064911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82630fd6e5ba7225587bd7986c7b6245801f8c7b001c9db318aecbb7fcb188a4`  
		Last Modified: Tue, 05 Dec 2017 03:44:19 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:119d364c885d49cacd5587d152fc93747a1758e1cfdd3d10d627c00091c5b365`  
		Last Modified: Tue, 05 Dec 2017 03:46:37 GMT  
		Size: 54.5 MB (54453882 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46f8fad107eeaa6f5d69afa710d251ad703ba209a6eca3e7d53ae59afc59ab83`  
		Last Modified: Tue, 05 Dec 2017 05:38:18 GMT  
		Size: 1.7 MB (1689198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe7f5c604f0491122c65e32c3959c9ef91b0a0eff4302fc62feda94f3817b7ff`  
		Last Modified: Tue, 05 Dec 2017 05:38:17 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd4ca7c99ff73d96780fa5037a4c63858f9fee531cae746119d5a74af22815b`  
		Last Modified: Tue, 05 Dec 2017 05:38:24 GMT  
		Size: 90.9 MB (90890931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d242a75fec77bc1cead2e8170515be5ee2c898e2a1ef3582f45dba2153812072`  
		Last Modified: Tue, 05 Dec 2017 05:38:17 GMT  
		Size: 2.3 KB (2276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
