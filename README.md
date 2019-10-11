# Simple and neat maintenance page
50 lines of html for your users while the backend services are unavailable :

![Service Unavailable](screenshot.png)

# Usage
Comes in 2 versions:
- unavailable.html, static
- unavailable-reload, contains a background check for the backend service and page will automatically reload once available

## Example with HAProxy
Copy and modify the content of the html file in the path, check permissions, and add the *errorfile* directive to the defaults section of the haproxy configuration file (see [here](https://www.haproxy.com/blog/the-four-essential-sections-of-an-haproxy-configuration/)):

```
defaults
    log                        global
    option                     dontlognull
    option                     redispatch
    retries                    3
    errorfile                  503 /etc/haproxy/maintenance_page.http
```
