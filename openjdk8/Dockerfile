###########################################################
#
#	a base JDK8 image, based on Alpine Linux
#
###########################################################

FROM		alpine:3.3
MAINTAINER	Ehud Kaldor <ehud.kaldor@gmail.com>

RUN 		echo "@community http://nl.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories && \
		apk add --update openjdk8@community curl unzip binutils tar bzip2 xz xarchiver && \
		rm -rf /var/cache/apk/* 

RUN		curl -sSL http://ftp.us.debian.org/debian/pool/main/c/ca-certificates-java/ca-certificates-java_20140324_all.deb > /ca-certificate-java.deb && \
		ar xv ca-certificate-java.deb && \
		tar -Jxvf data.tar.xz && \
                tar -zxvf control.tar.gz && \
		cd /etc/ssl/certs &&
		for file in `ls`; do keytool -importcert -keypass changeit -file $file -keystore /usr/lib/jvm/java-1.8-openjdk/jre/lib/security/cacerts -noprompt -storepass changeit -alias $file; done && \
		rm -rf ca-certificate-java.deb && \
		rm -rf data.tar.xz && \
		rm -rf control.tar.gz

RUN		apk update && \
		apk del -f unzip binutils tar bzip2 xz && \
                rm -rf /var/cache/apk/*
