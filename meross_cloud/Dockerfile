ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY common.py /
COPY cover.py /
COPY __init__.py /
COPY light.py /
COPY sensor.py /
COPY switch.py /

# Install requirements for add-on
RUN apk add --no-cache python3

# Python 3 HTTP Server serves the current working dir
# So let's set it to our add-on persistent data directory.
# WORKDIR /data

RUN chmod a+x /run.sh
RUN pip3 install meross_iot

CMD [ "/run.sh" ]
