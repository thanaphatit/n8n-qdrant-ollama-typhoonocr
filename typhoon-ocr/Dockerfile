# Custom n8n image with Python and Typhoon OCR
FROM n8nio/n8n:latest

USER root

# ติดตั้ง Python และ dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        python3 \
        python3-pip \
        poppler-utils \
        curl \
        git && \
    rm -rf /var/lib/apt/lists/*

# ให้เรียก python ได้ตรงๆ
RUN ln -s /usr/bin/python3 /usr/bin/python

# ติดตั้ง Typhoon OCR SDK
RUN pip3 install --no-cache-dir typhoon-ocr

USER node