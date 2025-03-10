# Voice Transcription App

A web-based voice transcription tool with live transcription, recording capabilities, and multiple interface modes.

**Live Demo:** [https://andrewminseo.github.io/voice/](https://andrewminseo.github.io/voice/)

## Features

### Real-time Transcription
- Convert speech to text instantly as you speak
- Support for multiple speakers with customizable profiles
- Press Tab to switch between speakers during recording

### Audio Recording
- Capture audio along with transcription
- Save recordings for future reference
- Download recordings as MP3 files

### Interface Modes
- **Standard Mode:** Clean, professional interface
- **Blue Light Filter:** Reduces eye strain in low light
- **Notepad Mode:** Discreet interface that resembles a simple note-taking app
- **Dark Mode:** Reduced eye strain in low-light environments

### Additional Features
- Automatic grammar correction
- Download transcripts as text files
- Copy text to clipboard
- Persistent storage of recordings

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

## Privacy

This app processes all audio and text locally in your browser:
- No audio or transcripts are sent to any server
- All recordings are stored only on your device using IndexedDB
- Works offline after initial load

## Browser Compatibility

Best experience in:
- Chrome
- Edge
- Safari

Speech recognition may have limited support in Firefox and other browsers.

## Usage Tips

1. **For best results:** Speak clearly and at a moderate pace
2. **Multiple speakers:** Add speaker profiles and use Tab to switch between speakers
3. **Discrete recording:** Use "Notepad" mode for a discreet interface that doesn't look like a recording app
4. **Save your work:** Download text and audio when finished

## Technical Details

The app is built with:
- Pure HTML, CSS, and JavaScript
- Web Speech API for transcription
- MediaRecorder API for audio capture
- IndexedDB for storage
- CSS custom properties for theming

No frameworks or server-side processing required!
