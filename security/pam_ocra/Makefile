PORTNAME=	pam_ocra
DISTVERSION=	1.6
CATEGORIES=	security

MAINTAINER=	sg2342@googlemail.com
COMMENT=	RFC6287 (OCRA) PAM module
WWW=		https://github.com/sg2342/pam_ocra

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		ssl uidfix
USE_GITHUB=	yes
GH_ACCOUNT=	sg2342

CFLAGS+=	-I${OPENSSLINC}
LDFLAGS+=	-L${OPENSSLLIB}

PLIST_FILES=	lib/pam_ocra.so \
		lib/pam_ocra.so.0 \
		sbin/ocra_tool \
		man/man8/pam_ocra.8.gz \
		man/man8/ocra_tool.8.gz

.include <bsd.port.mk>
