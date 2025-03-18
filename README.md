
# EX01 Developing a Simple Webserver
## Date:11/03/2025

NAME : YASHWANTH K

REG NO : 212224040369

## AIM:
To develop a simple webserver to serve html pages and to display welcome to my website.

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



from http.server import HTTPServer, BaseHTTPRequestHandler

content = """

<!DOCTYPE html>

<html lang="en">

  <head>
  
    <meta charset="UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>My Personal Website</title>
    
    <style>
    
        body {
        
            font-family: Arial, sans-serif;
            
            text-align: center;
            
            margin: 0;
            
            padding: 0;
            
            background-color: #f4f4f4;
        }
        
        
        header {
        
            background: #333;
            
            color: white;
            
            padding: 20px;
            
            font-size: 24px;
        }
        
        
        section {
        
            padding: 20px;
        }
        
        
        footer {
        
            background: #333;
            
            color: white;
            
            padding: 10px;
            
            position: fixed;
            
            bottom: 0;
            
            width: 100%;
        }
        

    </style>

</head>

<body>

  <header>Welcome to My Website</header>
  
    <section>
    
        <h2>About Me</h2>
        
        <p>Hello! I'm [Your Name]. This is my simple personal website.</p>
    
    </section>
    
    <footer>&copy; 2025 My Personal Website</footer>

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


## OUTPUT:

![Screenshot 2025-03-11 114051](https://github.com/user-attachments/assets/8584fb47-6431-4e9f-a491-81e427a21229)


![Screenshot 2025-03-11 114017](https://github.com/user-attachments/assets/4d676104-1541-41a9-8ae7-962404e9f338)


## RESULT:
The program for implementing simple webserver is executed successfully.

