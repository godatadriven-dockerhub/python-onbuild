ARG MINICONDA_VERSION=3
FROM godatadriven/miniconda:${MINICONDA_VERSION}

LABEL org.label-schema.name="Python OnBuild $MINICONDA_VERSION" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.version=$MINICONDA_VERSION

ONBUILD COPY requirements.txt requirements.txt
ONBUILD RUN apt-get update \
            && apt-get install -y gcc\
            && pip install --no-cache-dir -r requirements.txt \
            && apt-get remove -y --purge gcc \
            && apt-get autoremove -y \
            && apt-get clean

ENV PYTHONUNBUFFERED true
ENV PYTHONDONTWRITEBYTECODE 1

WORKDIR /app
ENTRYPOINT ["python"]
CMD ["/app/main.py"]