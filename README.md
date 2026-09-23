# Footprinting & Reconnaissance Attacks with GHDB

## Week 2 – Project Module 2

### Project Overview

This project demonstrates fundamental footprinting and reconnaissance techniques using the **Google Hacking Database (GHDB)** and Google search operators, commonly known as Google dorks.

The practical activities covered two reconnaissance exercises:

1. Identifying camera-related web interfaces using GHDB search queries.
2. Identifying publicly indexed directories containing mathematics-related PDF resources.

All activities were performed for educational and authorized cybersecurity research purposes.

> **Ethical Disclaimer:** The camera reconnaissance exercise was performed in a controlled local Kali Linux laboratory environment. No unauthorized access to third-party security cameras was performed.

---

## Objectives

- Understand the fundamentals of footprinting and reconnaissance.
- Learn how to use the Google Hacking Database (GHDB).
- Understand and apply Google dorks.
- Identify publicly indexed web resources using search operators.
- Practice reconnaissance techniques in a controlled environment.
- Document findings and observations.
- Understand the ethical and security implications of exposed resources.

---

## Tools & Environment

- Kali Linux
- VirtualBox
- Google
- Google Hacking Database (GHDB)
- Python 3
- GitHub

---

## Project Tasks

### Task 1 – Camera Reconnaissance

The first task involved studying GHDB queries associated with publicly indexed camera interfaces.

Because accessing an unknown third-party camera without authorization would be inappropriate, the camera-related portion was reproduced using a **controlled local web server in Kali Linux**.

### Task 2 – Mathematics PDF Reconnaissance

The second task involved using a Google dork to identify publicly indexed directories containing mathematics-related PDF resources.

The primary search query used was:

```text
intitle:index.of "parent directory" mathematics pdf
```

## Ethical Considerations

Footprinting and reconnaissance techniques can be useful for security research, vulnerability assessment, and information gathering. However, publicly accessible information does not automatically mean that a system is authorized for testing.

All testing in this project was therefore limited to authorized and controlled environments.

---

## Task 1 – Camera Reconnaissance

### Objective

The objective of this task was to investigate GHDB search queries associated with exposed web-camera interfaces.

The GHDB contains search queries that can be used to identify web pages matching particular patterns. During the practical, several camera-related dorks were studied.

Because testing unknown Internet-connected cameras without authorization would be inappropriate, the practical was reproduced in a controlled Kali Linux laboratory environment.

### Lab Environment

The laboratory was created using:

- Kali Linux running in VirtualBox
- A local Python HTTP server
- Port `8080`
- Localhost (`127.0.0.1`)

The HTTP server was started using:

```bash
python3 -m http.server 8080
```
The resulting web interfaces were accessed through the local browser.


GHDB Dorks Used

The following camera-related search patterns were reproduced in the authorized laboratory:

No.|	Dork / Search Pattern	|Local Test Path
|-|-|
1	| inurl:"view.shtml" "Network Camera"	| /view.shtml/
2	|intitle:"EvoCam" inurl:"webcam.html"	|/webcam.html/
3	|intitle:"Live View / - AXIS"	|/axis/
4	|intitle:"LiveView / - AXIS"  inurl:view/view.shtml |	/liveview/
5	|inurl:indexFrame.shtml "Axis Video Server"	| /indexFrame.shtml/
6	|inurl:axis-cgi/jpg |	/axis-cgi/jpg/
7	|inurl:"MultiCameraFrame?Mode=Motion" |	/MultiCameraFrame/
8	|inurl:/view.shtml	| /view/
9	|inurl:/view/index.shtml	| /view/index.shtml
10|	"my webcamXP server!"  |	/webcamXP/
