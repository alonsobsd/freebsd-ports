PORTNAME=	xsimd
DISTVERSION=	13.0.0
CATEGORIES=	devel

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	C++ wrappers for SIMD intrinsics and mathematical functions
WWW=		https://github.com/xtensor-stack/xsimd

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

TEST_DEPENDS=	googletest>0:devel/googletest \
		doctest>=2.4.9:devel/doctest

USES=		cmake:testing compiler:c++11-lang

USE_GITHUB=	yes
GH_ACCOUNT=	xtensor-stack

CMAKE_TESTING_ON=	BUILD_TESTS # tests fail, see https://github.com/xtensor-stack/xsimd/issues/917

NO_ARCH=	yes

.include <bsd.port.mk>
