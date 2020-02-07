---
layout: post
title:  "Errors redirects"
#date:   2020-01-31 22:26:23 +0200
categories: [blog, web]
tags: [web]
---

## Adding custom error messages

### Introduction 

The motivation is to display a custom error message instead of the standard server's error page:  
![Motivation](/assets/images/404.png)

In addition, using the same method, additional features might be obtained like:
* redirects from pretty addresses `yoursite.com/topic` to actual web pages about these topics like `yoursite.com/pages/topic.html`
* Generated error page from a single template instead of creating one per each error type.

All the solutions may be overridden by hosting provider's configurations so reaching hosting tech support might be required.

### Web servers types

There are 2 main web servers (a program that listens for incoming connection and based on the input string,  which is a web address, sends matching html page):
1. Apache
2. Nginx

### Solutions
#### Solution for Apache
In the base site's folder e.g. `./wwww/yoursite.com` create `.htaccess` file with following text with updated path to your error page:  
```
ErrorDocument 404 /error_pages/404.html
```  
<br />
<br />

#### Solution for Nginx
<span style="color:red">It isn't working in my case of shared hosting server as `*.conf` file is read only.</span>

Find configuration file of Nginx, in my case, it sits here:  `/etc/nginx/vhosts/u12345/balzes.com.conf`

add into `server` block:  
```
server {
...
    error_page 404 /error_pages/404.html;
    location = /error_pages/404.html {
            internal;
    }  
...
}
```
[internal](https://nginx.org/en/docs/http/ngx_http_core_module.html#internal) - For my current understanding, it means that this page will be accessible only as a result of an internal redirect, but not by direct access like `www.balzes.com/error_pages/404.html`.


And here is explained how to create template-based error page:  
[https://blog.adriaan.io/one-nginx-error-page-to-rule-them-all.html](https://blog.adriaan.io/one-nginx-error-page-to-rule-them-all.html)




#### Alternate solution for Nginx
<span style="color:red">**[TBD]** </span>
(To Be Determined) will update shortly.

