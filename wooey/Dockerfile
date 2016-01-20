FROM python

COPY ./requirements.txt ./requirements.txt

RUN pip install -r ./requirements.txt
RUN wooify -p   datasci

RUN echo "from django.contrib.auth.models import User;" >> /datasci/manage.py
RUN echo "User.objects.create_superuser('me', 'me@raff.ca', 'pass')" >> /datasci/manage.py

RUN python /datasci/manage.py migrate

EXPOSE 8000

CMD [ "python", "/datasci/manage.py", "runserver", "0.0.0.0:8000"]