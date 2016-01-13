###########################################################
#
#	a TypeSafe Activator, based on (openjdk8 based on) Alpine Linux
#
###########################################################

FROM		ehudkaldor/openjdk8
MAINTAINER	Ehud Kaldor <ehud.kaldor@gmail.com>

ENV		ACTIVATOR_VERSION 1.3.7

RUN		apk add --update curl unzip ca-certificates bash && \
		rm -rf /var/cache/apk/* 

RUN		curl -sSL https://downloads.typesafe.com/typesafe-activator/$ACTIVATOR_VERSION/typesafe-activator-$ACTIVATOR_VERSION.zip > activator_$ACTIVATOR_VERSION.zip
RUN		unzip activator_$ACTIVATOR_VERSION.zip && \
		rm -rf activator_$ACTIVATOR_VERSION.zip && \
		ln -s /activator-dist-$ACTIVATOR_VERSION/activator /usr/bin/

