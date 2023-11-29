FROM python:3-alpine
 
# Create app directory
WORKDIR /app
 
# Install app dependencies
COPY requirements.txt ./
RUN pip install -r requirements.txt
# Bundle app source
COPY . .
 
EXPOSE 5000
EXPOSE 443
EXPOSE 80
CMD [ "python3", "app.py"]
