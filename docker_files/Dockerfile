FROM ghcr.io/gohugoio/hugo:v0.154.3 AS site-builder
COPY --chown=hugo:hugo src/ /site/src/
WORKDIR /site/src/
RUN hugo --noBuildLock 


FROM httpd:2.4
COPY --from=site-builder /site/src/public /usr/local/apache2/htdocs/