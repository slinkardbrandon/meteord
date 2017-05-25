FROM debian:jessie
MAINTAINER Standard Nutrition

ENV METEORD_DIR /opt/meteord
COPY scripts $METEORD_DIR

ARG NODE_VERSION
ENV NODE_VERSION ${NODE_VERSION:-6.10.3}
ONBUILD ENV NODE_VERSION ${NODE_VERSION:-6.10.3}

RUN bash $METEORD_DIR/lib/install_base.sh
RUN bash $METEORD_DIR/lib/install_node.sh
RUN bash $METEORD_DIR/lib/install_phantomjs.sh
RUN bash $METEORD_DIR/lib/install_wk.sh
RUN bash $METEORD_DIR/lib/install_xvfb.sh
RUN bash $METEORD_DIR/lib/cleanup.sh

EXPOSE 80
ENTRYPOINT bash $METEORD_DIR/run_app.sh
