## `traefik:cancoillotte`

```console
$ docker pull traefik@sha256:d7d43516529cff5b03bf9a2ae5564cca7aa9b27d5f415f7f567ffba8a41e3c16
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8

### `traefik:cancoillotte` - linux; amd64

```console
$ docker pull traefik@sha256:0cfc6bd95f93749e5fa52acafdcc0850a74a259d40405f132d56660ef5f03ec7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.0 MB (13958771 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:00f95bbafd3bd97596f43deeab8c215ac3eeb1ca300f63ccdaf175afab5bd0cb`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Fri, 03 Nov 2017 22:11:40 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Thu, 04 Jan 2018 17:59:48 GMT
COPY file:814db57f6caa786ab2ab7d1352639cd969586a97cc81ddacbc53036d12c38ac7 in / 
# Thu, 04 Jan 2018 17:59:48 GMT
EXPOSE 80/tcp
# Thu, 04 Jan 2018 17:59:48 GMT
ENTRYPOINT ["/traefik"]
# Thu, 04 Jan 2018 17:59:49 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.5.0-rc4 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:5d3835484afecc78dccfa2f7d4fcf273aacfe0c7600b957314e38488f3942045`  
		Last Modified: Fri, 03 Nov 2017 22:12:12 GMT  
		Size: 155.2 KB (155152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5966baca844a31e55f12a0193322fe9e9ea6a1d6a52c7ff40880551cf205f7cc`  
		Last Modified: Thu, 04 Jan 2018 18:01:19 GMT  
		Size: 13.8 MB (13803619 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `traefik:cancoillotte` - linux; arm variant v6

```console
$ docker pull traefik@sha256:d4aa04640aaeb606b2aee4419012798d373aa2c48612bf7ecd8a00fe97019e1b
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.1 MB (13094470 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:79ee548093c5c04be909152d5d84ece746a714e69011e214c154a76609fe274b`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Tue, 24 Oct 2017 23:48:27 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Fri, 05 Jan 2018 00:48:25 GMT
COPY file:e5aa52ff80288b659c2b132edca7e5ff093f49c0df891fa911c466b7deffd328 in / 
# Fri, 05 Jan 2018 00:48:25 GMT
EXPOSE 80/tcp
# Fri, 05 Jan 2018 00:48:26 GMT
ENTRYPOINT ["/traefik"]
# Fri, 05 Jan 2018 00:48:26 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.5.0-rc4 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:8996ab8c9ae2c6afe7d318a3784c7ba1b1b72d4ae14cf515d4c1490aae91cab0`  
		Last Modified: Tue, 24 Oct 2017 23:48:35 GMT  
		Size: 155.2 KB (155184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3664f7d1017ff81d773b629224d5ee2b263a65958ad61b6962b685e5d0f6e846`  
		Last Modified: Fri, 05 Jan 2018 00:48:56 GMT  
		Size: 12.9 MB (12939286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `traefik:cancoillotte` - linux; arm64 variant v8

```console
$ docker pull traefik@sha256:a2ea1bc20307477e3281fdcf86528c005487ca8c0db84f756789d1a6ada00525
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **12.8 MB (12761589 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d237239c694754765662ab8a448dc393e44663221f2543668cfd6668763ffb0c`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Wed, 25 Oct 2017 04:54:39 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Fri, 05 Jan 2018 05:54:39 GMT
COPY file:f188ffaa1598c2c1c78a6b292398de9a5881c101f0b6bb653a0d71d5f9e0eada in / 
# Fri, 05 Jan 2018 05:54:39 GMT
EXPOSE 80/tcp
# Fri, 05 Jan 2018 05:54:40 GMT
ENTRYPOINT ["/traefik"]
# Fri, 05 Jan 2018 05:54:41 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.5.0-rc4 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:78fe135ba97a13abc86dbe373975f0d0712d8aa6e540e09824b715a55d7e2ed3`  
		Last Modified: Wed, 25 Oct 2017 04:55:01 GMT  
		Size: 155.2 KB (155151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55dc9d7a1a51c35b0f9cedc44fe37c503c356287b2b227ca3f3fbe55b2368d68`  
		Last Modified: Fri, 05 Jan 2018 05:55:39 GMT  
		Size: 12.6 MB (12606438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
