---
layout: default
title: MSAL Error Debug Steps
description: Help AJ debug a weird auth issue.
permalink: /msal-error
---

If you ever get this error in stage/prod: 

![screenshot of auth error 'unable to access the authentication service'](https://private-user-images.githubusercontent.com/88003213/386339295-dd2d73ba-3dbf-47c4-9b38-4131ca6eee3f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzE2MTIzNTQsIm5iZiI6MTczMTYxMjA1NCwicGF0aCI6Ii84ODAwMzIxMy8zODYzMzkyOTUtZGQyZDczYmEtM2RiZi00N2M0LTliMzgtNDEzMWNhNmVlZTNmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDExMTQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMTE0VDE5MjA1NFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTllMjk4ZmYzZmZjMTkyOTJjMzJmZTYyNTJmN2FiYjAzZGNkNDE2YTMxNDVlOWI4ZDAyYzY4MzBlMmMyM2MwMDImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.3FTIl-SVlZXNrjl1G8YneRrB6sBhKLrpdqYvn7n1J8Y)

Follow these steps to debug and let AJ know.

- [ ] Document if you just changed environments or not
- [ ] Check to see if you got an `MSAL_Exception` from Telemeter in Logcat
- [ ] Attach the debugger, and put a breakpoint on these two places and click the retry button (and/or close out the fragment and retry Sign In)
    - [ ] [In the `else` block of the `initialiseMSAlApplication` function](https://github.com/krogertechnology/kroger-android/blob/2baae1574700c7945c61d758ddf877171a88190c/DigitalCoupons/features/authentication/src/main/java/com/kroger/mobile/authentication/ui/B2CAuthenticationLoadingFragment.kt#L97)
    - [ ] [In the `MSALResult.Failure` block of `signInOrCreateAccount`](https://github.com/krogertechnology/kroger-android/blob/2baae1574700c7945c61d758ddf877171a88190c/DigitalCoupons/features/authentication/src/main/java/com/kroger/mobile/authentication/ui/B2CAuthenticationLoadingFragment.kt#L110)
- [ ] Inform AJ (aj.kueterman@kroger.com)
