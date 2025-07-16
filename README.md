# StompJumpSmash

## Project Summary
**Stomp Jump Smash** is an interactive augmented reality platformer inspired by *Super Mario Bros*.  
In this game, the **player’s live body** is captured by a webcam, segmented using computer vision, and composited directly into a scrolling Mario-like game world.  
The player jumps, stomps, or smashes blocks and enemies using **real-world body movements** tracked with OpenCV and pose detection.


## Key Features
- Live webcam video feed — the player becomes the in-game character.  
- Full-body tracking for jumps, stomps, and arm swings.  
- Background subtraction or chroma keying for player segmentation.  
- Classic platformer mechanics: blocks, coins, simple enemies.  
- Game world rendered with **openFrameworks**, composited with the player feed.  
- Output displayed on a projector for an immersive experience.


## System Architecture

### **1. Input**
- **Camera Input:** Captures live video.
- **OpenCV:**  
  - Performs background subtraction or chroma keying.
  - Uses **Mediapipe** or **OpenPose** for real-time body pose detection.


### **2. Processing**
- **Action Detection:**  
  - Jump → detect upward hip/feet motion.  
  - Stomp → detect downward foot motion.  
  - Arm swing → detect lateral hand motion.  
  - Head bump → detect upward head motion.
- **Collision Logic:**  
  - Checks overlap between player keypoints and game objects.


### **3. Output**
- **openFrameworks:**  
  - Renders game world, platforms, enemies, and blocks.  
  - Composites the player’s segmented video into the scene.  
  - Handles physics and game interactions.
- **Projector:** Displays the final composited scene onto a screen or wall.


## Tools & Libraries
- **Language:** C++
- **Framework:** openFrameworks
- **Computer Vision:** OpenCV (`ofxOpenCv`)
- **Pose Detection:** Mediapipe (recommended) or OpenPose
- **Projection:** Standard projector or large display


## How It Works
1. Player stands in front of the camera.
2. OpenCV captures and segments the player’s body.
3. Pose detection determines if the player jumps, stomps, or swings.
4. Actions map to in-game interactions (breaking blocks, stomping enemies).
5. openFrameworks renders the final scene and composited player.
6. Projector displays the game so the player sees themselves in the world.


## References
- [openFrameworks Documentation](https://openframeworks.cc/)
- [OpenCV Docs](https://docs.opencv.org/)
- [Mediapipe Pose](https://google.github.io/mediapipe/solutions/pose)


## Credits
- **Developer:** *Elizabeth*
- Inspired by *Super Mario Bros* (Nintendo)




