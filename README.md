# hikari-note


Generating a self-signed certificate using OpenSSL
Last Updated: 2022-09-22

OpenSSL is an open source implementation of the SSL and TLS protocols. It provides the transport layer security over the normal communications layer, allowing it to be intertwined with many network applications and services.

Before you begin
One of the following roles is required to complete this task:

Administrator
Owner
Topology Administrator
Custom role with the Settings: Manage permissions
About this task
This topic tells you how to generate a self-signed SSL certificate request using the OpenSSL toolkit to enable HTTPS connections.

Procedure
To generate a self-signed SSL certificate using the OpenSSL, complete the following steps:

Write down the Common Name (CN) for your SSL Certificate. The CN is the fully qualified name for the system that uses the certificate. For static DNS, use the hostname or IP address set in your Gateway Cluster (for example. 192.16.183.131 or dp1.acme.com).
Run the following OpenSSL command to generate your private key and public certificate. Answer the questions and enter the Common Name when prompted.
`openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certificate.pem`

Review the created certificate:
`openssl x509 -text -noout -in certificate.pem`

Combine your key and certificate in a PKCS#12 (P12) bundle:
` openssl pkcs12 -inkey key.pem -in certificate.pem -export -out certificate.p12`

Validate your P2 file.
`openssl pkcs12 -in certificate.p12 -noout -info`

Once the certificate file is created, it can be uploaded to a keystore.
In the Cloud Manager, click Resources Resources.
Select TLS.
Click Create in the Keystore table.
Create a Keystore and upload the certificate file following the instructions at Creating a Keystore.
