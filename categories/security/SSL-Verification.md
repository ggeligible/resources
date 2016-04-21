Very good resource: http://mislav.net/2013/07/ruby-openssl/
https://github.com/lostisland/faraday/issues/371

**********************
if you are only interested in how to make Ruby behave the same way as OpenSSL s_client or your browser does, you may skip to the very last section, I'll cover the fine print in what is following.

By default, the OpenSSL::X509::Store used for making the connection doesn't use any trusted certificates at all. Based on your knowledge of the application domain, you would typically feed an instance of X509::Store with the trusted certificate(s) that are relevant for your application. There are several options for this:

    Store#add_file takes a path to a PEM/DER-encoded certificate
    Store#add_cert takes an instance of X509::Certificate
    Store#add_path takes a path to a directory where trusted certificates can be found

### The "Browser" Approach

This is in contrast to the approach browsers, Java (cacerts), or Windows with its own internal store of trusted certificates, take. There the software is pre-equipped with a set of trusted certificates that is considered to be "good" in the opinion of the software vendor. Generally this is not a bad idea, but if you actually look into these sets, then you will soon notice that there are just too many certificates. An individual can't really tell whether all of these certificates should be trusted blindly or not.

### The Ruby Approach

The requirements of your typical Ruby application on the other hand are a lot different than that of a browser. A browser must be be able to let you navigate to any "legitimate" web site that comes with a TLS certificate and is served over https. But in a typical Ruby application you will only have to deal with a few services that use TLS or would otherwise require certificate validation.

And there is the benefit of the Ruby approach - although it requires more manual work, you will end up with a hand-tailored solution that exactly trusts the certificates it should trust in your given application context. This is tedious, but security is much higher this way because you expose a lot less attack surface. Take recent events: if you never had to include DigiNotar or any other compromised root in your trust set, then there's no way such breaches can affect you.

The downside of this, however, as you have already noticed, is that by default, if you don't actively add trusted certificates, the OpenSSL extension will not be able to validate any peer certificate at all. In order to make things work, you have to set up the configuration manually.

This inconvenience has led to a lot of dubious measures to circumvent it, the worst of all being to globally set OpenSSL::SSL::VERIFY_PEER = OpenSSL::SSL::VERIFY_NONE. Please don't do this. We have even made jokes about adding code that lets your application crash randomly if we encounter that hack :)

If manual trust setup seems too complicated, I'll offer an easy alternative now that makes the OpenSSL extension behave exactly the same as OpenSSL CLI commands like s_client.
Why s_client can verify the certificate

OpenSSL uses a similar approach to browsers and Windows. A typical installation will put a bundle of trusted certificates somewhere on your hard disk (something like /etc/ssl/certs/ca-bundle.crt) and this will serve as the default set of trusted certificates. That's where s_client looks when it needs to verify peer certificates and that's why your experiment succeeded.
Making Ruby act like s_client

If you'd still like to have the same comfort when validating certificates with Ruby, you can tell it to use the OpenSSL bundle of trusted certificates if available on your system by calling OpenSSL::X509::Store#set_default_paths. Additional information can be found here. To use this with XMLRPC::Client, simply ensure that set_default_paths gets called on the X509::Store it uses.
