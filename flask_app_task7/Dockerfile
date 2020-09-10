# our base image
FROM python:3.8-alpine

# install Python modules needed by the Python app
ADD ./templates . 
ADD ./app.py .
ADD ./requirements.txt . 
RUN pip install --no-cache-dir -r requirements.txt

# tell the port number the container should expose
EXPOSE 5000

# run the application
CMD ["python", "app.py"]
