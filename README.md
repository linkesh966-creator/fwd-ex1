# EX01 Developing a Simple Webserver

## Date:
15/10/2026

## REG No:
26019024

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
    <title>List of Protocols</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f8ff;
            padding: 20px;
        }

        h1 {
            color: #163a70;
            text-align: center;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background-color: white;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        th {
            background-color: #1565c0;
            color: white;
            padding: 12px;
            border: 1px solid #0d47a1;
        }

        td {
            padding: 10px;
            border: 1px solid #b0bec5;
            text-align: left;
        }

        tr:nth-child(even) {
            background-color: #e3f2fd;
        }

        tr:nth-child(odd) {
            background-color: #ffffff;
        }

        tr:hover {
            background-color: #bbdefb;
        }

        td:first-child {
            text-align: center;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>List of Protocols</h1>

    <table>
        <tr>
            <th>S.No.</th>
            <th>Protocol</th>
            <th>Full Form</th>
            <th>Purpose</th>
            <th>Default Port</th>
        </tr>

        <tr>
            <td>1</td>
            <td>HTTP</td>
            <td>Hypertext Transfer Protocol</td>
            <td>Transfers web pages</td>
            <td>80</td>
        </tr>

        <tr>
            <td>2</td>
            <td>HTTPS</td>
            <td>Hypertext Transfer Protocol Secure</td>
            <td>Secure web communication</td>
            <td>443</td>
        </tr>

        <tr>
            <td>3</td>
            <td>FTP</td>
            <td>File Transfer Protocol</td>
            <td>Transfers files</td>
            <td>21</td>
        </tr>

        <tr>
            <td>4</td>
            <td>TCP</td>
            <td>Transmission Control Protocol</td>
            <td>Reliable data transmission</td>
            <td>Not fixed</td>
        </tr>

        <tr>
            <td>5</td>
            <td>UDP</td>
            <td>User Datagram Protocol</td>
            <td>Fast data transmission</td>
            <td>Not fixed</td>
        </tr>

        <tr>
            <td>6</td>
            <td>DNS</td>
            <td>Domain Name System</td>
            <td>Converts domain names into IP addresses</td>
            <td>53</td>
        </tr>

        <tr>
            <td>7</td>
            <td>DHCP</td>
            <td>Dynamic Host Configuration Protocol</td>
            <td>Assigns IP addresses automatically</td>
            <td>67, 68</td>
        </tr>

        <tr>
            <td>8</td>
            <td>SMTP</td>
            <td>Simple Mail Transfer Protocol</td>
            <td>Sends emails</td>
            <td>25</td>
        </tr>

        <tr>
            <td>9</td>
            <td>SSH</td>
            <td>Secure Shell</td>
            <td>Secure remote access</td>
            <td>22</td>
        </tr>

        <tr>
            <td>10</td>
            <td>Telnet</td>
            <td>Teletype Network</td>
            <td>Remote terminal access</td>
            <td>23</td>
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
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~

## OUTPUT:
![alt text](<Screenshot (8).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
