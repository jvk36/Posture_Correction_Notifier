Consider setting up this project under an environment:

### python -m venv .env
### 
### # Activate the virtual environment
### source .env/Scripts/activate OR source .env/bin/activate 
### # Deactivate the virtual environment
### source .env/Scripts/deactivate

Statement of Product Market Fit:

There are products in the market that use slow robots to automatically and unobtrusively do posture correction. They rely on co-robot hardware attached to the desk/monitor. The basic idea was based on a paper titled "Slow Robots for Unobtrusive Posture Correction" presented at the ACM CHI Conference on Human Factors in Computing Systems held in Glasgow, Scotland. 

One drawback identified in this solution was that “frequent posture changes” rather than permanently sitting in a “balanced posture” is more beneficial. 

This App is aimed at fixing this drawback while also being unobtrusive and also without requiring additional hardware. 

Basic Functionality of the App:

The core idea of this software is to analyze the images from the webcam to figure out posture changes. if the system identifies that the posture has not changed in a while, it provides a simple notification suggesting a posture change. 

The user’s face is detected using the computer’s webcam. Every few seconds, the snapshot from the webcam is analyzed to identify the frame of the user’s face. It then checks whether the user has gone out of the “safe zone” by analyzing the relative position of the eyes. If a persistent (more than 30 seconds) posture change is detected within a period of 10 minutes, it means the user has changed posture and so the application resets the timer. OTOH, if no change is detected over that period, a notification is given to the user suggesting a posture change. 

Overall Results: 

This project helps people correct posture in an unobtrusive manner. It does a gentle unobtrusive desktop notification when suggesting a posture change. Background noises are ok, but the software can get confused if multiple people are looking at the same screen. It can be useful to most desktop users. Also, the software can accurately detect posture, independent of whether the person is blinking or doing any other type of eye movement.

Future Considerations for Further Work: 

1.	Detecting the face/eyes from webcam images can be a challenge in some situations - low-light conditions, eye detection with eye glasses, etc. This could be improved by optimizing the image processing algorithm. 
2.	Eliminating false-positives can be a challenge in some cases. Example - the face/eye positions have not changed but the rest of the body has moved. Enhancing the detection mechanism to monitor the shoulder position is a solution to this issue that can be considered, and 
3.	Eliminating false-negatives is a challenge. Example - face/eye positions have changed because the user is tired. In this case, an ideal solution should suggest a break. Detecting eye-blinking and adding logic to provide feedback through notifications is a solution to this issue that can be considered.

References

1.	https://realpython.com/face-detection-in-python-using-a-webcam/ 
2.	https://towardsdatascience.com/create-desktop-notifier-application-using-python-fb3b7b2c3cf3
3.	https://machinelearningmastery.com/how-to-perform-face-detection-with-classical-and-deep-learning-methods-in-python-with-keras/
4.	https://github.com/kipr/opencv 
