* [OpenSSL Commands](https://redkestrel.co.uk/articles/openssl-commands)
* [OpenSSL Cookbook](https://www.feistyduck.com/library/openssl-cookbook/online/)

#### Check openssl directory

openssl version -d

#### Calculate Cert SHA1 Fingreprint

openssl x509 -in digicert.pem -noout -fingerprint

#### Show SSL Cert chain
* HTTPS: `echo 0|openssl s_client -showcerts -connect host:port`
* FTPS: `openssl s_client -showcerts -connect host:port  -starttls ftp`

