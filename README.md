# SBB-XVA-1200
Fix for SSL certificate error in SBB app on iOS 13 beta

### Update: As of today, this workaround is no longer needed. SBB updated their app with proper certificate.

## Steps:
1) On your Mac, enter the following command in Terminal:

```openssl s_client -showcerts -connect p1.sbbmobile.ch:443```

2) As an output, you will get two blocks of base64-encoded text delimited by `-----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----`. Copy the second block (including those delimiters).
3) Open a new plaintext document in TextEdit or any other text editor, paste the copied code and save it as sbb_ca.pem
4) (Optional) Double click on the new certificate to validate that you created a valid certificate file. Keychain Access should open and when you click on View Ceritificate, you should see:
```
*.sbbmobile.ch
Root certificate authority
Expires: Monday, 1 October 2035 at 09:50:01 Central European Summer Time
"*.sbbmobile.ch" certificate is not trusted
```
5) AirDrop the certificate file to your iPhone/iPad running iOS 13 beta
6) Go to Settings and Install the certificate (There will be a new button at the top of the Settings page, between iCloud and Airplane Mode, asking you to finish the installation.)
7) Go to Settings > General > About > Certificate Trust Settings and enable the newly installed certificate

--- OR ---

Download the extracted certificate from this repo
