# EX01 Developing a Simple Webserver
## Date:5-10-2023

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue Generating Software Companies<h1>
</body>
<ul>
    <li>Accenture</li>
    <li>HCL</li>
    <li>Zoho</li>
    <li>HP</li>
    <li>GOOGLE</li>
</ul>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2023-10-19 155809](https://github.com/mustbenandan/simplewebserver/assets/129033280/096b8a5c-3496-4c6e-bf12-eb29d1362a3c)
![Screenshot 2023-10-19 160117](https://github.com/mustbenandan/simplewebserver/assets/129033280/65009c4a-ceaf-4c35-9ff0-7b8e28c64522)


## RESULT:
The program for implementing simple webserver is executed successfully.
