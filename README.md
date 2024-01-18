# Integrating PERENDER with Apache
Updated at: https://doc.perender.com/cdn-integrations/apache

# Step 1.

<b>Enable the following modules in the httpd.conf file:</b>

<b>1.</b> headers_module

<b>2.</b> proxy_module

<b>3.</b> proxy_http_module

<b>4.</b> ssl_module

<b>5.</b> rewrite_module

To do this, uncomment the LoadModule line for each of the above modules in the httpd.conf file.

Then, add the following code in the httpd.conf file to allow proxy through https.

<b>&lt;IfModule mod_ssl.c&gt;</b>
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>SSLProxyEngine On</b>
  
<b>&lt;/IfModule&gt;</b>

# Step 2.

<b>1.</b> Then, create a file named .htaccess in the root of your application.

<b>Notes:</b>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; If your application already has the .htaccess file, include the following code.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; If your .htaccess file already contains rewrite rules, include the PERENDER rule at the beginning of them and remove [END] from the provided code to allow the evaluation of your subsequent rewrite rules.

<b>2.</b> Within the provided code, replace [PERENDER_TOKEN] with your token from the PERENDER dashboard.
