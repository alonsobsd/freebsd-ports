PORTNAME=	kplot
DISTVERSIONPREFIX=	VERSION_
DISTVERSION=	0_1_15
PORTREVISION=	1
CATEGORIES=	graphics

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Cairo plotting library
WWW=		https://kristaps.bsd.lv/kplot/

LICENSE=	ISCL
LICENSE_FILE=	${WRKSRC}/LICENSE.md

USES=		gmake gnome localbase pkgconfig
USE_GNOME=	cairo

USE_GITHUB=	yes
GH_ACCOUNT=	kristapsdz

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/libkplot.so

.include <bsd.port.mk>
