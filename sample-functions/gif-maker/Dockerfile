FROM alpine:3.7

RUN apk --no-cache add ffmpeg gifsicle curl \
   && curl -LS https://github.com/openfaas/faas/releases/download/0.9.6/fwatchdog > /usr/bin/fwatchdog \
   && chmod +x /usr/bin/fwatchdog \
   && apk del curl
WORKDIR /root/
COPY entry.sh   .
ENV fprocess="./entry.sh"
CMD ["fwatchdog"]
