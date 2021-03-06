# Created by: ijliao
# $FreeBSD$

PORTNAME=	rpy2
PORTVERSION=	3.3.3
CATEGORIES=	math
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Python interface to the R Programming Language

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/gpl-2.0.txt

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}cffi>=1.10.0:devel/py-cffi@${PY_FLAVOR}
LIB_DEPENDS=	libR.so:math/R \
		libicui18n.so:devel/icu \
		libpcre.so:devel/pcre
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}cffi>=1.10.0:devel/py-cffi@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Jinja2>0:devel/py-Jinja2@${PY_FLAVOR} \
		${PYNUMPY} \
		${PYTHON_PKGNAMEPREFIX}pytz>=0:devel/py-pytz@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}tzlocal>=0:devel/py-tzlocal@${PY_FLAVOR}

USES=		compiler:c11 fortran python:3.6+ readline
USE_PYTHON=	autoplist distutils

MAKE_ENV=	RPY2_CFFI_MODE=BOTH

PLIST_FILES=	${PYTHON_SITELIBDIR}/__pycache__/_rinterface_cffi_abi.cpython-${PYTHON_SUFFIX}.${PYTHON_PYOEXTENSION} \
		${PYTHON_SITELIBDIR}/__pycache__/_rinterface_cffi_abi.cpython-${PYTHON_SUFFIX}.pyc \
		${PYTHON_SITELIBDIR}/_rinterface_cffi_abi.py

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/_rinterface_cffi_api.abi3.so

.include <bsd.port.mk>
