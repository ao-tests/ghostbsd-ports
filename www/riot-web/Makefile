# $FreeBSD$

PORTNAME=	riot
DISTVERSIONPREFIX=	v
DISTVERSION=	1.6.2
CATEGORIES=	www
MASTER_SITES=	https://github.com/vector-im/riot-web/releases/download/${DISTVERSIONFULL}/
PKGNAMESUFFIX=	-web

MAINTAINER=	ports@xanderio.de
COMMENT=	Glossy Matrix collaboration client for the web

LICENSE=	APACHE20

NO_ARCH=	yes
NO_BUILD=	yes

do-install:
	@${MKDIR} ${STAGEDIR}${WWWDIR}
	cd ${WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${WWWDIR}

.include <bsd.port.mk>
