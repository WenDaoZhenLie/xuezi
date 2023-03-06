## **server**
```python
class WSGIServer(object):
    socket_family = socket.AF_INET
    socket_type = socket.SOCK_STREAM
    request_queue_size = 10

    def __init__(self, sever_address):
        self.listen_socket = listen_socket = socket.socket(
            self.socket_family, 
            self.socket_type
        )
        listen_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
        listen_socket.bind(server_address)
        listen_socket.listen(self.request_queue_size)
        host, port = self.listen_socket.getsockname()[:2]
        self.server_name = socket.getfqdn(host)
        self.server_port = port
        self.headers_set = []

    def set_application(self, application):
        self.application = application

    def serve_forever(self):
        while True:
            self.client_connection, client_address = self.listen_socket.accept()
            self.handle_request()
    
    def handle_request(self):
        self.request_data = request_data = self.client_connection.recv(1024)
        self.parse_request(request_data)
        env = self.get_environ()
        result = self.application(env, self.start_response)
        self.finish_response(result)
    
    def parse_request(self, text):
        request_line = text.splitlines()[0]
        request_line = request_line.rstrip('\r\n')
        (self.request_method,  # GET
         self.path,
         self.request_version  # HTTP/1.1
         ) = request_line.split()

    def get_environ(self):
        env = {
            'wsgi.version': (1, 0),
            'wsgi.url_scheme': 'http',
            'wsgi.input': StringIO.StringIO(self.request_data),
            'wsgi.errors': sys.stderr,
            'wsgi.multithread': False,
            'wsgi.multiprocess': False,
            'wsgi.run_once': False,
            'REQUEST_METHOD': self.request_method,
            'PATH_INFO': self.path,
            'SERVER_NAME': self.host,
            'SERVER_PORT': self.port,
            'USER_AGENT': self.request_dict.get('User-Agent')
        }
        return env

    def start_response(self, status, response_headers, exc_info=None):
        server_headers = [
            ('Date', datetime.datetime.now().strftime('%a, %d %b %Y %H:%M:%S GMT')),
            ('Server', 'WSGIServer 0.2'),
        ]
        self.headers = response_headers + server_headers
        self.status = status
    
    def finish_response(self, result):
        try:
            response = f'HTTP/1.1 {self.status}\r\n'
            for header in response_headers:
                response += '{0}: {1}\r\n'.format(*header)
            response += '\r\n'
            for data in result:
                response += data
            self.client_connection.sendall(response)
        finally:
            self.client_connection.close()
    

SERVER_ADDRESS = (HOST, PORT) = '', 8888


def make_server(server_address, application):
    server = WSGIServer(server_address)
    server.set_application(application)
    return server


if __name__ = '__main__':

```

## **application**
```python
def application(environ, start_response):
    start_response(status, response_headers)
    isinstance(_, Iterable)
    return _
```