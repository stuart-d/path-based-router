# Simple path based router using NGINX

Build a dockerised nginx instance to redirect users to URL's based on path.

e.g. 

https://localhost/news --> https://news.com.au
https://localhost/news/cnn --> https://cnn.com.au

```
# Clone repo
git clone

# Generate self signed certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx-selfsigned.key -out nginx-selfsigned.crt
mkdir certs
mv nginx-selfsigned.key certs/
mv nginx-selfsigned.crt certs/

# Build dockerfile
docker build -t path-router .

# Run
docker run -p 443:443 -d path-router
```

