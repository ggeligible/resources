https://redkestrel.co.uk/articles/openssl-commands

#### Check openssl directory

openssl version -d

#### Calculate Cert SHA1 Fingreprint

openssl x509 -in digicert.pem -noout -fingerprint

#### Show SSL Cert chain
echo 0|openssl s_client -showcerts -connect host:port 
