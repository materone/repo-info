## `pypy:3-slim`

```console
$ docker pull pypy@sha256:ed029650ca48b2ac0c43eb57c392dbd46d4ba4b2edfc7d891b30ee2ee82b8355
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; 386

### `pypy:3-slim` - linux; amd64

```console
$ docker pull pypy@sha256:15596afaf6b14d85e357cbb08d1df9bc4f416a7d4c380a965c72bca2bbea42e8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **66.4 MB (66429209 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9ce73fd24db503562b881ad74987270ff70a88f002d55097c2a8a3cc1b822ccf`
-	Default Command: `["pypy3"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:34 GMT
ADD file:e7ac45803c3ab9b7023933b75f5a88eda1f3edca97c7e462401860777cf312f7 in / 
# Tue, 12 Dec 2017 01:41:35 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 06:21:38 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Dec 2017 06:21:38 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 06:21:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Tue, 26 Dec 2017 20:08:50 GMT
ENV PYPY_VERSION=5.10.0
# Tue, 26 Dec 2017 20:08:50 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Tue, 26 Dec 2017 20:10:44 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) pypyArch='linux64'; sha256='aa4fb52fb858d973dd838dcf8d74f30705e5afdf1150acb8e056eb99353dfe77' ;; 		armel) pypyArch='linux-armel'; sha256='c2cc529befb3e1f2ef8bd4e96af4a823c52ef2d180b0b3bd87511c5b47d59210' ;; 		i386) pypyArch='linux32'; sha256='529bc3b11edbdcdd676d90c805b8f607f6eedd5f0ec457a31bbe09c03f5bebfe' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding PyPy $PYPY_VERSION binary release"; exit 1 ;; 	esac; 		fetchDeps=' 		bzip2 		wget 	'; 	apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/*; 		wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy3-v${PYPY_VERSION}-${pypyArch}.tar.bz2"; 	echo "$sha256 *pypy.tar.bz2" | sha256sum -c; 	tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2; 	rm pypy.tar.bz2; 		pypy3 --version; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		pypy3 get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		rm -f get-pip.py; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 26 Dec 2017 20:10:45 GMT
CMD ["pypy3"]
```

-	Layers:
	-	`sha256:c4bb02b17bb4b034c95a948c99c762cf0486a45f45441a052208d7750f1b413b`  
		Last Modified: Tue, 12 Dec 2017 01:48:52 GMT  
		Size: 30.1 MB (30114519 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13ed6d99248693c2acd5109ff75533464052952167eca48dbf989268a392ebb3`  
		Last Modified: Tue, 12 Dec 2017 06:28:04 GMT  
		Size: 2.9 MB (2859578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afc40ee7ab5b72d3c86d40fd176bb5b7b850b9927227250a15b2e538972214b3`  
		Last Modified: Tue, 26 Dec 2017 20:14:55 GMT  
		Size: 33.5 MB (33455112 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `pypy:3-slim` - linux; arm variant v5

```console
$ docker pull pypy@sha256:6fbad7cf0c183fb747507f6ac8791840c9b4b3e5d46ea1dcaf7124dd63657d5e
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.8 MB (62751974 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3f7f885215a3cc0441128c5fa481506a6d5799b9dc67ebed0a530becfc4d78ab`
-	Default Command: `["pypy3"]`

```dockerfile
# Tue, 12 Dec 2017 20:57:33 GMT
ADD file:29d0e44ebcc6f8dc2cfbc86c5034380677d263e9eec27a22ba045e0810836f81 in / 
# Tue, 12 Dec 2017 20:57:34 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 21:39:30 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Dec 2017 21:39:31 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 22:43:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Wed, 27 Dec 2017 17:09:11 GMT
ENV PYPY_VERSION=5.10.0
# Wed, 27 Dec 2017 17:09:11 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 27 Dec 2017 17:12:31 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) pypyArch='linux64'; sha256='aa4fb52fb858d973dd838dcf8d74f30705e5afdf1150acb8e056eb99353dfe77' ;; 		armel) pypyArch='linux-armel'; sha256='c2cc529befb3e1f2ef8bd4e96af4a823c52ef2d180b0b3bd87511c5b47d59210' ;; 		i386) pypyArch='linux32'; sha256='529bc3b11edbdcdd676d90c805b8f607f6eedd5f0ec457a31bbe09c03f5bebfe' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding PyPy $PYPY_VERSION binary release"; exit 1 ;; 	esac; 		fetchDeps=' 		bzip2 		wget 	'; 	apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/*; 		wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy3-v${PYPY_VERSION}-${pypyArch}.tar.bz2"; 	echo "$sha256 *pypy.tar.bz2" | sha256sum -c; 	tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2; 	rm pypy.tar.bz2; 		pypy3 --version; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		pypy3 get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		rm -f get-pip.py; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 27 Dec 2017 17:12:31 GMT
CMD ["pypy3"]
```

-	Layers:
	-	`sha256:51e696f556166d0e25b3b27c824c4aafbddd5adcfd3f5186c09707f7baa3b312`  
		Last Modified: Tue, 12 Dec 2017 21:07:41 GMT  
		Size: 28.4 MB (28423526 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa1e1f15069f149f59c18e22308fea3709837800f0d2954fbbc664799384ce6f`  
		Last Modified: Tue, 12 Dec 2017 22:45:35 GMT  
		Size: 2.6 MB (2608019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18f35ee1bc350f37f05623077614b04a65c94ccfedeb1b22b9577d1190fa6650`  
		Last Modified: Wed, 27 Dec 2017 17:14:19 GMT  
		Size: 31.7 MB (31720429 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `pypy:3-slim` - linux; 386

```console
$ docker pull pypy@sha256:77398de5cdaa3e330114b28bdd97452ee8a02582605619a9bf531de6d0bc20de
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **65.9 MB (65929948 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1631a6977e0bf7e09c1063e96bcab4254941ac5522abc25bc521d711533937c1`
-	Default Command: `["pypy3"]`

```dockerfile
# Tue, 12 Dec 2017 14:21:05 GMT
ADD file:d31765999b40e32b628f3ec72b762f007f4918b08c507484e425adc990c87c26 in / 
# Tue, 12 Dec 2017 14:21:05 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 22:02:21 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Dec 2017 22:02:22 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 22:08:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Wed, 27 Dec 2017 19:05:55 GMT
ENV PYPY_VERSION=5.10.0
# Wed, 27 Dec 2017 19:05:55 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 27 Dec 2017 19:25:13 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) pypyArch='linux64'; sha256='aa4fb52fb858d973dd838dcf8d74f30705e5afdf1150acb8e056eb99353dfe77' ;; 		armel) pypyArch='linux-armel'; sha256='c2cc529befb3e1f2ef8bd4e96af4a823c52ef2d180b0b3bd87511c5b47d59210' ;; 		i386) pypyArch='linux32'; sha256='529bc3b11edbdcdd676d90c805b8f607f6eedd5f0ec457a31bbe09c03f5bebfe' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding PyPy $PYPY_VERSION binary release"; exit 1 ;; 	esac; 		fetchDeps=' 		bzip2 		wget 	'; 	apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/*; 		wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy3-v${PYPY_VERSION}-${pypyArch}.tar.bz2"; 	echo "$sha256 *pypy.tar.bz2" | sha256sum -c; 	tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2; 	rm pypy.tar.bz2; 		pypy3 --version; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		pypy3 get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		rm -f get-pip.py; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 27 Dec 2017 19:25:13 GMT
CMD ["pypy3"]
```

-	Layers:
	-	`sha256:6b323e7c684c46ec9e577d3acb692c7e1c0c26ffbea6a4530dbe784a7eedf0f7`  
		Last Modified: Tue, 12 Dec 2017 14:49:35 GMT  
		Size: 30.3 MB (30266257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:846baa5afdbb2caec4218e67e02a9b0793718ada3ec4d2a8c4d9ebe7c73c0713`  
		Last Modified: Tue, 12 Dec 2017 22:13:37 GMT  
		Size: 5.0 MB (4957755 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9496c6a37dbcb61fe2218728b3ec6b904d78757813955aa061f70ecfbddc4614`  
		Last Modified: Wed, 27 Dec 2017 21:07:41 GMT  
		Size: 30.7 MB (30705936 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
