# Simple and neat maintenance page
50 lines of html for your users while the backend services are unavailable.

<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='https://github.com/fabricev/maintenance-page/blob/master/unavailable.html' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

# Usage

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
