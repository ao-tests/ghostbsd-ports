# Created by: thinker@branda.to
# $FreeBSD$

PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
PORTREVISION=	0

MAINTAINER=	lev@FreeBSD.org
COMMENT=	Python bindings for version control system

BUILD_DEPENDS=	${LOCALBASE}/include/py3c.h:devel/py3c

USES=		python:${BINDINGS_PYTHON_VERSION}
USE_PYTHON=	flavors py3kplist

PORTREVISION_114=	0
PORTREVISION_LTS=	0

SVN_BUILD_BINDINGS=	yes

.include "${.CURDIR}/../../devel/subversion/Makefile.addons"

CATEGORIES+=	python

.if ${WITH_SUBVERSION_VER} == 114
BINDINGS_PYTHON_VERSION=	3.5+
.elif ${WITH_SUBVERSION_VER} == LTS
BINDINGS_PYTHON_VERSION=	2.7
.else
BROKEN=			Wrong WITH_SUBVERSION_VER=${WITH_SUBVERSION_VER}, only 114 (default) and LTS are supported
.endif

CONFIGURE_ARGS+=	--without-gnome-keyring \
			--without-kwallet \
			--with-apxs=no

ALL_TARGET=	swig-py check-swig-py
INSTALL_TARGET=	install-swig-py

.include <bsd.port.post.mk>
