
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

- Apache
  Add this line below into your site's configuration to configure Apache to send X-Frame-Options header for all pages.
  ```
  Header set X-Frame-Options DENY
  ```
- nginx
  Add snippet below into configuration file to send X-Frame-Options header.
  ```
  add_header X-Frame-Options "DENY";
  ```
- lighttpd
  Add snippet below into configuration file to send X-Frame-Options header.
  ```
  setenv.add-response-header = ("X-Frame-Options" => "DENY",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options

# X-XSS-Protection

-----------------------------------------------------------------------------------------------------------
Add appropriate snippet into configuration file.

- Apache
  ```
  Header set X-XSS-Protection: 1; mode=block
  ```
- nginx
  ```
  add_header X-XSS-Protection "1;mode=block";
  ```
- lighttpd
  ```
  setenv.add-response-header = ("X-XSS-Protection" => "1; mode=block",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#x-xss-protection

# X-Content-Type-Options

-----------------------------------------------------------------------------------------------------------

Add appropriate snippet into configuration file.

- Apache
  ```
  Header set X-Content-Type-Options: nosniff
  ```
- nginx
  ```
  add_header X-Content-Type-Options "nosniff";
  ```
- lighttpd
  ```
  setenv.add-response-header = ("X-Content-Type-Options" => "nosniff",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options

# Content-Security-Policy

-----------------------------------------------------------------------------------------------------

Add appropriate snippet into configuration file.

- Apache
  ```
  Header set Content-Security-Policy "script-src 'self'; object-src 'self'"
  ```
- nginx
  ```
  add_header Content-Security-Policy "script-src 'self'; object-src 'self'";
  ```
- lighttpd
  ```
  setenv.add-response-header = ("Content-Security-Policy" => "script-src 'self'; object-src 'self'",)
  ```
- IIS
  Visit https://scotthelme.co.uk/hardening-your-http-response-headers/#content-security-policy

# X-Permitted-Cross-Domain-Policies

------------------------------------------------------------------------------------------------------

Add appropriate snippet into configuration file.

- Apache
  ```
  Header set X-Permitted-Cross-Domain-Policies: none
  ```
- nginx
  ```
  add_header X-Permitted-Cross-Domain-Policies "none";
  ```
- lighttpd
  ```
  setenv.add-response-header = ("X-Permitted-Cross-Domain-Policies" => "none",)
  ```
- IIS
  [update needed]


# Referrer-Policy

--------------------------------------------------------------------------------------------------------

- Apache
  [update needed]

- nginx
  [update needed]

- lighttpd
  [update needed]

- IIS
  [update needed]

# Have fun with nu11secur1ty =)







