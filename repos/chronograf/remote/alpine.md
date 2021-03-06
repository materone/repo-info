## `chronograf:alpine`

```console
$ docker pull chronograf@sha256:5ec841b153435eb846a5d57ea82fb03cd4b918b18ceaee3f503ed2c315daf6e6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `chronograf:alpine` - linux; amd64

```console
$ docker pull chronograf@sha256:fb1150fcca38b4793a02a4f51f53430a20828fe8df9882d19a42ce4599f2694f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **8.9 MB (8864996 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dc8a2124d244046a1dc011d774fa985fa5d18f2f67038709b52f31ccbee99f19`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Fri, 01 Dec 2017 18:46:26 GMT
ADD file:cb381165dec3689cf77e902c07ea78ca4da6bce4f5ac1909eebd40dba3273bfe in / 
# Fri, 01 Dec 2017 18:46:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Dec 2017 19:57:11 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Fri, 01 Dec 2017 19:57:15 GMT
RUN apk add --no-cache ca-certificates &&     update-ca-certificates
# Wed, 03 Jan 2018 00:16:36 GMT
ENV CHRONOGRAF_VERSION=1.4.0.0
# Wed, 03 Jan 2018 00:16:43 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/chronograf/releases/chronograf-${CHRONOGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/chronograf/releases/chronograf-${CHRONOGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify chronograf-${CHRONOGRAF_VERSION}-static_linux_amd64.tar.gz.asc chronograf-${CHRONOGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src &&     tar -C /usr/src -xzf chronograf-${CHRONOGRAF_VERSION}-static_linux_amd64.tar.gz &&     rm -f /usr/src/chronograf-*/chronograf.conf &&     chmod +x /usr/src/chronograf-*/* &&     cp -a /usr/src/chronograf-*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Wed, 03 Jan 2018 00:16:43 GMT
COPY file:bb4b392707bfb4ca737581b240f672796f5744c7220fea711a5d1f669992b912 in /usr/share/chronograf/LICENSE 
# Wed, 03 Jan 2018 00:16:44 GMT
COPY file:8cfc239e035af78ba9337d25f99200091e0d054985fe0c87e60b767d7759d99d in /usr/share/chronograf/agpl-3.0.md 
# Wed, 03 Jan 2018 00:16:44 GMT
EXPOSE 8888/tcp
# Wed, 03 Jan 2018 00:16:44 GMT
VOLUME [/var/lib/chronograf]
# Wed, 03 Jan 2018 00:16:45 GMT
COPY file:70420cc587871e64a3833c5e0724565624ad66205b4febab38c9c37f93a25e28 in /entrypoint.sh 
# Wed, 03 Jan 2018 00:16:45 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 03 Jan 2018 00:16:45 GMT
CMD ["chronograf"]
```

-	Layers:
	-	`sha256:1160f4abea84cbe2f316db6306839d2704f09a04af763ee493dd92cb066c0865`  
		Last Modified: Fri, 01 Dec 2017 18:50:17 GMT  
		Size: 2.0 MB (1991501 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93ff176d481367411591b2d81a3bb7bc2d2e2c76822d5ad20ff82628dbc61c69`  
		Last Modified: Fri, 01 Dec 2017 19:57:47 GMT  
		Size: 155.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0e711ab050183d8f8013c0aff7397f33117cde2345b501427ac61b511282d00`  
		Last Modified: Fri, 01 Dec 2017 19:57:45 GMT  
		Size: 351.0 KB (351003 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dd5b81e5149b6a2ff39b593569d5e29d413920377f2a3f5950f3cfa364e827c8`  
		Last Modified: Wed, 03 Jan 2018 00:17:50 GMT  
		Size: 6.5 MB (6497964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85828987bb1240f20e3be57eab6537bba896f2ad59d34c45659b51c3d11ab9f8`  
		Last Modified: Wed, 03 Jan 2018 00:17:48 GMT  
		Size: 12.2 KB (12238 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0be61595a5d9d2a47d5617e95b48b3e8170e593724786ad65c923d6230047ab`  
		Last Modified: Wed, 03 Jan 2018 00:17:48 GMT  
		Size: 11.9 KB (11898 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baadeef21d3f8bbc08c27c7345e4038d34e19a257b03ae0a3870b0235e18e45d`  
		Last Modified: Wed, 03 Jan 2018 00:17:49 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
