FROM quay.io/refgenomics/docker-ubuntu:14.04

MAINTAINER Amit James <aamitjames@gmail.com>

RUN apt install bcftools
RUN apt install bwa
RUN apt install samtools
RUN pip install cyvcf2

# Convenience commands
ADD align.py /usr/local/bin/align.py
RUN chmod +x /usr/local/bin/align.py
RUN ln -s /usr/local/bin/align.py /usr/local/bin/align
CMD ["/usr/local/bin/align"]

# Integration tests
ADD test /tmp/test
RUN bats /tmp/test
