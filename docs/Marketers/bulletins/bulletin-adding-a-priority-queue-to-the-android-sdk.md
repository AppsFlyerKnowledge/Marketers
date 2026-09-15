---
title: "Bulletin: Adding a priority queue to the Android SDK"
excerpt: "Learn about the priority queue changes introduced in Android SDK version 6.7.0 to ensure in-app events are sent in the correct order."
---
> 📘 What's new
>
> In version 6.7.0 we introduced some changes to the way the SDK is handling the various requests to the AppsFlyer servers.
> We've noticed that there are apps that try and send in-app events before they have started the SDK. By introducing this change, we're making sure things are executed in the right order.

> 📘 What's changing
>
> **Before the change**: In earlier versions of the SDK, the app could send in-app events to AppsFlyer before calling the SDK’s `start` method (which means before the conversion was sent to the server).
>
> **After the change**: Starting with this version, the conversion request is prioritized and all the in-app events that take place before calling `start` are stored and wait for the conversion request to be sent.