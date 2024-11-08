FROM python:3.9-slim

ARG VERSION=0.1.0
ARG CHECKSUM=3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444

WORKDIR /StaticJinja

ADD --checksum=sha256:${CHECKSUM} https://github.com/MrDave/StaticJinjaPlus/archive/refs/tags/${VERSION}.tar.gz /tmp/app.tar.gz

RUN tar xzf /tmp/app.tar.gz --strip-components=1 -C /StaticJinja && rm /tmp/app.tar.gz
RUN python3 -m venv venv
RUN . venv/bin/activate && pip install --no-cache-dir -r requirements.txt

ENTRYPOINT ["/StaticJinja/venv/bin/python3", "main.py"]

CMD ["--srcpath=/app/templates/", "--outpath=/app/build/"]
