FROM pytorch/pytorch:2.4.1-cuda12.4-cudnn9-runtime

ENV PYTHONUNBUFFERED "yes"

WORKDIR /opt/app

ENV DEBIAN_FRONTEND=noninteractive
ENV NCCL_DEBUG=INFO

RUN apt update && apt install -y \
    iputils-ping \
    net-tools \
    libnuma1 \
    libsubunit0 \
    libpci-dev \
    libibverbs1 \
    libibverbs-dev \
    ibverbs-utils \
    librdmacm1 \
    librdmacm-dev \
    libibumad3 \
    libibumad-dev \
    infiniband-diags \
    ibutils \
    numactl \
    perftest \
    iproute2

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY src .
