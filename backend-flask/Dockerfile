FROM python:3.10-slim-buster
# Inside container
# Make a new folder inside container
WORKDIR /backend-flask
# Outside container
# This contains library we want to install to run the app
COPY requirements.txt requirements.txt
# inside container
# install the python library used for the app
RUN pip3 install -r requirements.txt
# Outside container...>inside container
# . means everythings in the currents directory
# First period ./ backend-flask(outside container)
# Second period ./ backend-flask (inside  container) 
COPY . .
# Set envirnment variable(Env Var)
# Inside container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]