FROM ubuntu:18.04 AS build
RUN apt-get update && \
    apt-get install -y build-essential
RUN mkdir /app
WORKDIR /app
COPY . /app
RUN mkdir bin
RUN gcc hello.c -o bin/hello

FROM ubuntu:18.04
COPY --from=build /app/bin/hello /app/hello
CMD /app/hello
