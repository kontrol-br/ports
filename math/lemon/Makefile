PORTNAME=	lemon
DISTVERSION=	1.3.1
PORTREVISION=	4
CATEGORIES=	math
MASTER_SITES=	https://lemon.cs.elte.hu/pub/sources/
PKGNAMEPREFIX=	coin-or-

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Library for Efficient Modeling and Optimization in Networks
WWW=		https://lemon.cs.elte.hu/trac/lemon/

LICENSE=	BSL
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libCbc.so:math/cbc \
		libCgl.so:math/cgl \
		libClp.so:math/clp \
		libCoinUtils.so:math/coinutils \
		libOsi.so:math/osi

USES=		cmake
USE_LDCONFIG=	yes

CMAKE_ON=	BUILD_SHARED_LIBS

CONFLICTS_BUILD=	SoPlex # Incompatible with SoPlex-4.0.0 optional dependency: https://lemon.cs.elte.hu/trac/lemon/ticket/616

OPTIONS_DEFINE=		GLPK
OPTIONS_DEFAULT=	GLPK

GLPK_DESC=		Build with GLPK solver
GLPK_CMAKE_BOOL=	LEMON_ENABLE_GLPK
GLPK_LIB_DEPENDS=	libglpk.so:math/glpk

.include <bsd.port.options.mk>

.if ${OPSYS} == FreeBSD && ${OSVERSION} >= 1400091
CXXFLAGS+=  -Dregister=
.endif

post-install:
	@${RM} ${STAGEDIR}${PREFIX}/bin/${PORTNAME}-0.x-to-1.x.sh

.include <bsd.port.mk>
