# Implementation of Speech Recognition

## AIM
Construct a python program to implement speech recognition.

## EQUIPMENTS REQUIRED:
Hardware – PCs
<br>
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook
## ALGORITHM
* Step 1: Import the speech_recognition module as sr.
* Step 2: Assign a string variable "file" with the name of the audio file that you want to transcribe.
* Step 3: Create an instance of the Recognizer class called "r".
* Step 4: Use the AudioFile() method of sr to create an AudioFile object with the audio file name passed as an argument.
* Step 5: Use the record() method of r to read the audio data from the AudioFile object and store it in the variable "audio".
* Step 6: Use the recognize_google() method of r to transcribe the audio data stored in the "audio" variable.
* Step 7: Print the transcribed text on the console if the transcribe process was successful.
* Step 8: Handle any potential errors during the transcribing process. If the audio is not clear, print "not clear". If there's an error while trying to retrieve the transcribed text from the Google speech recognizer, print "Couldnt get results from google speech recognizer".

## PROGRAM
```python3
import speech_recognition as sr

# Assign a string variable "file" with the name of the audio file that you want to transcribe.
file = "audio.wav"

# Create an instance of the Recognizer class called "r".
r = sr.Recognizer()

# Use the AudioFile() method of sr to create an AudioFile object with the audio file name passed as an argument.
with sr.AudioFile(file) as source:
    audio = r.record(source)

# Use the recognize_google() method of r to transcribe the audio data stored in the "audio" variable.
try:
    text = r.recognize_google(audio)
except sr.UnknownValueError:
    print("Not clear")
except sr.RequestError as e:
    print("Couldn't get results from Google Speech Recognition service; {0}".format(e))

# Print the text in the next lines.
for line in text.splitlines():
    print(line)
```

## OUTPUT
![image](https://github.com/Y-CHETHAN/Experiment-5--Implementation-of-Speech-Recognition/assets/75234991/b6ef501b-53b9-451a-b006-f2ec6876a1ed)
## RESULT
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
