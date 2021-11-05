FROM python:3


# this line of code will config the working dir of the container to be "/scr"
WORKDIR /src

# this next 2 lines of code will copy the required files into the image's 
# ...working dir
COPY ./requirements.txt .
COPY ./server.py .

# this line of code will install all the python modules listed in the file 
# ..."requirements.txt"
RUN pip3 --no-cache-dir install -r requirements.txt

# this line of code will expose port "8000" on the container created from this image
EXPOSE 8000

# this line of code sets the env variable in order to run the flask app with the "flask run" command
ENV FLASK_APP=server.py
ENV FLASK_ENV=development

# this line of code sets the running process of the containers that will be made from this image.
# it will run the flask app and make it response to traffic on port 8000 coming on its interface.
# it will be the equivalant of running the following in a the CLI:
    # python -m flask run --port-8000 --host=0.0.0.0
    # this was needed because the code for the flask app did not contain the "app.run()" method at the
    # ...end of the file
ENTRYPOINT ["python", "-m", "flask", "run", "--port=8000", "--host=0.0.0.0"]
