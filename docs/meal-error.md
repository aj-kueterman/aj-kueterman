---
layout: default
title: MSAL Error Debug Steps
description: Help AJ debug a weird auth issue.
permalink: /msal-error
---

If you ever get this error in stage/prod: 

![screenshot of auth error 'unable to access the authentication service'](https://private-user-images.githubusercontent.com/88003213/386340505-a1c17be4-a13a-4bc6-a109-6b0d7762430d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzE2MTI2MjMsIm5iZiI6MTczMTYxMjMyMywicGF0aCI6Ii84ODAwMzIxMy8zODYzNDA1MDUtYTFjMTdiZTQtYTEzYS00YmM2LWExMDktNmIwZDc3NjI0MzBkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDExMTQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMTE0VDE5MjUyM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTgzYjM2MTE3NjZjYjU3OWVmOGY3YTgyODJjMGYwZTEzYjZiMzkwNTVhOTFmNTExYTU1MGVkMGE5OTAyNjIyMDcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.N3gY8QnmYxVaOAicdlsjNegZrfLmHOkotEHwdwyjumE)

Follow these steps to debug and let AJ know.

1. Document if you just changed environments or not
1. Check to see if you got an `MSAL_Exception` from Telemeter in Logcat
1. Attach the debugger, and put a breakpoint on these two places and click the retry button (and/or close out the fragment and retry Sign In)
    1. [In the `else` block of the `initialiseMSAlApplication` function](https://github.com/krogertechnology/kroger-android/blob/2baae1574700c7945c61d758ddf877171a88190c/DigitalCoupons/features/authentication/src/main/java/com/kroger/mobile/authentication/ui/B2CAuthenticationLoadingFragment.kt#L97)
    1. [In the `MSALResult.Failure` block of `signInOrCreateAccount`](https://github.com/krogertechnology/kroger-android/blob/2baae1574700c7945c61d758ddf877171a88190c/DigitalCoupons/features/authentication/src/main/java/com/kroger/mobile/authentication/ui/B2CAuthenticationLoadingFragment.kt#L110)
1. Inform AJ (aj.kueterman@kroger.com)
