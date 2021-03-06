## `openjdk:9-windowsservercore-1709`

```console
$ docker pull openjdk@sha256:dcbb5df950c21c2353fa1f153899f4de364e0114f79c4cba90258366fb0cc40b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.125; amd64

### `openjdk:9-windowsservercore-1709` - windows version 10.0.16299.125; amd64

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
