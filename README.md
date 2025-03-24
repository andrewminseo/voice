# Voice Transcription App

A web-based voice transcription tool with live transcription, recording capabilities, and multiple interface modes.

**Live Demo:** [https://andrewminseo.github.io/voice/](https://andrewminseo.github.io/voice/)

## Features

### Real-time Transcription
- Convert speech to text instantly as you speak
- Support for multiple speakers with customizable profiles
- Press Tab to switch between speakers during recording


## How It Works

### Speech Recognition
The app uses the Web Speech API's SpeechRecognition interface to convert speech to text in real-time. 

```javascript
const recognition = new window.SpeechRecognition();
recognition.continuous = true;
recognition.interimResults = true;
```

### Audio Recording
The MediaRecorder API captures audio from your microphone while transcribing:

```javascript
const mediaRecorder = new MediaRecorder(stream);
mediaRecorder.ondataavailable = (event) => {
    audioChunks.push(event.data);
};
```

### Storage
- **IndexedDB:** Stores audio recordings locally in your browser
- **localStorage:** Saves your interface preferences

### Grammar Correction
Simple grammar correction engine fixes common errors as you speak:

- Capitalization of sentences and proper nouns
- Common contractions (don't, can't, I'm)
- Other common typing/speaking errors
- Does NOT do complex grammar correction.

## Privacy

This app processes all audio and text locally in your browser:
- No audio or transcripts are sent to any server
- All recordings are stored only on your device using IndexedDB
- Works offline after initial load

## Browser Compatibility

DOESNT WORK IN FIREFOX


## Technical Details


No frameworks or server-side processing required!
