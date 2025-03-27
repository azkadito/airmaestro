# AirMaestro

AirMaestro is an application that uses computer vision to track hand movements in the air and generates music using the Notochord AI music generation model. Users can "conduct" music by moving their hands in the air, with Notochord generating improvised music responses based on these gestures.

## Features

- Real-time hand tracking using MediaPipe Hands
- Virtual piano keyboard visualization
- MIDI output for sound generation
- Integration with Notochord AI for musical improvisation
- Gesture-based musical interaction

## Requirements

- Python 3.7+
- OpenCV
- MediaPipe
- MIDI support (python-rtmidi or mido)
- Notochord (requires PyTorch)

## Installation

1. Clone this repository:
```bash
git clone https://github.com/azkadito/airmaestro.git
cd airmaestro
```

2. Install the required packages:
```bash
pip install -r requirements.txt
```

3. Download the Notochord model:
The application uses the Notochord model for AI music generation. The first time you run the application, it will prompt you to download the model if it's not already present.

## Usage

1. Run the main application:
```bash
python air_maestro.py
```

2. Position your hands above the camera, with your palms facing down toward the virtual keyboard shown on screen.

3. Move your fingers up and down to "play" in the air. The application will:
   - Track your fingertip movements
   - Register "presses" when your fingers make downward movements
   - Generate AI-improvised music based on these gestures using Notochord

4. Use the on-screen controls:
   - Press 'R' to reset the application
   - Press 'ESC' or 'Q' to quit

## Debugging

If you encounter issues with sound output, you can run the debug script to test MIDI functionality:
```bash
python debug_midi.py
```

## Configuration

The `config.py` file contains various settings that can be adjusted:
- Camera settings
- Piano keyboard display options
- Hand tracking sensitivity
- MIDI output configuration
- Notochord musical parameters (tempo, rhythm variation, etc.)

## How It Works

AirMaestro uses your hand gestures as musical inspiration rather than as direct note inputs. 
When you move your hands:

1. The system tracks the pitch register (high or low on the keyboard), velocity (hard or soft movements), and timing of your gestures
2. These gesture trends influence but don't directly determine the notes Notochord generates
3. Notochord produces a continuous musical output that follows your expressive contours while applying its musical intelligence

This creates a "maestro-like" experience where you conduct the AI rather than playing specific notes.

## License

[MIT License](LICENSE)

## Credits

- [Notochord](https://github.com/Intelligent-Instruments-Lab/notochord) - Neural music generation model
- [MediaPipe](https://mediapipe.dev/) - Hand tracking framework
- [OpenCV](https://opencv.org/) - Computer vision library