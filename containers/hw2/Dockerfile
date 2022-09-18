ARG PYTHON_VERSION=3.9

FROM python:${PYTHON_VERSION}

WORKDIR /opt

COPY requirements.txt requirements.txt
COPY ./service ./service

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8080

HEALTHCHECK --interval=5s --timeout=10s --start-period=5s --retries=3 CMD curl --fail http://localhost:8080/ping || exit 1

CMD ["uvicorn", "service.main:app", "--host", "0.0.0.0", "--port", "8080"]