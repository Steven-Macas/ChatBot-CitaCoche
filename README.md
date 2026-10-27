<div align="center">

# CitaCoche Chatbot

**An Android chatbot that understands natural language with Dialogflow**

<img src="https://img.shields.io/badge/Java-Android-E76F00?style=flat-square" alt="Java: Android" /> <img src="https://img.shields.io/badge/Android-Studio-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Android: Studio" /> <img src="https://img.shields.io/badge/Dialogflow-ES-FF9800?style=flat-square&logo=dialogflow&logoColor=white" alt="Dialogflow: ES" />

</div>

## Overview

**CitaCoche** ("car appointment") is an Android app written in **Java** with a chat interface.
Each message the user types is sent to a **Dialogflow** agent, which detects the intent of the sentence
and returns the most appropriate answer to help the user with car service appointments.
The conversation runs in Spanish (`es-ES`).

## How it works

1. The user writes a message in the chat screen (`MainActivity`).
2. The app authenticates against Google Cloud with a service account and opens a Dialogflow session.
3. The message is sent with `DetectIntent` (Dialogflow ES API v2).
4. The agent matches the intent and the response is shown in the conversation.

## Tech stack

- Java · Android SDK (AppCompat, Material Components)
- `com.google.cloud:google-cloud-dialogflow` 4.22.0
- `com.google.auth:google-auth-library-oauth2-http` and gRPC (OkHttp)

## Repository structure

| Path | Description |
| --- | --- |
| `app/src/main/java/com/example/gframe/MainActivity.java` | Chat screen and Dialogflow integration |
| `app/src/main/res/layout/activity_main.xml` | Chat layout |
| `app/src/main/res/raw/` | Location of the service-account key used to call Dialogflow |
| `app/build.gradle` | Dependencies |

## How to run

1. Create an agent in [Dialogflow ES](https://dialogflow.cloud.google.com/) with your intents and answers.
2. In Google Cloud, create a service account with the **Dialogflow API Client** role and download a JSON key.
3. Save the key as `app/src/main/res/raw/client.json`. The key is not included in this repository and that path is listed in `.gitignore`, so it is never committed.
4. Open the project in **Android Studio**, sync Gradle and run the app on an emulator or device.

---

<sub>Made by <b>Steven Macas</b> — Data Engineer &amp; Data Analyst · <a href="https://gointy.com">gointy.com</a> · <a href="https://www.linkedin.com/in/steven-macas">LinkedIn</a> · <a href="https://github.com/Steven-Macas">GitHub</a></sub>
