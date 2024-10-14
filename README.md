<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Object Detection and Avoidance App</title>
</head>
<body>

<h1>Object Detection and Avoidance App for the Visually Impaired</h1>

<p>This Android application is designed to assist visually impaired individuals by detecting objects in their path and providing real-time audio feedback to avoid obstacles. The app uses <strong>TensorFlow Lite</strong> for object detection and <strong>CameraX</strong> for capturing live video feed from the device's camera. Detected objects are announced through Text-to-Speech (TTS), helping users navigate their surroundings safely.</p>

<h2>Features</h2>
<ul>
    <li><strong>Real-time Object Detection</strong>: Uses TensorFlow Lite to detect objects from the device's camera feed.</li>
    <li><strong>Obstacle Warning</strong>: Provides real-time audio feedback (Text-to-Speech) when obstacles are detected ahead.</li>
    <li><strong>Lightweight</strong>: TensorFlow Lite ensures efficient model inference with low latency.</li>
    <li><strong>Easy to Use</strong>: Automatically starts camera feed and provides feedback without the need for manual intervention.</li>
</ul>

<h2>Prerequisites</h2>
<p>Before you begin, ensure you have met the following requirements:</p>
<ul>
    <li><strong>Android Studio</strong> (version 2021.1.1 or above)</li>
    <li><strong>Android SDK</strong> with minimum <strong>API level 21</strong></li>
    <li>A <strong>physical Android device</strong> with a camera (emulator won't support real-time camera features effectively)</li>
    <li>Basic understanding of Android development, Kotlin, and machine learning concepts</li>
</ul>

<h2>Getting Started</h2>
<p>Follow these instructions to set up the project and run the application on your device.</p>

<h3>1. Clone the Repository</h3>
<p>Clone this repository using the following command:</p>

<pre><code>git clone https://github.com/your-username/object-detection-app.git
</code></pre>

<h3>2. Open in Android Studio</h3>
<ol>
    <li>Open <strong>Android Studio</strong> and select <strong>File</strong> &gt; <strong>Open</strong>.</li>
    <li>Navigate to the project directory you just cloned.</li>
    <li>Wait for Android Studio to sync the project and install the required dependencies.</li>
</ol>

<h3>3. Install Dependencies</h3>
<p>The following dependencies are used in the project:</p>

<pre><code>
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
</code></pre>

<h3>4. TensorFlow Lite Model</h3>
<p>Ensure you have a TensorFlow Lite model file (<code>model.tflite</code>) in the <code>assets</code> directory. If you don't have a model, you can either train a custom model or download a pre-trained object detection model (e.g., MobileNet SSD) compatible with TensorFlow Lite.</p>

<p>Place your model in the following directory:</p>

<pre><code>app/src/main/assets/model.tflite
</code></pre>

<h3>5. Running the App</h3>
<ol>
    <li><strong>Connect a physical Android device</strong> and enable <strong>USB Debugging</strong>.</li>
    <li>Click <strong>Run</strong> in Android Studio or use the command:</li>
</ol>

<pre><code>./gradlew installDebug
</code></pre>

<ol start="3">
    <li>The app will launch on the device and start the camera feed.</li>
    <li>As objects are detected, the app will provide audio feedback indicating the presence of obstacles.</li>
</ol>

<h2>How It Works</h2>
<p>The app captures live video feed using <strong>CameraX</strong>. Each frame is analyzed in real time by a <strong>TensorFlow Lite</strong> object detection model. When an obstacle is detected with confidence higher than a threshold, the app uses the device's <strong>Text-to-Speech</strong> engine to notify the user about the obstacle.</p>

<h2>Project Structure</h2>

<pre><code>
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
</code></pre>

<h2>License</h2>
<p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>

<h2>Acknowledgements</h2>
<ul>
    <li><a href="https://www.tensorflow.org/lite">TensorFlow Lite</a></li>
    <li><a href="https://developer.android.com/training/camerax">Android CameraX</a></li>
    <li><a href="https://developer.android.com/reference/android/speech/tts/TextToSpeech">Text-to-Speech (TTS)</a></li>
</ul>

</body>
</html>
