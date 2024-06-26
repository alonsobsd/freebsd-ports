PORTNAME=	topcom
DISTVERSION=	1.1.2
CATEGORIES=	math
MASTER_SITES=	https://www.wm.uni-bayreuth.de/de/team/rambau_joerg/TOPCOM-Downloads/
DISTNAME=	${PORTNAME:tu}-${DISTVERSION:S/./_/g}

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Computing triangulations of point configurations and oriented matroids
WWW=		https://www.wm.uni-bayreuth.de/de/team/rambau_joerg/TOPCOM/index.html

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libcddgmp.so:math/cddlib \
		libgmp.so:math/gmp

USES=		autoreconf gmake localbase:ldflags tar:tgz

GNU_CONFIGURE=	yes

EXTRACT_AFTER_ARGS=	--exclude ${PORTNAME}-${DISTVERSION}/external \
			--no-same-owner --no-same-permissions

CFLAGS+=	-I${LOCALBASE}/include/cdd/
LDFLAGS+=	-lgmp -lgmpxx -lcddgmp

CONFLICTS_INSTALL=	p5-Set-CrossProduct # bin/cross

WRKSRC=		${WRKDIR}/${PORTNAME}-${DISTVERSION}

OPTIONS_DEFINE=		SOPLEX # SOPLEX shouldn't be made default because SoPlex's license prevents packaging.

SOPLEX_DESC=		Build with SoPlex linear programming problem solver
SOPLEX_CXXFLAGS=	-I${LOCALBASE}/include/soplex
SOPLEX_LIB_DEPENDS=	libsoplex.so:math/SoPlex
SOPLEX_BROKEN=		not compatible with SoPlex-5.0.2 - missing header, reported to the upstream author vie e-mail

post-patch:
	@${FIND} ${WRKSRC} -name "Makefile*" \
		| ${XARGS} ${REINPLACE_CMD} ' \
			s|\.\./external/lib/libcddgmp\.a|${LOCALBASE}/lib/libcddgmp.so| ; \
			s|\.\./external/lib/libgmp\.a|${LOCALBASE}/lib/libgmp.so| ; \
			s|\.\./external/lib/libgmpxx\.a|${LOCALBASE}/lib/libgmpxx.so|'

post-patch-SOPLEX-off:
	@${REINPLACE_CMD} -e 's|AC_CHECK_LIB(soplex,|AC_CHECK_LIB(soplex_disabled,|' ${WRKSRC}/configure.ac

.include <bsd.port.mk>
