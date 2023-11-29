# SSL/TLS Documentation

## Table of Contents

<!-- toc -->

- [Overview](#overview)
- [Flask Secure Connection](#Flask-Secure-Connection)

<!-- tocstop -->

## Overview
This documentation is for anyone trying to setup a secure connection in Flask, FastApi, Spark, Airflow, 

## Flask Secure Connection
As an example, we're going to use the application [app.py](https://github.com/KubeHawk/SSL/blob/main/Flask/app.py).

```sh
# Import flask module
from flask import Flask
 
app = Flask(__name__)
 
@app.route('/')
def index():
    return 'Hello to Flask!'
 
# main driver function
if __name__ == "__main__":
    app.run(debug=True,host='0.0.0.0',ssl_context=('cert.pem','key.pem'))
```
For the certificates, we only need to generate both cert.pem and key.pem with OpenSSL.

```sh
openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365
```
This command will generate the certificate we need with RSA algorithme using a 4096 bit and expires in a year.

![image](https://github.com/KubeHawk/SSL/assets/75808939/993ce510-a9ab-4028-a1de-61fbbe19ebc7)



