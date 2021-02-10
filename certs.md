# Certificates Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

## JKS → P12
```bash
keytool -importkeystore -srckeystore [MY_KEYSTORE.jks] -destkeystore [MY_FILE.p12] -srcstoretype JKS -deststoretype PKCS12 -deststorepass [PASSWORD_PKCS12] -srcalias [ALIAS_SRC] -destalias [ALIAS_DEST]

# MY_FILE.p12: path to the PKCS#12 file (.p12 or .pfx extension) that is going to be created.
# MY_KEYSTORE.jks: path to the keystore that you want to convert.
# PASSWORD_PKCS12: password that will be requested at the PKCS#12 file opening.
# ALIAS_SRC: name matching your certificate entry in the JKS keystore, "tomcat" for example.
# ALIAS_DEST: name that will match your certificate entry in the PKCS#12 file, "tomcat" for example.
```