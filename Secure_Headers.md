
Please note the best practices below suggest methods to change webserver configuration to add headers. Security headers can also be successfully added to your application at the software level as well in almost every web language. Many web frameworks add some of these headers automatically. 

# HTTP Strict Transport Security (HSTS)

- Apache
  Edit your apache configuration file and add the following to your VirtualHost.
    ```
    Header always set Strict-Transport-Security "max-age=63072000; includeSubdomains"
    ```
    
    
