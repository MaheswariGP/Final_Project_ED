# Repository for final project

# Emotion Detection Application

A Python-based web application that analyzes a user's text and identifies five emotions — **anger, disgust, fear, joy, and sadness** — using the Watson NLP Emotion Detection service.

The application also determines the **dominant emotion** based on the highest emotion score.

## Project Overview

This project demonstrates how to:

* Build an emotion detection application using Python.
* Consume the Watson NLP Emotion Detection API.
* Create a reusable Python package.
* Handle invalid or blank user input.
* Create unit tests using Python's `unittest` framework.
* Build a web application using Flask.
* Deploy the application locally on `localhost:5000`.
* Perform static code analysis using PyLint.
* Package the application as `EmotionDetection`.

## Technologies Used

* Python 3
* Flask
* Requests
* Watson NLP Emotion Detection API
* unittest
* PyLint
* HTML
* JavaScript
* Git and GitHub

## Project Structure

```text
final_project/
│
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py
│
├── templates/
│   └── index.html
│
├── static/
│   └── mywebscript.js
│
├── test_emotion_detection.py
├── server.py
├── setup.py
└── README.md
```

## Emotion Detection

The application sends the user's text to the Watson NLP Emotion Detection service.

The following emotions are returned with their corresponding scores:

* Anger
* Disgust
* Fear
* Joy
* Sadness

The application then determines the dominant emotion.

For example:

```text
Input:
I love this new technology.

Output:
anger: ...
disgust: ...
fear: ...
joy: ...
sadness: ...
dominant_emotion: joy
```

## Installation

Clone the repository:

```bash
git clone https://github.com/MaheswariGP/Final_Project_ED.git
```

Move into the project directory:

```bash
cd Final_Project_ED
```

Install the required dependencies:

```bash
python3 -m pip install requests flask pylint
```

## Package Installation

The project is packaged as `EmotionDetection`.

Install the package using:

```bash
python3 -m pip install .
```

The package can then be imported using:

```python
from EmotionDetection import emotion_detector
```

## Running the Application

Start the Flask server:

```bash
python3 server.py
```

The application will run on:

```text
http://localhost:5000
```

Open the URL in a web browser to access the application.

## API Endpoint

The emotion detection endpoint is:

```text
/emotionDetector
```

Example:

```text
http://localhost:5000/emotionDetector?textToAnalyze=I%20love%20this%20new%20technology.
```

The application returns a response containing the emotion scores and dominant emotion.

Example:

```text
For the given statement, the system response is
'anger': 0.006274985,
'disgust': 0.0025598293,
'fear': 0.009251528,
'joy': 0.9680386
and 'sadness': 0.049744144.
The dominant emotion is joy.
```

## Error Handling

The application handles blank or invalid user input.

When the Watson NLP service returns a `400` status code, the `emotion_detector()` function returns:

```python
{
    "anger": None,
    "disgust": None,
    "fear": None,
    "joy": None,
    "sadness": None,
    "dominant_emotion": None
}
```

The Flask application then displays:

```text
Invalid text! Please try again!
```

## Unit Testing

The project includes unit tests for the five required emotions.

Run the tests using:

```bash
python3 -m unittest test_emotion_detection.py
```

The tests verify:

| Input                                    | Expected Dominant Emotion |
| ---------------------------------------- | ------------------------- |
| I am glad this happened                  | joy                       |
| I am really mad about this               | anger                     |
| I feel disgusted just hearing about this | disgust                   |
| I am so sad about this                   | sadness                   |
| I am really afraid that this will happen | fear                      |

A successful test run should display:

```text
.....
----------------------------------------------------------------------
Ran 5 tests

OK
```

## Static Code Analysis

PyLint is used to check the code quality of `server.py`.

Run:

```bash
pylint server.py
```

The target score for the project is:

```text
10.00/10
```

## Flask Application

The Flask application provides:

* A home page.
* An emotion detection endpoint.
* Integration with the `EmotionDetection` Python package.
* Error handling for invalid input.
* Human-readable emotion detection results.





