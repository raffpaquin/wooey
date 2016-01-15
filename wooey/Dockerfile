FROM python

COPY ./requirements.txt ./requirements.txt

RUN pip install -r ./requirements.txt
RUN wooify -p   datasci

RUN python ./datasci/manage.py createsuperuser

EXPOSE 8000

CMD [ "python", "/datasci/manage.py", "runserver","0.0.0.0:8000"]