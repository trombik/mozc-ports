UNIDIC_TO_MOZC=	UniDic-to-Mozc
PORTNAME=	${UNIDIC_TO_MOZC:tl}
DISTVERSION=	1.0.0
DISTVERSIONPREFIX=	v
CATEGORIES=	japanese

MAINTAINER=	y@trombik.org
COMMENT=	Mozc user dictionary based on UniDic
WWW=		https://github.com/jassdack/UniDic-to-Mozc/

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/UNIDIC_LICENSE.txt

USES=	zip
NO_BUILD=	yes
NO_ARCH=	yes

DISTFILES=	mozc_unidic_merged_${DISTVERSIONFULL}.zip
MASTER_SITES+=	http://github.com/jassdack/${UNIDIC_TO_MOZC}/releases/download/${DISTVERSIONFULL}/
SUB_FILES=	pkg-message
SUB_LIST=	DATADIR=${DATADIR}

post-extract:
	${MKDIR} ${WRKSRC}
	${MV} ${EXTRACT_WRKDIR}/*.tsv ${EXTRACT_WRKDIR}/*.txt ${WRKSRC}/

do-install:
	${INSTALL} -d ${STAGEDIR}${DATADIR}
	${INSTALL_DATA} ${WRKSRC}/*.tsv ${STAGEDIR}${DATADIR}/

.include <bsd.port.mk>
