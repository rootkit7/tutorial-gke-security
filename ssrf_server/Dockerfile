FROM python:3

RUN apt update -y && apt full-upgrade -y && \
    apt clean && rm -rf /var/lib/apt/lists/*
RUN pip install bottle pycurl

# Add unprivileged user
RUN useradd server -d /home/server
WORKDIR /home/server

ADD server.py .
ADD index.html .
ADD get.html .
RUN chown -R server:server /home/server

USER server
EXPOSE 8080
CMD ["python", "server.py"]
