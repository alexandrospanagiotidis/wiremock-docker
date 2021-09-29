FROM gcr.io/distroless/java:11

ARG WIREMOCK_VERSION

LABEL wiremock.version=$WIREMOCK_VERSION

# We want a shell so we can pass/interpolate arguments
COPY --from=busybox:musl /bin/busybox /bin/sh

WORKDIR /wiremock

ADD https://repo1.maven.org/maven2/com/github/tomakehurst/wiremock-standalone/$WIREMOCK_VERSION/wiremock-standalone-$WIREMOCK_VERSION.jar wiremock.jar

EXPOSE 8080

ENTRYPOINT java -jar wiremock.jar --port 8080 ${WIREMOCK_OPTIONS}
