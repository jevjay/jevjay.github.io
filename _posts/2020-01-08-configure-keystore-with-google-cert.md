---
layout: post
title: "Updating Android keystore file with GPlay generated certificate"
date: 2020-01-08 08:36
categories: unity linux
---
Every android build needs to be signed with a keystore file, which (as per official Android documentation) "protects key material from unauthorized use".

Unity provides a way to configure a Keystore file via "Publishing Settings" (more information on this topic can be found [here](https://docs.unity3d.com/Manual/class-PlayerSettingsAndroid.html#Publishing)),but unfortunately it has one, rather annoying flaw: currently it does not support keystore creation with Google provided certificate which can be retrieved from "App Signing" section within application release management console in Google Play Console.

By default, "App signing" is disabled, which allows users to sign their generated keystores with their locally generated certificate and that is what Unity supports. But everything changes if you/developer or anyone with enough access generates certificate via Goggle Play Console as this prompts Google to reject all application release uploads signed by default Unity generated keystore.

Fortunately for you my dear reader after playing around with `keytool` CLI tool I was able to figure out the way to generate a keystore file signed by Google provided certificate and it can be achieved in two steps:


1. Generate keystore file: `keytool -genkey -keyalg RSA -storetype jks -alias release -validity 10000 -keysize 2048 -keystore stc-unity-android-key.jks`
2. Attach certificate to the keystore file: `keytool -export -rfc -alias release -file /home/jay/Downloads/upload_cert.der -keystore stc-unity-android-key.jks`

_Note: It is important to use JKS storetype, as it allows to create password signed aliases_

Thats it and as always, I hope you found this read useful.
