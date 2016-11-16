# ---------------------------------------------------------------------------- #
#                               List GitHub Stars                              #
# ---------------------------------------------------------------------------- #
FROM mhart/alpine-node:12.18.2

ENV GITHUB_USER=droxey

ADD https://gist.githubusercontent.com/droxey/75e8a0ff55242b097708720fa3781fed/raw/6f6bf9f24cfc54daf070b056498d37d54b3f68a9 starcounter.js

CMD node starcounter.js ${GITHUB_USER}
