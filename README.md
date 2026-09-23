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

|No.|	Dork / Search Pattern	|Local Test Path|
|---|---|---|
|1	| inurl:"view.shtml" "Network Camera"	| /view.shtml/ |
|2	|intitle:"EvoCam" inurl:"webcam.html"	| /webcam.html/ |
|3	|intitle:"Live View / - AXIS"	| /axis/ |
|4	|intitle:"LiveView / - AXIS"  inurl:view/view.shtml |	/liveview/ |
|5	|inurl:indexFrame.shtml "Axis Video Server"	| /indexFrame.shtml/ |
|6	|inurl:axis-cgi/jpg |	/axis-cgi/jpg/ |
|7	|inurl:"MultiCameraFrame?Mode=Motion" |	/MultiCameraFrame/ |
|8	| inurl:/view.shtml	| /view/
|9	| inurl:/view/index.shtml	| /view/index.shtml |
|10 |	"my webcamXP server!"  |	/webcamXP/ |


## Results

All ten paths were successfully reproduced within the local laboratory environment.

The tests demonstrated how recognizable URL patterns and page structures can be associated with different camera-server technologies.

No third-party camera systems were accessed during this exercise.

## Evidence

Screenshots from the controlled Kali Linux laboratory are included below.

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/909f2487-6cd5-45f0-92b6-adc4d99f9f7d" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/8ca6ca1f-77c0-419f-944a-776c80f1b568" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/da0f0803-fa26-4ae7-937c-90733f4a51d4" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/58d5b3f0-58bc-4cb4-bf06-fe55b6846718" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/8c6cff46-317d-4854-95f3-916826622c11" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/598fc0b4-1c49-4504-8ba2-f43e71386d3d" />

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/66e54a53-c3da-4e79-af94-6a746eb31269" />


---

## Task 2 – Mathematics PDF Reconnaissance

### Objective

The objective of this task was to use Google dorking techniques to identify publicly indexed directories containing mathematics-related PDF resources.

The search focused on directory listings that could be discovered through the following query:

```text
intitle:index.of "parent directory" mathematics pdf
```
Methodology

The following procedure was used:

1. Open Google.
2. Enter the specified GHDB search query.
3. Examine the returned directory listings.
4. Open relevant directories.
5. Check the available files and identify mathematics-related PDF resources.
6. Record the directory URL and the search query used.
7. Exclude directories that did not contain relevant mathematics resources.

```text
intitle:index.of "parent directory" mathematics pdf
```

Results

The following publicly indexed directories were identified during the reconnaissance exercise:

| No. | Directory / Link                                                               | Relevant Dork                                         | Username / Password |
| --- | ------------------------------------------------------------------------------ | ----------------------------------------------------- | ------------------- |
| 1   | `http://erewhon.superkuh.com/library/Math/`                                    | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 2   | `https://justmathbg.info/files/`                                               | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 3   | `https://math.dartmouth.edu/~carlp/PDF/`                                       | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 4   | `/sl/vol2/Mathematics/Math.Encyclopedia/Pdf`                                   | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 5   | `https://www.math.utah.edu/~cherk/teach/5740MathModeling/12mathmodel/sources/` | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 6   | `https://www.learn-fo.com/FYUG%20mathematics%20solutions/`                     | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 7   | `/~dobelman/notes_papers/math`                                                 | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 8   | `https://secure.math.ubc.ca/Links/Putnam/`                                     | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 9   | `https://math.uchicago.edu/~shmuel/lg-readings/`                               | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |
| 10  | `/pdf/projectLearningTree`                                                     | `intitle:index.of "parent directory" mathematics pdf` | N/A                 |

## Task 2 – Evidence

The screenshot below document the directory listings identified during the reconnaissance exercise.

<img width="1920" height="964" alt="image" src="https://github.com/user-attachments/assets/6895e6e3-cd02-4370-9409-e38a7343c249" />


## Observations

The exercise demonstrated that search engines can index directory listings that expose information about files and resources hosted on web servers.
The filenames and directory structures provided useful information about the type of material available without requiring the use of specialized vulnerability-scanning tools.
No attempt was made to bypass authentication or access restricted resources. 

## Conclusion

This project provided practical experience with footprinting and reconnaissance using the Google Hacking Database and Google dorks.
The exercises demonstrated how search engines can index web resources based on specific patterns, including URL structures, page titles, and file types.
The project also reinforced an important cybersecurity principle: **the fact that a resource is publicly accessible does not necessarily mean that a person is authorized to interact with it.**
Using controlled environments and clearly defined authorization boundaries is therefore essential when practicing reconnaissance techniques.
