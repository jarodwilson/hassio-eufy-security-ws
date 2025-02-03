ARG BUILD_FROM
FROM $BUILD_FROM

ARG EUFY_SECURITY_WS_VERSION

WORKDIR /usr/src/app
RUN apk update && apk upgrade
RUN apk add "nodejs>20.18"
RUN apk add --no-cache npm jq git
RUN npm install typescript
RUN set -x && npm install --force "https://github.com/jarodwilson/eufy-security-ws/releases/download/${EUFY_SECURITY_WS_VERSION}/eufy-security-ws-${EUFY_SECURITY_WS_VERSION}.tgz"

COPY run.sh /
RUN chmod a+x /run.sh
WORKDIR /data

CMD [ "/run.sh" ]
