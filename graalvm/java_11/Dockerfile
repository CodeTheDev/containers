# Copyright (c) 2022 CodeTheDev
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

FROM            debian:bullseye-slim

LABEL           author="CodeTheDev" maintainer="code@codeslab.ca"

LABEL           org.opencontainers.image.source="https://github.com/CodeTheDev/containers"
LABEL           org.opencontainers.image.licenses=MIT

ARG		DEBIAN_FRONTEND=noninteractive
ARG		GRAAL_VERSION=22.3.0
ARG		JAVA_VERSION=11
ARG		DOWNLOAD_URL=https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-${GRAAL_VERSION}/graalvm-ce-java${JAVA_VERSION}-linux-amd64-${GRAAL_VERSION}.tar.gz

RUN		apt-get update -y \
		&& apt-get full-upgrade -y \
		&& apt-get install -y curl tar \
		&& mkdir -p /opt/java/graalvm \
		&& cd /opt/java/graalvm \
		&& curl -L ${DOWNLOAD_URL} -o graalvm.tar.gz \
		&& tar -xvzf graalvm.tar.gz \
		&& rm -rf graalvm.tar.gz

ENV		PATH="/opt/java/graalvm/graalvm-ce-java${JAVA_VERSION}-${GRAAL_VERSION}/bin:$PATH" \
		JAVA_HOME="/opt/java/graalvm/graalvm-ce-java${JAVA_VERSION}-${GRAAL_VERSION}"
