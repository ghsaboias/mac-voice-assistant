# Jarvis Assistant

This project is a voice assistant named Jarvis, designed for macOS. It uses speech recognition and text-to-speech to interact with your computer. The assistant can perform tasks such as:

- Opening new tabs in Brave Browser
- Navigating to websites
- Performing web searches using your default search engine
- Searching YouTube directly
- Managing browser tabs
- Logging activity for debugging purposes

## Project Structure

```
jarvis-assistant/
├── src/                      # Source code
│   ├── browser/             # Browser control
│   │   ├── __init__.py
│   │   └── brave_controller.py
│   ├── commands/            # Command parsing
│   │   ├── __init__.py
│   │   └── command_parser.py
│   ├── handlers/            # System interactions
│   │   ├── __init__.py
│   │   └── apple_script_handler.py
│   └── voice/              # Voice assistant core
│       ├── __init__.py
│       └── voice_assistant.py
├── main.py                  # Entry point
├── requirements.txt         # Dependencies
├── USER_FLOWS.md           # Command documentation
└── voice_assistant.log     # Activity logs
```

## Requirements

- **Operating System:** macOS
- **Python Version:** 3.11 or higher
- **Browser:** Brave Browser

### Core Libraries

The assistant uses several key Python libraries:

- **SpeechRecognition**: Converts spoken words to text using Google's Speech Recognition API
- **PyAudio**: Handles microphone input capture for speech recognition
- **pyttsx3**: Provides text-to-speech functionality for assistant responses

### Python Dependencies

Install the required Python packages using:

```bash
pip install -r requirements.txt
```

## Running the Voice Assistant

To start the voice assistant:

```bash
python main.py
```

## Usage

The assistant responds to voice commands prefixed with the wake word "Jarvis". See `USER_FLOWS.md` for a complete list of available commands and their variations.

Example commands:

- "Jarvis navigate to youtube"
- "Jarvis search python tutorials"
- "Jarvis youtube search cats"
- "Jarvis new tab"
- "Jarvis close tab"

## Configuration

The assistant is configured through several components:

- `CommandTriggers`: Defines command patterns
- `BraveController`: Manages browser interactions
- `MacVoiceAssistant`: Core assistant functionality

## Voice Processing

The assistant uses a pipeline of voice processing components:

1. **Speech Input**: PyAudio captures microphone input
2. **Speech Recognition**: Google's Speech Recognition API converts audio to text
3. **Command Processing**: Pattern matching identifies and validates commands
4. **Text-to-Speech**: pyttsx3 converts responses to spoken audio

## Logging

The assistant logs to both console and `voice_assistant.log`, including:

- Command processing
- Speech recognition
- Error handling
- System interactions

## System Requirements

- Microphone access permissions
- Network connection for speech recognition
- Brave Browser installation
- macOS system permissions for automation

## License

This project is open-source. Feel free to modify and distribute it.
