FROM python:3.9.6-slim

RUN pip3 install pipenv

WORKDIR /app
COPY ["Pipfile" , "Pipfile.lock" , "./"]

RUN pipenv install --system --deploy

COPY ["predict.py" , "model_C=1.0.bin" , "./"]

EXPOSE 9696

ENTRYPOINT ["gunicorn" , "--bind=0.0.0.0:9696", "predict:app" ]

