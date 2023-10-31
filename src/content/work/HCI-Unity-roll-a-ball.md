---
title: Roll-a-ball Unity Tutorial
publishDate: 2020-03-02 00:00:00
img: /assets/thumbnails/roll-a-ball-thumbnail.png
img_alt: a personn scanning a document whith his phone
description: A Comprehensive Guide - Dive into the world of game development with Unity's beginner-friendly Roll-a-Ball tutorial. This guide will walk you through each step, ensuring you grasp the basics and more!
tags:
  - Unity
  - Game Devolpement for VR
---

### Table of Contents
| Section                                          | Description                                 |
|--------------------------------------------------|---------------------------------------------|
| 1. [Setting Up the Project](#setting-up-the-project)            | Starting a new Unity project.               |
| 2. [Designing the Game Arena](#designing-the-game-arena)        | Creating the main play area.                |
| 3. [Introducing the Player Ball](#introducing-the-player-ball)  | Adding and setting up the player object.    |
| 4. [Making the Ball Move](#making-the-ball-move)                | Scripting the player's movement.            |
| 5. [Introducing Collectible Objects](#introducing-collectible-objects) | Placing and scripting collectibles.       |
| 6. [Adding the Enemy (Evil) Object](#adding-the-enemy-evil-object) | Introducing obstacles in the game.       |
| 7. [Implementing the Mini-Map](#implementing-the-mini-map)      | Adding a top-down view of the game.         |
| 8. [Winning the Game](#winning-the-game)                        | Displaying the player's progress and victory.|
| 9. [Wrapping Up](#wrapping-up)                                  | Concluding the tutorial and next steps.     |
| 10. [Adapting your game to VR](#Adapting-your-game-to-VR)                                  | See how you could adapt your game to VR     |

---

### Setting Up the Project
Step 1: Launch Unity Hub. Click on New to start a fresh project.

Step 2: Name your project "Roll-a-Ball" and choose your desired save location.


<img src='/assets/images/HCI-roll-a-ball/unity-hub.png' alt='unity hub for my project' style='width: 100%;'>


---

### Designing the Game Arena
**Step 1:** In the Hierarchy panel, right-click and select 3D Object > Plane. This serves as our game floor.

**Step 2:** Adjust the plane's scale to 2x2 to provide ample space for gameplay.

<div style='text-align:center;'>
    <img src='/assets/images/HCI-roll-a-ball/arena.png' alt='simple arena' style='width: 70%;'>
</div>

---

### Introducing the Player Ball
**Step 1:** Add a sphere by right-clicking in the Hierarchy and selecting 3D Object > Sphere.

**Step 2:** Elevate the sphere slightly above the plane to ensure smooth movement.

<div style='text-align:center;'>
    <img src='/assets/images/HCI-roll-a-ball/player-ball.png' alt='simple arena' style='width: 70%;'>
</div>

---

### Making the Ball Move
**Step 1:** Select the sphere. In the Inspector, click Add Component and choose Rigidbody for physics-based movement.

**Step 2:** Create a new script named "PlayerController". Attach this to the sphere.

**Step 3:** Script the movement. Use the Rigidbody's AddForce method to apply movement based on player input.

```csharp
 // This function is called when a move input is detected.
    void OnMove(InputValue movementValue)
    {
        // Convert the input value into a Vector2 for movement.
        Vector2 movementVector = movementValue.Get<Vector2>();

        // Store the X and Y components of the movement.
        movementX = movementVector.x;
        movementY = movementVector.y;
    }

    // FixedUpdate is called once per fixed frame-rate frame.
    private void FixedUpdate()
    {
        // Create a 3D movement vector using the X and Y inputs.
        Vector3 movement = new Vector3(movementX, 0.0f, movementY);

        // Apply force to the Rigidbody to move the player.
        rb.AddForce(movement * speed);
    }
```

---

### Introducing Collectible Objects
**Step 1:** Create smaller cubes as collectibles. Use prefabs to be able to generalize them and modify them all at once.

**Step 2:** Scatter them throughout the game arena.

**Step 3:** Modify the "PlayerController" script. Add collision detection to "collect" these objects when the player ball touches them.

```csharp
void OnTriggerEnter(Collider other)
    {
        // Check if the object the player collided with has the "PickUp" tag.
        if (other.gameObject.CompareTag("PickUp"))
        {
            // Deactivate the collided object (making it disappear).
            other.gameObject.SetActive(false);

            // Increment the count of "PickUp" objects collected.
            count = count + 1;

            // Update the count display.
            SetCountText();
        }
    }
```

**step 4 :** Add the pickUp tag to the collectibles so the srcipts knows what to activate.
And don't forget to tick the on trigger box in the box collider

<div style='text-align:center;'>
    <img src='/assets/images/HCI-roll-a-ball/pickup.png' alt='simple arena' style='width: 70%;'>
</div>

---

### Adding the Enemy (Evil) Object
**Step 1:** Introduce a new object (e.g., a cube) to act as the enemy or "Evil" object.

**Step 2:** Position it strategically in the game arena.

**Step 3:** Update the "PlayerController" script to recognize collisions with the enemy, triggering a game over or similar event.

**step 5 :** Add the evil tag to the collectibles so the srcipts knows what to activate.
And don't forget to tick the on trigger box in the box collider

**UI design :** The basic components I added to the UI; are a counter, to keep track of the number of collectables. And a "you lose" message when you touch an enemi.

```csharp
if (other.gameObject.CompareTag("Evil"))
        {
            loseTextObject.SetActive(true);
        }
```

<div style='text-align:center;'>
    <img src='/assets/images/HCI-roll-a-ball/evil.png' alt='simple arena' style='width: 70%;'>
</div>

---

### Implementing the Mini-Map
**Step 1:** Create a new camera for the mini-map. Position it above the game arena, looking downward.

**Step 2:** Adjust the camera's Culling Mask to display only relevant game objects.

**Step 3:** In the UI, add a Raw Image element. This will display the mini-map.

**Step 4:** Link the mini-map camera's output to this Raw Image using a Render Texture.

<div style='display: flex; justify-content: center;'>
    <img src='/assets/images/HCI-roll-a-ball/minimap-1.png' alt='simple arena' style='width: 50%;'>
    <img src='/assets/images/HCI-roll-a-ball/minimap-2.png' alt='simple arena' style='width: 50%; margin-left: 5px;'>
</div>

You can that on the second picture, the collectables have disapered from the mini-map (the count has incresed) and the ball is in a different location.

---

### Winning the Game
**Step 1:** Introduce a UI Text element to display the player's score. By adding a Canva and an Eventsystem to the herarchy

**Step 2:** As collectibles are gathered, update this score.

```csharp
void OnTriggerEnter(Collider other)
    {
        // Check if the object the player collided with has the "PickUp" tag.
        if (other.gameObject.CompareTag("PickUp"))
        {
            //...

            // Increment the count of "PickUp" objects collected.
            count = count + 1;

            // Update the count display.
            SetCountText();
        }
            //...
    }
            //...

    // Function to update the displayed count of "PickUp" objects collected.
void SetCountText()
    {
    // Update the count text with the current count.
    countText.text = "Count: " + count.ToString();

    }

```

**Step 3:** When all collectibles are collected, display a victory message.


<div style='display: flex; justify-content: center;'>
    <img src='/assets/images/HCI-roll-a-ball/gameplay-1.png' alt='gamplay1' style='width: 33%;'>
    <img src='/assets/images/HCI-roll-a-ball/gameplay-win.png' alt='gameplay2' style='width: 33%; margin-left: 5px;'>
    <img src='/assets/images/HCI-roll-a-ball/gameplay-lose.png' alt='gameplay3' style='width: 33%; margin-left: 5px;'>
</div>


---

### Wrapping Up
Congratulations on building your Roll-a-Ball game with added features! This foundation sets the stage for more complex games. Experiment, iterate, and most importantly, have fun!

This expanded tutorial now provides a more detailed walkthrough, including the mini-map addition. Remember to replace the "Insert Image" placeholders with relevant visuals to enhance the tutorial's clarity and appeal.

---

### Adapting your game to VR

Adapting a Unity game like Roll-a-Ball to Virtual Reality (VR) involves several steps. Below is a step-by-step tutorial to guide you through the process. This tutorial assumes you have a basic understanding of Unity and have completed the Roll-a-Ball project or something similar.

#### Prerequisites:
- Unity Hub and Unity Editor installed (preferably the latest version)
- A completed Roll-a-Ball project or similar
- A VR headset compatible with Unity (e.g., Oculus Rift, HTC Vive)
- VR SDKs installed (e.g., Oculus, OpenVR)

#### Steps:
1. Install VR Packages:
Open your Roll-a-Ball project in Unity.
Go to Window > Package Manager.
Search for "XR Plugin Management" and install it.

2. Enable XR Plugin Management:
Go to Edit > Project Settings.
In the Project Settings window, select XR Plugin Management.
Check the box for your desired platform (Oculus, OpenVR, etc.).

3. Update Camera:
In the Unity hierarchy, find your Main Camera.
Delete the Main Camera as we'll be using the VR camera rig.
Import the VR camera rig related to your SDK (e.g., for Oculus, you might use the OVRCameraRig prefab).

4. Update Player Controller:
Attach your player control script (e.g., PlayerController) to the VR camera rig or one of its child objects.
Update the script to use VR inputs. For example, you might use the thumbstick or touchpad to move the ball.

```csharp
void Update()
{
    // Example for Oculus Touch thumbstick
    Vector2 thumbstick = OVRInput.Get(OVRInput.Axis2D.PrimaryThumbstick);
    movementX = thumbstick.x;
    movementY = thumbstick.y;
    // ... (rest of your code)
}
```

1. Test in VR:
Save your scene and project.
Put on your VR headset and make sure it's set up correctly.
Press the Play button in Unity to test the game in VR.

2. Fine-Tuning:
You may need to adjust the scale and positioning of game objects to better suit the VR perspective.
Test extensively to ensure that the controls feel intuitive and that the game is comfortable to play in VR.

3. Build for VR:
Go to File > Build Settings.
Add your scenes and select your target platform.
Click Build and follow the prompts to create a VR build of your game.

<video controls width="100%">
  <source src="/assets/images/HCI-roll-a-ball/roll-a-ball-vr.mp4" type="video/mp4">
</video>

And there you have it! You've adapted a basic Unity game for VR. This is a simplified guide, so you may encounter specific issues that require additional troubleshooting. Feel free to ask for further clarification or help on any of the steps