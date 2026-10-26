# Build current anmol098/waka-readme-stats from source.
# Their published Docker Hub image (wakareadmestats/waka-readme-stats:master)
# is still Debian Bullseye; those security packages 404 after Bullseye LTS ended.
FROM python:3.13-alpine

ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1

RUN apk add --no-cache g++ jpeg-dev zlib-dev libjpeg make git \
    && git clone --depth 1 https://github.com/anmol098/waka-readme-stats.git /tmp/wrs \
    && mkdir -p /waka-readme-stats/assets \
    && pip3 install --no-cache-dir -r /tmp/wrs/requirements.txt \
    && cp /tmp/wrs/sources/* /waka-readme-stats/ \
    && cp -r /tmp/wrs/locales /waka-readme-stats/locales \
    && git config --global user.name "readme-bot" \
    && git config --global user.email "41898282+github-actions[bot]@users.noreply.github.com" \
    && rm -rf /tmp/wrs

WORKDIR /waka-readme-stats
ENTRYPOINT ["python3", "main.py"]
