## `python:2-windowsservercore`

```console
$ docker pull python@sha256:01a1e151fef74dc65842fb407d01b66f6d417ed2ccdcb8c0f37dbfe243f8b436
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64
	-	windows version 10.0.16299.125; amd64

### `python:2-windowsservercore` - windows version 10.0.14393.2007; amd64

```console
$ docker pull python@sha256:2ba08e774f1846479425d5006d9150c9e13d4d59cf750b60ab618746cbb912d8
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.4 GB (5428265849 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0cd807fca2427372d9a855fde877b80393ac26c3efbc6769f1725ab547a5a4e2`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 17:39:50 GMT
ENV PYTHON_VERSION=2.7.14
# Fri, 05 Jan 2018 17:39:51 GMT
ENV PYTHON_RELEASE=2.7.14
# Fri, 05 Jan 2018 17:42:04 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}.amd64.msi' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.msi'; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'python.msi', 			'/quiet', 			'/qn', 			'TARGETDIR=C:\Python', 			'ALLUSERS=1', 			'ADDLOCAL=DefaultFeature,Extensions,TclTk,Tools,PrependPath' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.msi -Force; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:42:05 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Fri, 05 Jan 2018 17:43:35 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:44:43 GMT
RUN pip install --no-cache-dir virtualenv
# Fri, 05 Jan 2018 17:44:44 GMT
CMD ["python"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:449343c9d7e2919413898dc8a7e8780ef164b76a3b9dd19de104706edf05113a`  
		Last Modified: Thu, 04 Jan 2018 20:07:32 GMT  
		Size: 1.3 GB (1304019288 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c86d0434e36d69287bea586f96045245d5ee4f04e4e2a5edf6881dbbfdc628c3`  
		Last Modified: Fri, 05 Jan 2018 10:13:30 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e41b6b16cb26c71bf465c4eb0edd8a39b1334438b55231f414a13ac00683eb51`  
		Last Modified: Fri, 05 Jan 2018 17:47:00 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a9c15adc9f74c1ddcdb59ff1aaf400bc89364293c20323221e7a3bee0d1692`  
		Last Modified: Fri, 05 Jan 2018 17:47:00 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13de81a1e220546359b424835fdfa8ef7a5b9ff2b9e4fdd5c64a61ebeb7ca4c8`  
		Last Modified: Fri, 05 Jan 2018 17:47:08 GMT  
		Size: 38.4 MB (38414025 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e153921e590d4c85a36a8e29f669cf4e03836d942660971b46f66e6233118dc8`  
		Last Modified: Fri, 05 Jan 2018 17:46:56 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964c61bf86aa7f476d772ef6a86d865a149fe4425ca2f2686a96c9eed1fc8ccd`  
		Last Modified: Fri, 05 Jan 2018 17:47:02 GMT  
		Size: 9.1 MB (9060226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9702d0ff66644104c0d306b20cf430d447f69cb2e996a67d54bfe3c04cb98ef8`  
		Last Modified: Fri, 05 Jan 2018 17:46:59 GMT  
		Size: 6.8 MB (6780436 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c8cf9e4d2d620e721acc43a87022a449d97f111ccf6d3239215de3118f7f017`  
		Last Modified: Fri, 05 Jan 2018 17:46:56 GMT  
		Size: 1.2 KB (1190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `python:2-windowsservercore` - windows version 10.0.16299.125; amd64

```console
$ docker pull python@sha256:f11322ae39758adf7c4230e0e39aa3f4ac3ecf26b8348415ef656181e84f1411
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **2.9 GB (2916692330 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8caa71a4541e9402927ee2ff1cbbc449996c37aac2c75073e4e89d72a90b5104`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sat, 09 Dec 2017 18:00:03 GMT
RUN Install update 10.0.16299.125
# Thu, 14 Dec 2017 01:07:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Tue, 19 Dec 2017 17:54:57 GMT
ENV PYTHON_VERSION=2.7.14
# Tue, 19 Dec 2017 17:54:57 GMT
ENV PYTHON_RELEASE=2.7.14
# Tue, 19 Dec 2017 17:56:46 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}.amd64.msi' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.msi'; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'python.msi', 			'/quiet', 			'/qn', 			'TARGETDIR=C:\Python', 			'ALLUSERS=1', 			'ADDLOCAL=DefaultFeature,Extensions,TclTk,Tools,PrependPath' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.msi -Force; 		Write-Host 'Complete.';
# Tue, 19 Dec 2017 17:56:47 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Tue, 19 Dec 2017 17:58:05 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Tue, 19 Dec 2017 17:58:58 GMT
RUN pip install --no-cache-dir virtualenv
# Tue, 19 Dec 2017 17:58:59 GMT
CMD ["python"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:e50cc21fbc56936f06a5d9dfe4559b7108a89064fcb39dfbe14150d5cfeb912b`  
		Last Modified: Mon, 11 Dec 2017 22:06:21 GMT  
		Size: 589.5 MB (589524514 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:da9070a4da21ca9a4ce14f2c4d0f840c44addcfa4b5c90c421df47e49151d7e6`  
		Last Modified: Thu, 14 Dec 2017 02:02:37 GMT  
		Size: 1.2 KB (1180 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbf780d71b11789a94f9b93e57fc343fa41629006760da498cee7fee22fbfbab`  
		Last Modified: Tue, 19 Dec 2017 18:02:59 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db2dee1b2b8a405bb2bc1dac5e5190fd0aeaafbc9c50338e22bb69c6b5bfa357`  
		Last Modified: Tue, 19 Dec 2017 18:02:58 GMT  
		Size: 1.2 KB (1170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a552719e301f16502f6d8b0510c98c1ccce4a4fa34143e2911a27f3471ad361a`  
		Last Modified: Tue, 19 Dec 2017 18:03:07 GMT  
		Size: 38.0 MB (37965114 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0be92c675ea0af726e324e21431cb3469c3cdf6fac703f2cf3f9b0b2e4968efd`  
		Last Modified: Tue, 19 Dec 2017 18:02:56 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12b1e34cf691c19775fd5f83c1523175dbee69b68e05c10c36ffcc46826c69fa`  
		Last Modified: Tue, 19 Dec 2017 18:03:01 GMT  
		Size: 8.6 MB (8578701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f9b397f75598012e41317241ea804d820d38f4dbdcc4c87ff8d9e6504e25b95`  
		Last Modified: Tue, 19 Dec 2017 18:02:57 GMT  
		Size: 6.3 MB (6317482 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95c180f621df2ec553fcca29a7f46b90d87252fff8fa142cf91d65fd8ba61d59`  
		Last Modified: Tue, 19 Dec 2017 18:02:55 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
