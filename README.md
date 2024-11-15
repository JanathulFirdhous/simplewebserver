# EX01 Developing a Simple Webserver
## Date:08.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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

<html>
<body><pre>
<h1>Laptop configuration(24900115)</h1>
<ul>
<li>Device name       jannath</li>
<li>Processor         13th gen intel(R) core(TM)i7-1360P 2.20Ghz</li>
<li>Installed ram     16.0GB (15.7 GB usable)</li>
<li>Device id         216368D7-1D96-474A-BC0E=9AE87D56F723</li>
<li>Product id        00342-42676-67005-AAOEM</li>
<li>System type       64-bit operating system,x64-based processor</li>
<li>Pen and touch     no pen or touch input is available for this display</li>
</ul>

</pre></body>
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
![alt text](<Screenshot (3)-2.png>)
![alt text](<Screenshot (2).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
