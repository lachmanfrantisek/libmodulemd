FROM fedora-modularity/libmodulemd-deps-fedora:30

MAINTAINER Stephen Gallagher <sgallagh@redhat.com>

RUN dnf -y --setopt=install_weak_deps=False install rsync \
    && dnf -y clean all

ARG TARBALL

ADD $TARBALL /builddir/

RUN  /builddir/.travis/coverity_prep.sh

ENTRYPOINT /builddir/.travis/coverity/travis-tasks.sh
