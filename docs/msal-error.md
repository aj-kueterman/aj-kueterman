---
layout: default
title: MSAL Error Debug Steps
description: Help AJ debug a weird auth issue.
permalink: /msal-error
---

If you ever get this error in stage/prod: 

![screenshot of auth error 'unable to access the authentication service'](https://private-user-images.githubusercontent.com/88003213/386340505-a1c17be4-a13a-4bc6-a109-6b0d7762430d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzMxNTM1NjIsIm5iZiI6MTczMzE1MzI2MiwicGF0aCI6Ii84ODAwMzIxMy8zODYzNDA1MDUtYTFjMTdiZTQtYTEzYS00YmM2LWExMDktNmIwZDc3NjI0MzBkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMDIlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjAyVDE1Mjc0MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWU5ZjgyMzRkMzE0ODY2YmUwNzUyNDNkYmVlYzQ2NzY2NGM2MzQ3NGJmYjVlODE1YjU3NjdlMTJkYTZlMGFkYjcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.yLKVcPdKinp7BrYtxwSyp4wAZC3BBh6CM8_0p9Bz7Pg)

Follow these steps to debug and let AJ know.

1. Document if you just changed environments or not
1. Check to see if you got an `MSAL_Exception` or a `B2C_Auth_Exception` from Telemeter in Logcat, and document the details of the log
1. Try again using the 'Please try again' link, and document the behavior/logs
1. If that doesn't work, try killing the app and restarting, and document the behavior/logs
1. If that doesn't work, try re-installing the app, and document the behavior/logs
1. Inform AJ (aj.kueterman@kroger.com)
