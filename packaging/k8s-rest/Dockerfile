FROM python:3.6
ARG DEBIAN_FRONTED=noninteractive
RUN printenv
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils > /dev/null
RUN apt-get install -y build-essential tcl
RUN apt-get install -y systemd-sysv
RUN apt-get update  > /dev/null
RUN apt-get install  -y wget > /dev/null
RUN apt-get install  -y zip > /dev/null
RUN apt-get install  -y libaio1 > /dev/null
RUN apt-get update > /dev/null
RUN apt-get install  -y alien > /dev/null
WORKDIR /
RUN mkdir /code
WORKDIR /code
COPY . .
RUN make init
RUN pip install --upgrade pip --user
WORKDIR /code/k8s
ENTRYPOINT ["make"]