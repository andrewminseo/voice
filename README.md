# Voice Transcription App

A web-based voice transcription tool with live transcription, recording capabilities

**Live Demo:** [https://andrewminseo.github.io/voice/](https://andrewminseo.github.io/voice/)


## How It Works

Web Speech API's SpeechRecognition interface to converts speech to text in real-time. 

```javascript
const recognition = new window.SpeechRecognition();
recognition.continuous = true;
recognition.interimResults = true;
```

MediaRecorder API captures audio from your microphone while transcribing.

```javascript
const mediaRecorder = new MediaRecorder(stream);
mediaRecorder.ondataavailable = (event) => {
    audioChunks.push(event.data);
};
```


## Browser Compatibility

DOESNT WORK IN FIREFOX


