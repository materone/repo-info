## `maven:3-ibmjava-9`

```console
$ docker pull maven@sha256:d8531a31bc96a95d151698374b6adcc507e8bcb6605c208c7d035ded4e90bb94
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `maven:3-ibmjava-9` - linux; amd64

```console
$ docker pull maven@sha256:ed6eb716169d8f4a9c9c29c8ba344eaf7f4d4cb4698148b7f24b1021d4316a29
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **360.0 MB (359989967 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1130082dcca7933bf5589d37e787a0d508cbb82bccd48848ee34203799c50004`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Thu, 14 Dec 2017 20:59:45 GMT
ADD file:f5a2d04c3f3cafada15eb32e4e8d971e48ef11724939c399a8664bf498111e67 in / 
# Thu, 14 Dec 2017 20:59:46 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 14 Dec 2017 20:59:46 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 20:59:47 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 14 Dec 2017 20:59:48 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 14 Dec 2017 20:59:48 GMT
CMD ["/bin/bash"]
# Thu, 14 Dec 2017 21:53:38 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Thu, 14 Dec 2017 21:53:49 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Thu, 14 Dec 2017 21:56:28 GMT
ENV JAVA_VERSION=1.9.0_ea2
# Thu, 14 Dec 2017 21:57:34 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='0fe3712b54a93695cf4948d9ae171bf5cef038c0e41b364b4e9eb7cb80a60688';          YML_FILE='sdk/linux/x86_64/index.yml';          ;;        i386)          ESUM='5add39cc5ca56b97cf8ce71b9e1a15d19d36864aaed1e0296f50355ba3f34bd5';          YML_FILE='sdk/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='3c0dda9f449a667d12fe5f59a1ec059a90a9dc483fd35eef5ff53dd8b096cdf5';          YML_FILE='sdk/linux/ppc64le/index.yml';          ;;        s390)          ESUM='8d06af57d8236839f5c403c12dcf4c89e22dd91716a4d26b85c8d92f6d1e2e8b';          YML_FILE='sdk/linux/s390/index.yml';          ;;        s390x)          ESUM='6e823afa1df83e364381f827f4244bfe29b0ddd58ef0203eb60df9b8c0d123af';          YML_FILE='sdk/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(cat /tmp/index.yml | sed -n '/'${JAVA_VERSION}'/{n;p}' | sed -n 's/\s*uri:\s//p' | tr -d '\r');     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Thu, 14 Dec 2017 21:59:51 GMT
ENV JAVA_HOME=/opt/ibm/java PATH=/opt/ibm/java/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 14 Dec 2017 23:06:12 GMT
ARG MAVEN_VERSION=3.5.2
# Thu, 14 Dec 2017 23:06:13 GMT
ARG USER_HOME_DIR=/root
# Thu, 14 Dec 2017 23:06:13 GMT
ARG SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff
# Thu, 14 Dec 2017 23:06:13 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries
# Thu, 14 Dec 2017 23:06:24 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries MAVEN_VERSION=3.5.2 SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff USER_HOME_DIR=/root
RUN apt-get update && apt-get install -y curl   && mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 14 Dec 2017 23:06:24 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 14 Dec 2017 23:06:24 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 14 Dec 2017 23:06:52 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 14 Dec 2017 23:06:53 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 14 Dec 2017 23:06:53 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 14 Dec 2017 23:06:53 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:50aff78429b146489e8a6cb9334d93a6d81d5de2edc4fbf5e2d4d9253625753e`  
		Last Modified: Sun, 03 Dec 2017 11:19:40 GMT  
		Size: 42.7 MB (42743207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6d82e297bce031a3de1fa8c1587535e34579abce09a61e37f5a225a8667422f`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:275abb2c8a6f1ce8e67a388a11f3cc014e98b36ff993a6ed1cc7cd6ecb4dd61b`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 621.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f15a39356d6fc1df0a77012bf1aa2150b683e46be39d1c51bc7a320f913e322`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc0342a94c89e477c821328ccb542e6fb86ce4ef4ebbf1098e85669e051ef0dd`  
		Last Modified: Thu, 14 Dec 2017 21:01:57 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d523a11d2e4b94f1037f230c7a6766d7e6edf07bba2b2e2a801253adf579ba1`  
		Last Modified: Thu, 14 Dec 2017 22:00:49 GMT  
		Size: 3.0 MB (3020983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7621a0c34a6bd49e121d1b418db2f5d00d47426e6757fc91c5954d5d245c3f28`  
		Last Modified: Thu, 14 Dec 2017 22:05:07 GMT  
		Size: 271.6 MB (271634471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:434afe263c1a5ca75df2be78ae3ec430353525a9a9a3b9bd54f354c09a5d4d89`  
		Last Modified: Thu, 14 Dec 2017 23:07:49 GMT  
		Size: 42.6 MB (42587711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0ce8b6c6420a3539ad85f61a212681139965ae6447e59538230910099132656`  
		Last Modified: Thu, 14 Dec 2017 23:09:05 GMT  
		Size: 740.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b776bddf2da17800a13b2a1bc20d4f143a63dcb2afc74bed81522c51cd6fe2fa`  
		Last Modified: Thu, 14 Dec 2017 23:09:05 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-ibmjava-9` - linux; 386

```console
$ docker pull maven@sha256:15ccdf66ac00c01abee7b173b7bbfe25dd89a487fa859dbd46bcc67e81d60162
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **341.4 MB (341442568 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8c9a4d80b9931da232b087eed2fe957c4a3694cabc68aefac911d4b71f73b8a8`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Fri, 15 Dec 2017 04:49:36 GMT
ADD file:db6281c0035641aa2735fb58b607c51543c5d7c489f464561d4735774b0d8ca7 in / 
# Fri, 15 Dec 2017 04:49:37 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 15 Dec 2017 04:49:37 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 04:49:38 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 15 Dec 2017 04:49:39 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 15 Dec 2017 04:49:39 GMT
CMD ["/bin/bash"]
# Fri, 15 Dec 2017 05:16:35 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Fri, 15 Dec 2017 05:16:48 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 05:36:07 GMT
ENV JAVA_VERSION=1.9.0_ea2
# Fri, 15 Dec 2017 05:37:41 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='0fe3712b54a93695cf4948d9ae171bf5cef038c0e41b364b4e9eb7cb80a60688';          YML_FILE='sdk/linux/x86_64/index.yml';          ;;        i386)          ESUM='5add39cc5ca56b97cf8ce71b9e1a15d19d36864aaed1e0296f50355ba3f34bd5';          YML_FILE='sdk/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='3c0dda9f449a667d12fe5f59a1ec059a90a9dc483fd35eef5ff53dd8b096cdf5';          YML_FILE='sdk/linux/ppc64le/index.yml';          ;;        s390)          ESUM='8d06af57d8236839f5c403c12dcf4c89e22dd91716a4d26b85c8d92f6d1e2e8b';          YML_FILE='sdk/linux/s390/index.yml';          ;;        s390x)          ESUM='6e823afa1df83e364381f827f4244bfe29b0ddd58ef0203eb60df9b8c0d123af';          YML_FILE='sdk/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(cat /tmp/index.yml | sed -n '/'${JAVA_VERSION}'/{n;p}' | sed -n 's/\s*uri:\s//p' | tr -d '\r');     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Fri, 15 Dec 2017 05:47:39 GMT
ENV JAVA_HOME=/opt/ibm/java PATH=/opt/ibm/java/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 15 Dec 2017 06:30:45 GMT
ARG MAVEN_VERSION=3.5.2
# Fri, 15 Dec 2017 06:30:45 GMT
ARG USER_HOME_DIR=/root
# Fri, 15 Dec 2017 06:30:45 GMT
ARG SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff
# Fri, 15 Dec 2017 06:30:46 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries
# Fri, 15 Dec 2017 06:32:12 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries MAVEN_VERSION=3.5.2 SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff USER_HOME_DIR=/root
RUN apt-get update && apt-get install -y curl   && mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Fri, 15 Dec 2017 06:32:12 GMT
ENV MAVEN_HOME=/usr/share/maven
# Fri, 15 Dec 2017 06:32:13 GMT
ENV MAVEN_CONFIG=/root/.m2
# Fri, 15 Dec 2017 06:33:00 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Fri, 15 Dec 2017 06:33:00 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Fri, 15 Dec 2017 06:33:00 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Fri, 15 Dec 2017 06:33:00 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:aef6d0613937d52d60f194bc25f0ac7e33110ffe2240d0da27f0ca61e29312d4`  
		Last Modified: Fri, 15 Dec 2017 04:57:51 GMT  
		Size: 43.1 MB (43097644 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83de9eba49f17ed49396ef3339ee48947df3f6a970585c7ee9aae96406e8ea89`  
		Last Modified: Fri, 15 Dec 2017 04:57:38 GMT  
		Size: 848.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9087439057e1695a8ce4cd54750e754c9681383dc3afb06a11f59987fcba7f80`  
		Last Modified: Fri, 15 Dec 2017 04:57:38 GMT  
		Size: 584.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45d36c0ac9f9f11a3ae5dbd35a2b9d9c319f3a97fe6300fb377e3f77ee896746`  
		Last Modified: Fri, 15 Dec 2017 04:57:39 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e991b5792ff6c2f669fc3211eaa3ed9cc1f936ad1c2741182fd8b60ee81fe158`  
		Last Modified: Fri, 15 Dec 2017 04:57:38 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e6b7878d4483aec967fa598fe350c7960f5e143008cd2f9a5595dab4ef91837`  
		Last Modified: Fri, 15 Dec 2017 05:48:28 GMT  
		Size: 2.9 MB (2877127 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c505c542eb8c22a6d94bbcda4bd271a5224b3541a27e12022e9b46fce4bdf07`  
		Last Modified: Fri, 15 Dec 2017 05:59:19 GMT  
		Size: 251.5 MB (251467992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed3ec6ab3305be1d60d48b0c736696853e21fceb4047120e538ec81031a7ea2d`  
		Last Modified: Fri, 15 Dec 2017 06:34:08 GMT  
		Size: 44.0 MB (43996249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a95748fa059de9ce4ae69afc3fed002f605ecc4cea570ec95e1df0257a43d0c`  
		Last Modified: Fri, 15 Dec 2017 06:35:26 GMT  
		Size: 741.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:def9ad8918c245f4805d865457005c2962339e3a44b241a0ec67904c24c500be`  
		Last Modified: Fri, 15 Dec 2017 06:35:26 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-ibmjava-9` - linux; ppc64le

```console
$ docker pull maven@sha256:95b6d0dabf4015656b2c64791b74ff726a29c3ccb5c15ec5536f9a9f52b3e204
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **381.6 MB (381643709 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fe63cc74135651b5177fc902bf5351c1b836e6dc0531449680a90af9d571772e`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Fri, 15 Dec 2017 03:41:58 GMT
ADD file:d36796d61133bdf450effb63948c6fb33d8ef17a91b33113fadfdd210a29d225 in / 
# Fri, 15 Dec 2017 03:42:02 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 15 Dec 2017 03:42:11 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 03:42:15 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 15 Dec 2017 03:42:19 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 15 Dec 2017 03:42:20 GMT
CMD ["/bin/bash"]
# Fri, 15 Dec 2017 04:01:13 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Fri, 15 Dec 2017 04:01:58 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Fri, 15 Dec 2017 04:09:50 GMT
ENV JAVA_VERSION=1.9.0_ea2
# Fri, 15 Dec 2017 04:18:33 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='0fe3712b54a93695cf4948d9ae171bf5cef038c0e41b364b4e9eb7cb80a60688';          YML_FILE='sdk/linux/x86_64/index.yml';          ;;        i386)          ESUM='5add39cc5ca56b97cf8ce71b9e1a15d19d36864aaed1e0296f50355ba3f34bd5';          YML_FILE='sdk/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='3c0dda9f449a667d12fe5f59a1ec059a90a9dc483fd35eef5ff53dd8b096cdf5';          YML_FILE='sdk/linux/ppc64le/index.yml';          ;;        s390)          ESUM='8d06af57d8236839f5c403c12dcf4c89e22dd91716a4d26b85c8d92f6d1e2e8b';          YML_FILE='sdk/linux/s390/index.yml';          ;;        s390x)          ESUM='6e823afa1df83e364381f827f4244bfe29b0ddd58ef0203eb60df9b8c0d123af';          YML_FILE='sdk/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(cat /tmp/index.yml | sed -n '/'${JAVA_VERSION}'/{n;p}' | sed -n 's/\s*uri:\s//p' | tr -d '\r');     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Fri, 15 Dec 2017 04:18:39 GMT
ENV JAVA_HOME=/opt/ibm/java PATH=/opt/ibm/java/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 15 Dec 2017 04:43:37 GMT
ARG MAVEN_VERSION=3.5.2
# Fri, 15 Dec 2017 04:43:40 GMT
ARG USER_HOME_DIR=/root
# Fri, 15 Dec 2017 04:43:45 GMT
ARG SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff
# Fri, 15 Dec 2017 04:43:47 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries
# Fri, 15 Dec 2017 04:46:41 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries MAVEN_VERSION=3.5.2 SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff USER_HOME_DIR=/root
RUN apt-get update && apt-get install -y curl   && mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Fri, 15 Dec 2017 04:46:44 GMT
ENV MAVEN_HOME=/usr/share/maven
# Fri, 15 Dec 2017 04:46:48 GMT
ENV MAVEN_CONFIG=/root/.m2
# Fri, 15 Dec 2017 04:48:28 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Fri, 15 Dec 2017 04:48:32 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Fri, 15 Dec 2017 04:48:36 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Fri, 15 Dec 2017 04:48:39 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:586a07d977d9891f197122f365df967649e26ee09657cb0824e7245080ebf62d`  
		Last Modified: Fri, 15 Dec 2017 03:44:27 GMT  
		Size: 45.2 MB (45208592 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2bf911559ec0ea1563afc47ba82a8c1b83545bae3749f9958ee937748a7fc99c`  
		Last Modified: Fri, 15 Dec 2017 03:44:15 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48999c060756be3aa70909a36813a48ab5661a4ca3b7563f76fe78913f5a9f88`  
		Last Modified: Fri, 15 Dec 2017 03:44:15 GMT  
		Size: 646.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa5e5494889f3c21fd44b4939663dbede3397e8ec024fd280d15cd4ca8b19796`  
		Last Modified: Fri, 15 Dec 2017 03:44:15 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3bd4f80d03d3a8858dff9c2464ff8ad31b15f8097b10833d3066d4256771c625`  
		Last Modified: Fri, 15 Dec 2017 03:44:15 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4ac2d58c37076040ee62ec5ea5b04c7262f59e28bbe6d1dcc3570407427c45`  
		Last Modified: Fri, 15 Dec 2017 04:19:04 GMT  
		Size: 2.9 MB (2878165 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91cc6fb618095bdf5bd8ab8fd8108b6b8496ba936bb5e18155ae7e18b4793961`  
		Last Modified: Fri, 15 Dec 2017 04:21:32 GMT  
		Size: 292.0 MB (291957695 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df750fb5891079a5db8d0cad0544f8403005ac1183b7baa0e355a511956748b9`  
		Last Modified: Fri, 15 Dec 2017 04:49:37 GMT  
		Size: 41.6 MB (41595636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bac475a24ddb1bac73bad9d10d3d07ff674672e7b84c1331c87ff7f50871fdf7`  
		Last Modified: Fri, 15 Dec 2017 04:50:15 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1927b12e61db0ce19e005b30383b16aed5b242e7de768b8c9aa465a644a50d02`  
		Last Modified: Fri, 15 Dec 2017 04:50:14 GMT  
		Size: 357.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-ibmjava-9` - linux; s390x

```console
$ docker pull maven@sha256:70e1b19b8f40630752579feb0f231ea16dc370b9089c8d1825fd1367d52931f9
```

-	Docker Version: 17.06.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **359.3 MB (359332501 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:10340166dc532ce65de81383471e2ffb1bf9f5c8854c6bc91838d3aa17d3cf6c`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sun, 07 Jan 2018 06:21:35 GMT
ADD file:11ba80bf6d29755a179a3aec11ff1cedac56856e058e8bc473bae7c772373af3 in / 
# Sun, 07 Jan 2018 06:21:36 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Sun, 07 Jan 2018 06:21:37 GMT
RUN rm -rf /var/lib/apt/lists/*
# Sun, 07 Jan 2018 06:21:37 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Sun, 07 Jan 2018 06:21:38 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Sun, 07 Jan 2018 06:21:38 GMT
CMD ["/bin/bash"]
# Sun, 07 Jan 2018 09:45:14 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Sun, 07 Jan 2018 09:45:22 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Sun, 07 Jan 2018 09:47:45 GMT
ENV JAVA_VERSION=1.9.0_ea2
# Sun, 07 Jan 2018 09:49:14 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='0fe3712b54a93695cf4948d9ae171bf5cef038c0e41b364b4e9eb7cb80a60688';          YML_FILE='sdk/linux/x86_64/index.yml';          ;;        i386)          ESUM='5add39cc5ca56b97cf8ce71b9e1a15d19d36864aaed1e0296f50355ba3f34bd5';          YML_FILE='sdk/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='3c0dda9f449a667d12fe5f59a1ec059a90a9dc483fd35eef5ff53dd8b096cdf5';          YML_FILE='sdk/linux/ppc64le/index.yml';          ;;        s390)          ESUM='8d06af57d8236839f5c403c12dcf4c89e22dd91716a4d26b85c8d92f6d1e2e8b';          YML_FILE='sdk/linux/s390/index.yml';          ;;        s390x)          ESUM='6e823afa1df83e364381f827f4244bfe29b0ddd58ef0203eb60df9b8c0d123af';          YML_FILE='sdk/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(cat /tmp/index.yml | sed -n '/'${JAVA_VERSION}'/{n;p}' | sed -n 's/\s*uri:\s//p' | tr -d '\r');     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Sun, 07 Jan 2018 09:49:14 GMT
ENV JAVA_HOME=/opt/ibm/java PATH=/opt/ibm/java/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sun, 07 Jan 2018 12:17:02 GMT
ARG MAVEN_VERSION=3.5.2
# Sun, 07 Jan 2018 12:17:02 GMT
ARG USER_HOME_DIR=/root
# Sun, 07 Jan 2018 12:17:02 GMT
ARG SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff
# Sun, 07 Jan 2018 12:17:02 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries
# Sun, 07 Jan 2018 12:17:12 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.2/binaries MAVEN_VERSION=3.5.2 SHA=707b1f6e390a65bde4af4cdaf2a24d45fc19a6ded00fff02e91626e3e42ceaff USER_HOME_DIR=/root
RUN apt-get update && apt-get install -y curl   && mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sun, 07 Jan 2018 12:17:12 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sun, 07 Jan 2018 12:17:13 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sun, 07 Jan 2018 12:18:10 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sun, 07 Jan 2018 12:18:10 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sun, 07 Jan 2018 12:18:11 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sun, 07 Jan 2018 12:18:11 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:dde4bd472ee5cfdfe0c36c4cabc9d57a4e904ff57cb4c0dd5da1a57da17fcd9c`  
		Last Modified: Sun, 07 Jan 2018 06:22:48 GMT  
		Size: 41.9 MB (41877572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bb275b8c445d96375f170f1921a0fc14d67bcf0a539f688a0fe685876e96d74`  
		Last Modified: Sun, 07 Jan 2018 06:22:41 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aac1ba7e93438f17ca3ccf8c3954f1773e07a36a84e4080c86cf14673aa31154`  
		Last Modified: Sun, 07 Jan 2018 06:22:41 GMT  
		Size: 617.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5062c5559d3c8a48dbc8e839a8909ec2ca84ec3e4b3554d39f46d14ac85e145`  
		Last Modified: Sun, 07 Jan 2018 06:22:42 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b61e9907f78d856d8fed0dc9c5f74c932839788e1d2796f7be9a9f513fbcb88`  
		Last Modified: Sun, 07 Jan 2018 06:22:41 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d7e68c138d902782e890f7ce265e0367ef1093adecb96c51df30257c8da34f1`  
		Last Modified: Sun, 07 Jan 2018 09:49:41 GMT  
		Size: 2.8 MB (2765488 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f03f5f43748dd01ccc87b8b367d0a909d1e651155b147fd1c7616acf5262ab42`  
		Last Modified: Sun, 07 Jan 2018 09:51:34 GMT  
		Size: 274.7 MB (274684317 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6cff45905707cd881f4dfaed1df7936cbd8d1aabdc86d9fd01c6727587fa87b`  
		Last Modified: Sun, 07 Jan 2018 12:19:11 GMT  
		Size: 40.0 MB (40001536 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e57d13e1aade2ae7e29645b3cf6628557585a81b61b26e202ba095333084f7b1`  
		Last Modified: Sun, 07 Jan 2018 12:21:47 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4744c4442712c3912fe135bb394a225460766e11a311784acfffca70b0082969`  
		Last Modified: Sun, 07 Jan 2018 12:21:47 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
