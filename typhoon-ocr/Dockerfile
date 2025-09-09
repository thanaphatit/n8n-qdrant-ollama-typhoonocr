FROM n8nio/n8n:latest

USER root

# ติดตั้ง dependencies ด้วย apk (Alpine package manager)
RUN apk add --no-cache \
      python3 \
      py3-pip \
      poppler-utils \
      curl \
      git

# สร้าง virtual environment และติดตั้ง typhoon-ocr
RUN python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --upgrade pip && \
    /opt/venv/bin/pip install typhoon-ocr

# เพิ่ม virtual environment ลงใน PATH
ENV PATH="/opt/venv/bin:$PATH"

# สร้างโฟลเดอร์แชร์ข้อมูล
RUN mkdir -p /data /doc && \
    chown -R node:node /data /doc

USER node
WORKDIR /home/node
