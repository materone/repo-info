## `python:rc-windowsservercore`

```console
$ docker pull python@sha256:6be070281be29c10fde647452675651ff24238e3e34714f64357fffabe89204a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64
	-	windows version 10.0.16299.125; amd64

### `python:rc-windowsservercore` - windows version 10.0.14393.2007; amd64

```console
$ docker pull python@sha256:90bafab26494854ba44e006293b4923357e51af30aa9feb7ecce827c8e388ea0
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.4 GB (5434814836 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d0deb7789428d4e2da4e53167a692fbd91dc5c427551c89e26d1c6195d670835`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 17:26:16 GMT
ENV PYTHON_VERSION=3.7.0a3
# Fri, 05 Jan 2018 17:26:17 GMT
ENV PYTHON_RELEASE=3.7.0
# Fri, 05 Jan 2018 17:29:04 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.exe'; 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:29:05 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Fri, 05 Jan 2018 17:30:35 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:30:36 GMT
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
	-	`sha256:c8e3b94ceb77e9b0fc6f0926e8448ebc959fd5d09061a0c9da87f3271f8365d6`  
		Last Modified: Fri, 05 Jan 2018 17:45:19 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f23470d8dc6b489f1c0844d7749e9e5be8648b6ef13d6e09bf47954a21508fef`  
		Last Modified: Fri, 05 Jan 2018 17:45:15 GMT  
		Size: 1.2 KB (1190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b94b6d038764136e18ce0a03eb422edeb03be1881607b96989260c1f783cd2bf`  
		Last Modified: Fri, 05 Jan 2018 17:45:33 GMT  
		Size: 51.4 MB (51421951 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:744f4603311237c93f9ed171dac629fc896b8998cea63289fb6d24a0322ca50f`  
		Last Modified: Fri, 05 Jan 2018 17:45:15 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b23686dda664118284b50e9d803db2a3b111e560c4d151ff8f9c04c2164579fa`  
		Last Modified: Fri, 05 Jan 2018 17:45:20 GMT  
		Size: 9.4 MB (9381750 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae7f540b4a62f71e7c19659c0ac85e667b9eea4efd6a831fad4f21ac2150772b`  
		Last Modified: Fri, 05 Jan 2018 17:45:16 GMT  
		Size: 1.2 KB (1170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `python:rc-windowsservercore` - windows version 10.0.16299.125; amd64

```console
$ docker pull python@sha256:856c193a0182341d8f09961f88c5443448137077b2cc90974d7e897ee108e859
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **2.9 GB (2919190306 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4969d85dabb79d81542715a6ca52e76d2b86fcd8b34f503974cf64a78f118896`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sat, 09 Dec 2017 18:00:03 GMT
RUN Install update 10.0.16299.125
# Thu, 14 Dec 2017 01:07:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Tue, 19 Dec 2017 17:29:26 GMT
ENV PYTHON_VERSION=3.7.0a3
# Tue, 19 Dec 2017 17:29:27 GMT
ENV PYTHON_RELEASE=3.7.0
# Tue, 19 Dec 2017 17:32:18 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.exe'; 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Tue, 19 Dec 2017 17:32:19 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Tue, 19 Dec 2017 17:33:35 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Tue, 19 Dec 2017 17:33:36 GMT
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
	-	`sha256:a9b0f4ef23ba03c83feded9ebd0584de2bf88e3defc2094c597e53bfa42a987a`  
		Last Modified: Tue, 19 Dec 2017 18:00:02 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1f6e0330735ca168865a7f54cc52958ab12a88318cd5e0b6083a67fb70d90fa`  
		Last Modified: Tue, 19 Dec 2017 17:59:57 GMT  
		Size: 1.2 KB (1171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9faa30f07432ab2a467082f064ff0d16b98d83bab98ccbf7ea293ecd0f1defb5`  
		Last Modified: Tue, 19 Dec 2017 18:00:12 GMT  
		Size: 46.5 MB (46497366 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c8e9ae206ddf1bb9860be6bcbcc56488c4e8e9d8891170b16a8bd3289f027b4`  
		Last Modified: Tue, 19 Dec 2017 17:59:57 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6cc58e81a294caef085a19bd927a4cdb9d68a4e8b58e2054cd08a4b28053780`  
		Last Modified: Tue, 19 Dec 2017 18:00:01 GMT  
		Size: 8.9 MB (8861911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:412f3019dc58d1e7a4f907e80ae210bd9fee48606effd093af527430919796ac`  
		Last Modified: Tue, 19 Dec 2017 17:59:58 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
