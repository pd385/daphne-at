FROM python:3.9.19

# The working directory where daphne_brain is placed is /usr/src/app/daphne_brain
WORKDIR /usr/src/app/daphne_brain

# Copy everything in the daphne_brain directory to /usr/src/app/daphne_brain
COPY ./. /usr/src/app/daphne_brain/.

# Set env variables
ENV DJANGO_SETTINGS_MODULE=daphne_brain.settings \
    USER=daphne \
    PASSWORD=daphnetest \
    #OPENAI_API_KEY=''\

# Update apt-get package manager -- Install daphne_brain dependencies
RUN apt-get -y update &&\
    apt-get -y upgrade &&\
    apt-get -y install build-essential manpages-dev &&\
    pip3 install --no-cache-dir -r ./requirements.txt

# Commands to start daphne_brain
#RUN python3 manage.py migrate --run-syncdb &&\
#    python3 manage.py collectstatic --clear --noinput

#CMD ["python", "manage.py", "migrate --run-syncdb"]

EXPOSE 8000

ENTRYPOINT ["python", "manage.py"]
#RUN python manage.py runserver 8000
CMD ["runserver", "0.0.0.0:8000"]
##CMD ["python", "manage.py"]
