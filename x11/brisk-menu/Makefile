PORTNAME=	brisk-menu
DISTVERSIONPREFIX=	v
DISTVERSION=	0.6.2
PORTREVISION=	2
CATEGORIES=	x11

MAINTAINER=	ericbsd@FreeBSD.org
COMMENT=	Brisk Menu is an efficient menu for the MATE Desktop
WWW=		https://github.com/solus-project/brisk-menu #brisk-menu

LICENSE=	GPLv2+ CC-BY-SA-4.0
LICENSE_COMB=	multi
LICENSE_FILE_CC-BY-SA-4.0=	${WRKSRC}/LICENSE.CC-BY-SA-4.0
LICENSE_FILE_GPLv2+ =	${WRKSRC}/LICENSE

LIB_DEPENDS=	libnotify.so:devel/libnotify

USES=		compiler:c11 gettext gnome mate meson ninja pkgconfig xorg

USE_GITHUB=	yes
GH_ACCOUNT=	getsolus
GH_TUPLE=	getsolus:brisk-menu-translations:e1b55e3:translations/subprojects/translations

USE_GNOME=	gtk30
GLIB_SCHEMAS=	com.solus-project.brisk-menu.gschema.xml
USE_MATE=	menus panel
USE_XORG=	x11

MESON_ARGS=	--sysconfdir=${PREFIX}/etc

.include <bsd.port.mk>
