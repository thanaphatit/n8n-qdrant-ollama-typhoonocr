FROM n8nio/n8n:latest

USER root

# อัพเดท repo และติดตั้งแพ็กเกจที่จำเป็น
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      python3 \
      python3-pip \
      poppler-utils \
      curl \
      git \
    && rm -rf /var/lib/apt/lists/*

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
