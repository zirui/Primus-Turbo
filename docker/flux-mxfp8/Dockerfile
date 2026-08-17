ARG BASE_IMAGE=unifiedtrainingdockers.azurecr.io/utd/ci@sha256:bb44383965e4cab227b06348e2f5044290542424252c97f476625920cf0f849f
FROM ${BASE_IMAGE}

ARG PRIMUS_TURBO_VERSION=0.3.2.dev43
ENV GPU_ARCHS=gfx950 \
    SETUPTOOLS_SCM_PRETEND_VERSION=${PRIMUS_TURBO_VERSION} \
    PRIMUS_TURBO_MXFP8_USE_FLUX_CONFIGS=1

COPY . /opt/primus-turbo-src
RUN pip3 install --no-build-isolation --no-deps /opt/primus-turbo-src \
    && rm -rf /opt/primus-turbo-src

LABEL org.opencontainers.image.base.digest="sha256:bb44383965e4cab227b06348e2f5044290542424252c97f476625920cf0f849f" \
      org.opencontainers.image.revision="b0bcdc25" \
      org.opencontainers.image.title="Primus FLUX MXFP8 dependencies"
