## `golang:rc-windowsservercore-1709`

```console
$ docker pull golang@sha256:3d3f25c6dd232b4d342b48f59b62218c40e4b641ad9611daa7c2953e3ed2dea4
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.125; amd64

### `golang:rc-windowsservercore-1709` - windows version 10.0.16299.125; amd64

```console
$ docker pull golang@sha256:f89ad0bc702b9e8448428d5500aacda270d43c8e9d5a3f18201f07da9145678a
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.1 GB (3098266492 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b71cd312e9472cc0635d63bfdc8033a6c31d7a8d0e1374788f1eab2a595ba1e5`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sat, 09 Dec 2017 18:00:03 GMT
RUN Install update 10.0.16299.125
# Thu, 14 Dec 2017 01:07:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Thu, 14 Dec 2017 01:07:59 GMT
ENV GIT_VERSION=2.11.1
# Thu, 14 Dec 2017 01:07:59 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Thu, 14 Dec 2017 01:08:00 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Thu, 14 Dec 2017 01:08:01 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Thu, 14 Dec 2017 01:09:47 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Thu, 14 Dec 2017 01:09:48 GMT
ENV GOPATH=C:\gopath
# Thu, 14 Dec 2017 01:10:35 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Thu, 14 Dec 2017 01:10:36 GMT
ENV GOLANG_VERSION=1.10beta1
# Thu, 14 Dec 2017 01:18:27 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'ff2789b7baf33f87111d30bac81ac1ae19dcc16bdd75553f9b5aceda14733a40'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Thu, 14 Dec 2017 01:18:29 GMT
WORKDIR C:\gopath
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
	-	`sha256:2db23d1ca581e2fe9eb3452303eb5aaef9cfd697788b3533ec8f4762c0814924`  
		Last Modified: Thu, 14 Dec 2017 02:02:36 GMT  
		Size: 1.2 KB (1185 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89827c291560e82e5dd38a7f03183b577c322ee1e312560f2bd92c384d9c2947`  
		Last Modified: Thu, 14 Dec 2017 02:02:35 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c008f62b24c4b813b602b0862b7335e002b219e941fb054696f6a75dfe2f97d8`  
		Last Modified: Thu, 14 Dec 2017 02:02:33 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a295427d954111694f96b479249ce25425534a79d54faa5ed67502d37d2f0c5`  
		Last Modified: Thu, 14 Dec 2017 02:02:32 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88158e57209e09bf2a6a6681cf3fbbaf91849bd7b88f80642069411ca307c958`  
		Last Modified: Thu, 14 Dec 2017 02:02:51 GMT  
		Size: 28.8 MB (28810841 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebb385cfc896cf251f251ff9cc3672d1f0883fe0046cedeb1c1ddb926b433629`  
		Last Modified: Thu, 14 Dec 2017 02:02:29 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12ecfcf588d13c3c0eff46fa699e0a9c613719aade19791247b475154993bd6e`  
		Last Modified: Thu, 14 Dec 2017 02:02:31 GMT  
		Size: 4.4 MB (4368768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a193d52a00d43a79411497eb013166e36e202826116472f90d44f455a434e3c`  
		Last Modified: Thu, 14 Dec 2017 02:02:30 GMT  
		Size: 1.2 KB (1168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f41ef2dccd88492eddd28854f17169d0193dc7ae6df9effe3db504419efff32`  
		Last Modified: Thu, 14 Dec 2017 02:05:41 GMT  
		Size: 201.3 MB (201252129 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31b3e0395b6b3b915c740ea04c190d885f924278ae1b7ab137525bab1f7338a5`  
		Last Modified: Thu, 14 Dec 2017 02:02:30 GMT  
		Size: 1.4 KB (1350 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
