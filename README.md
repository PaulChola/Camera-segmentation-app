Object Detection and Avoidance App for the Visually Impaired

This Android application is designed to assist visually impaired individuals by detecting objects in their path and providing real-time audio feedback to avoid obstacles. The app uses TensorFlow Lite for object detection and CameraX for capturing live video feed from the device's camera. Detected objects are announced through Text-to-Speech (TTS), helping users navigate their surroundings safely.
Features

    Real-time Object Detection: Uses TensorFlow Lite to detect objects from the device's camera feed.
    Obstacle Warning: Provides real-time audio feedback (Text-to-Speech) when obstacles are detected ahead.
    Lightweight: TensorFlow Lite ensures efficient model inference with low latency.
    Easy to Use: Automatically starts camera feed and provides feedback without the need for manual intervention.

Prerequisites

Before you begin, ensure you have met the following requirements:

    Android Studio (version 2021.1.1 or above)
    Android SDK with minimum API level 21
    A physical Android device with a camera (emulator won't support real-time camera features effectively)
    Basic understanding of Android development, Kotlin, and machine learning concepts

Getting Started

Follow these instructions to set up the project and run the application on your device.
1. Clone the Repository

Clone this repository using the following command:

bash

git clone https://github.com/your-username/object-detection-app.git

2. Open in Android Studio

    Open Android Studio and select File > Open.
    Navigate to the project directory you just cloned.
    Wait for Android Studio to sync the project and install the required dependencies.

3. Install Dependencies

The following dependencies are used in the project:

    TensorFlow Lite: For running machine learning models on Android.
    CameraX: For accessing the device's camera.
    Text-to-Speech (TTS): For providing real-time audio feedback.
    Compose: Jetpack Compose for modern Android UI design.

Ensure that your build.gradle.kts includes the following dependencies:

kotlin

dependencies {
    implementation("org.tensorflow:tensorflow-lite:2.6.0")
    implementation("org.tensorflow:tensorflow-lite-support:0.3.1")
    implementation("androidx.camera:camera-core:1.1.0")
    implementation("androidx.camera:camera-camera2:1.1.0")
    implementation("androidx.camera:camera-view:1.1.0")
    implementation("androidx.camera:camera-lifecycle:1.1.0")
    implementation("android.speech.tts.TextToSpeech")
    implementation("androidx.core:core-ktx:1.12.0")
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.6.2")
}

4. TensorFlow Lite Model

Ensure you have a TensorFlow Lite model file (model.tflite) in the assets directory. If you don't have a model, you can either train a custom model or download a pre-trained object detection model (e.g., MobileNet SSD) compatible with TensorFlow Lite.

Place your model in the following directory:

css

app/src/main/assets/model.tflite

5. Running the App

    Connect a physical Android device and enable USB Debugging.
    Click Run in Android Studio or use the command:

bash

./gradlew installDebug

    The app will launch on the device and start the camera feed.
    As objects are detected, the app will provide audio feedback indicating the presence of obstacles.

How It Works

    The app captures live video feed using CameraX.
    Each frame is analyzed in real time by a TensorFlow Lite object detection model.
    When an obstacle is detected with confidence higher than a threshold, the app uses the device's Text-to-Speech engine to notify the user about the obstacle.

Project Structure

bash

/app
├── src
│   ├── main
│   │   ├── java/com/example/navigationapp
│   │   │   └── MainActivity.kt           # Main activity that handles CameraX and TensorFlow Lite
│   │   ├── res                           # Resource files (layouts, icons, etc.)
│   │   ├── assets/model.tflite           # TensorFlow Lite model
│   │   └── AndroidManifest.xml            # Android app manifest file
├── build.gradle.kts                      # Gradle configuration file (Kotlin DSL)
└── README.md                             # Project readme file (this file)

License

This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgements

    TensorFlow Lite
    Android CameraX
    Text-to-Speech (TTS)
