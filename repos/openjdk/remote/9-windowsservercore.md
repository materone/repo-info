## `openjdk:9-windowsservercore`

```console
$ docker pull openjdk@sha256:d907565609e68db73ed1b44b1f0c35d0c9b2770f0f75da4f58dfd0474d89233b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64
	-	windows version 10.0.16299.125; amd64

### `openjdk:9-windowsservercore` - windows version 10.0.14393.2007; amd64

```console
$ docker pull openjdk@sha256:43b3b13d424c44d929cf87f6b8c61fc0953f56d834bd1c1a0511734cc39ff8e0
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5575365333 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0c057d81fd178cca2bdf02db78ada73044ac7357893ba79b78b5251942af8ee8`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 10:02:18 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Fri, 05 Jan 2018 10:03:43 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Fri, 05 Jan 2018 10:08:19 GMT
ENV JAVA_VERSION=9.0.1
# Fri, 05 Jan 2018 10:08:19 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.1-1
# Fri, 05 Jan 2018 10:08:20 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.1-1.b01.ojdkbuild.windows.x86_64.zip
# Fri, 05 Jan 2018 10:08:21 GMT
ENV JAVA_OJDKBUILD_SHA256=53d857727194635546d8af1e9c93ff272b737a46c1a03ef3d99b8078ab4e11f2
# Fri, 05 Jan 2018 10:10:45 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 10:10:47 GMT
CMD ["jshell"]
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
	-	`sha256:8043493a566c4b6517006bcc781208f6a6ed6679b087349f1c3abcfbc7c5bbc0`  
		Last Modified: Fri, 05 Jan 2018 10:13:30 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9863b66916588215ba59a3ee437280bdacb3e25f890c1f8886ddc754f6ed36b1`  
		Last Modified: Fri, 05 Jan 2018 10:13:32 GMT  
		Size: 4.9 MB (4932063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d931da49980d0d4a417819ae4f1408940fd28e2cda6a4c5dac0baab32713c695`  
		Last Modified: Fri, 05 Jan 2018 10:14:50 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4929ef856d4e4bffd6fb5247f0d218e18a21707b917f56565ab377ed4a598d90`  
		Last Modified: Fri, 05 Jan 2018 10:14:48 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ba2be08aa56925cc021618902b262fbc6ab036c8492974b75c5e1bca258dd96`  
		Last Modified: Fri, 05 Jan 2018 10:14:48 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f033c22fc1284318bba76038b7fdf3c4df8af60b0689a22d7f60688b36b9398`  
		Last Modified: Fri, 05 Jan 2018 10:14:48 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8d1aed251f3d14a8324fa037f67ba058fd1003c2baeb3ce100eb4e88fb00f48`  
		Last Modified: Fri, 05 Jan 2018 10:15:09 GMT  
		Size: 196.4 MB (196419721 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e868bf545ce852fdb5ff7215cfc2d98b345b0039ddb355e510a7e36986db083a`  
		Last Modified: Fri, 05 Jan 2018 10:14:48 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:9-windowsservercore` - windows version 10.0.16299.125; amd64

```console
$ docker pull openjdk@sha256:860adf983557922866401fe7ba856f7cff884fd3b702e1be0516191a5e4a6302
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.1 GB (3064193191 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:81cd630bc8cbd0bc2eff9cbc8ebe08bac33679ddeafe52ab1eb006671e0d6992`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sat, 09 Dec 2017 18:00:03 GMT
RUN Install update 10.0.16299.125
# Thu, 14 Dec 2017 01:07:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Thu, 21 Dec 2017 00:51:52 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Thu, 21 Dec 2017 00:53:07 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Thu, 21 Dec 2017 00:59:43 GMT
ENV JAVA_VERSION=9.0.1
# Thu, 21 Dec 2017 00:59:44 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.1-1
# Thu, 21 Dec 2017 00:59:45 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.1-1.b01.ojdkbuild.windows.x86_64.zip
# Thu, 21 Dec 2017 00:59:46 GMT
ENV JAVA_OJDKBUILD_SHA256=53d857727194635546d8af1e9c93ff272b737a46c1a03ef3d99b8078ab4e11f2
# Thu, 21 Dec 2017 01:01:41 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Thu, 21 Dec 2017 01:01:42 GMT
CMD ["jshell"]
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
	-	`sha256:be4727218d80350734a2ff75950b02669cb9e891a64cc496a6fe850c84e9bf19`  
		Last Modified: Thu, 21 Dec 2017 01:04:54 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeb7f8227c2e7979ac78eaadd86ab48aa19cc620c09b553a6098103be58694b0`  
		Last Modified: Thu, 21 Dec 2017 01:04:55 GMT  
		Size: 4.4 MB (4420909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f14f164ba7ae91c7a48172294471bed773903b6df44e796bb45f29e4026e1088`  
		Last Modified: Thu, 21 Dec 2017 01:06:52 GMT  
		Size: 1.2 KB (1155 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65c474275228f1369a41424c1f88219aec91b4de11df2cea760be535f6c9c8d5`  
		Last Modified: Thu, 21 Dec 2017 01:06:50 GMT  
		Size: 1.2 KB (1183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13ed0966cc33cf218ff71a19a54ec537260dc4504891668c78d7a87c362d8479`  
		Last Modified: Thu, 21 Dec 2017 01:06:50 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46707ea8d4091a621236e8fbea320aaa465e386b933b0be6beda510003c92247`  
		Last Modified: Thu, 21 Dec 2017 01:06:50 GMT  
		Size: 1.2 KB (1187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:245e50c4e7df3920b5b2b2e3aca754f4af7bb1e557ffc176a7721546fed6fe98`  
		Last Modified: Thu, 21 Dec 2017 01:07:09 GMT  
		Size: 195.9 MB (195938900 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6534f3ffcf63fd64f5bafa8726ea1bd8a81bb4839a540339e8dbc477fc17303e`  
		Last Modified: Thu, 21 Dec 2017 01:06:50 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
