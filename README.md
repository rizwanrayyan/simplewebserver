# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:07.10.2023
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<title>Top Software industries</title>
<body>
<table border="2" cellspacing="10" cellpadding="6" align="center">
<caption>Top 5 Revenue Generating Software companies </caption>
<tr>
<th>s.no</th>
<th>companies</th>
<th>revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65 Billion </th>
</tr>
<th>2</th>
<th>Oracle</th>
<th>29.6 Billion </th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 Billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4 Billion</th>
</tr>
<tr>
<th>5</th>
<th>Syemtec</th>
<th>5.6 BIllion</th>
</tr>
</table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2023-11-01 000103](https://github.com/rizwanrayyan/simplewebserver/assets/121215820/94180a08-e0ba-4966-8aac-dcfbd42979be)

## RESULT:
The program for implementing simple webserver is executed successfully.
