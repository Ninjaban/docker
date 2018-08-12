FROM alpine

RUN apk update
RUN apk upgrade
RUN apk add emacs

ENTRYPOINT ["emacs", "-nw"]
