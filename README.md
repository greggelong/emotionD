# 🎭 Emotional Surveillance System

A real-time facial emotion detection web application with a dystopian surveillance aesthetic. Built with face-api.js and TensorFlow.js.

## 📋 Description

This project uses computer vision to detect 7 human emotions from webcam feed in real-time:

- 😊 Happy (快乐) - MANIC
- 😢 Sad (悲伤) - DEPRESSED
- 😠 Angry (愤怒) - HOSTILE
- 😲 Surprise (惊讶) - ALERT
- 😨 Fear (恐惧) - TERMINAL
- 🤢 Disgust (厌恶) - REJECT
- 😐 Neutral (中性) - BASELINE

## 🔄 Processing Pipeline

### 1. **Face Detection** - `tinyFaceDetector`

- Lightweight model (190KB) optimized for real-time performance
- Depthwise separable convolutions for speed
- Detects face bounding boxes with confidence scores
- Configured with `inputSize: 224` and `scoreThreshold: 0.3`

### 2. **Facial Landmark Detection** - `faceLandmark68TinyNet`

- 68-point face landmark model (80KB)
- Identifies key facial features (eyes, nose, mouth, jawline)
- Enables face alignment for better emotion accuracy

### 3. **Expression Classification** - `faceExpressionNet`

- 310KB model trained on diverse emotion datasets
- Depthwise separable convolutions with densely connected blocks
- Outputs probabilities for 7 emotion classes
- Dominant emotion selected via highest confidence score

### 4. **Visual Rendering Pipeline**

- Canvas transformation for mirrored display
- Color-coded bounding boxes with emotion labels
- 10% opacity face overlays for surveillance aesthetic
- Real-time stats overlay with detection metrics

### 5. **Performance Loop**

- Async detection at ~10 FPS using `requestAnimationFrame`
- Prevents UI blocking with proper state management
- Fallback handling for detection errors

## ✨ Features

- **Real-time emotion detection** using pre-trained models
- **Dystopian UI** with CRT scanlines, glitch effects, and surveillance aesthetics
- **Bilingual labels** (English + Chinese) with dystopian status codes
- **Mobile-responsive** design that works on phones and computers
- **Live stats** showing detection confidence and frame count
- **Color-coded overlays** with transparent face tints matching detected emotions

## 🛠️ Technologies Used

- [face-api.js](https://github.com/justadudewhohacks/face-api.js) - JavaScript face recognition API
- TensorFlow.js - Machine learning backend
- HTML5/CSS3 - Responsive design with animations
- WebRTC - Webcam access

## 🚀 How to Use

1. Open the HTML file in any modern browser (Chrome, Firefox, Edge, Safari)
2. Allow camera access when prompted
3. Wait for models to load (few seconds)
4. Look at the camera - your emotion will be detected and displayed!

## 📁 Files Needed

Just one HTML file! The models load automatically from CDN (jsDelivr for China-friendly access).

## 📊 Model Sizes

| Model                | Size      | Purpose                |
| -------------------- | --------- | ---------------------- |
| Tiny Face Detector   | 190KB     | Face detection         |
| Face Landmark (tiny) | 80KB      | Facial feature points  |
| Face Expression Net  | 310KB     | Emotion classification |
| **Total**            | **580KB** | -                      |

## 🔧 Customization

You can easily modify:

- **Colors** - Change the `colors` object in JavaScript
- **Text** - Update the legend labels or status messages
- **Opacity** - Adjust the `'1A'` hex value for face overlay transparency
- **Detection speed** - Modify the `inputSize` and `scoreThreshold` options

## 📱 Browser Support

Works on all modern browsers including Chrome, Firefox, Safari, and Edge. Mobile support optimized for recent iOS and Android devices.

## ⚠️ Note

This is a client-side application - no data is sent to any server. All processing happens locally in your browser.

---

_"You are being emotionally monitored"_
