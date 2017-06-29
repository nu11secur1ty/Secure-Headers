
Please note the best practices below suggest methods to change webserver configuration to add headers. Security headers can also be successfully added to your application at the software level as well in almost every web language. Many web frameworks add some of these headers automatically. 

# HTTP Strict Transport Security (HSTS)
------------------------------------------------------------------------------------------------------------

- Apache
  Edit your apache configuration file and add the following to your VirtualHost.
    ```
    Header always set Strict-Transport-Security "max-age=63072000; includeSubdomains"
    ```
- nginx
  Edit your nginx configuration file and add the following snippet.
  ```
  add_header Strict-Transport-Security "max-age=63072000; includeSubdomains";
  ```
- lighttpd
  Edit your lighttpd configuration file and add the following snippet.
  ```
  setenv.add-response-header = ("Strict-Transport-Security" => "max-age=63072000; includeSubdomains",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#strict-transport-security
  
 
# Public Key Pinning Extension for HTTP (HPKP)
-------------------------------------------------------------------------------------------------------------


- Apache
  Edit your apache configuration file and add the following to your VirtualHost.
  ```
      Header set Public-Key-Pins "pin-sha256=\"klO23nT2ehFDXCfx3eHTDRESMz3asj1muO+4aIdjiuY=\";    pin-sha256=\"633lt352PKRXbOwf4xSEa1M517scpD3l5f79xMD9r9Q=\"; max-age=2592000; includeSubDomains"
  ```
- nginx
  Edit your nginx configuration file and add the following snippet.
  ```
      add_header Public-Key-Pins "pin-sha256=\"klO23nT2ehFDXCfx3eHTDRESMz3asj1muO+4aIdjiuY=\"; pin-sha256=\"633lt352PKRXbOwf4xSEa1M517scpD3l5f79xMD9r9Q=\"; max-age=2592000; includeSubDomains";
  ```
- lighttpd
  Edit your lighttpd configuration file and add the following snippet.
  ```
      setenv.add-response-header = ("Public-Key-Pins" => "pin-sha256=\"klO23nT2ehFDXCfx3eHTDRESMz3asj1muO+4aIdjiuY=\"; pin-sha256=\"633lt352PKRXbOwf4xSEa1M517scpD3l5f79xMD9r9Q=\"; max-age=2592000; includeSubDomains",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#public-key-pinning
  
  # X-Frame-Options
  
  -----------------------------------------------------------------------------------------------------------

























