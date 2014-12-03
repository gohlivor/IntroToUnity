#IntroToUnity
Author(s): Nathalie Goh-Livorness || aka.ms/nathalie || @stopNgoh
Original content can be found here: http://unity3d.com/learn/tutorials/projects/survival-shooter
============
#Objective
This lab goes through using the Unity Game engine to build and ship your first game to Windows.

#By the end of this lab you will be able to:
•Understand the Unity interface
•Set up a 3d environment in Unity
•Build and run your game to all platforms
01 - SETTING UP THE ENVIRONMENT 
02 - ADDING THE PLAYER CHARACTER 
03 - SETTING UP THE CAMERA 
04 - ADDING THE FIRST ENEMY

#Requirements
•Visual Studio for Unity - https://visualstudiogallery.msdn.microsoft.com/20b80b8c-659b-45ef-96c1-437828fe7cf2
•Unity 4.5.5 or higher - https://unity3d.com/unity/download

#Setup
Screenshot of VS plug in for Unity
#Environment
1.	Setup Editor Layout 2 by 3
2.	Drag Project tab below the Hierarchy
3.	Set view slider to minimum on Project panel
4.	File -> New Scene
5.	File -> Save Scene As, name it Level 01 in Scenes folder
6.	Locate Environment prefab in the Project panel Prefabs folder
7.	Drag into Scene or Hierarchy
8.	Ensure it is at Position (0,0,0) in Transform
9.	Repeat 1-3 for the Lights prefab
10.	Save your scene (CMD-S / CTRL-S)
11.	GameObject menu -> 3D Object -> Quad
12.	Rename to Floor
13.	Ensure it is at Position (0, 0, 0) in Transform
14.	Set Rotation (90, 0, 0) in Transform
15.	Set Scale to (100, 100, 1) in Transform
16.	Remove Mesh Renderer Component from the Floor game object
17.	Set the Floor game object to use the Floor layer at the top of the Inspector panel
18.	Save your Scene (CMD-S / CTRL-S)
19.	Game Object -> Create Empty
20.	Rename GameObject to BackgroundMusic
21.	Add Component -> Audio -> Audio Source
22.	Audio Clip -> Circle Select -> Background Music
23.	Check Loop and set Volume to 0.1
24.	Save your Scene (CMD-S / CTRL-S)
#End of Phase One!
#Player Character
1.	Locate the Player model in Models -> Characters folder of the Project panel
2.	Drag it into the Scene or Hierarchy panels
3.	Set the Position to (0, 0, 0) in Transform
4.	Set the Tag to Player in the drop-down in Inspector
5.	Select the Animation folder and click Create on the Project panel, choose Animator Controller
6.	Name this new asset PlayerAC
7.	Drag and drop it onto the Player in the Hierarchy
8.	Double-click PlayerAC asset in Project -> Animation
9.	Dock the Animator window by the Scene view
10.	Expand the Player model in Models -> Characters
11.	Drag the Idle, Move and Death animations to empty space in the Animator window to create states
12.	Right-click Idle state and choose Set as Default
13.	Create a bool parameter named IsWalking
14.	Create a Trigger parameter named Die
15.	Right-click Idle and Make Transition to move
16.	Select the Transition arrow you made
17.	Set the condition for this to Iswalking = true
18.	Right-click Move and Make Transition to Idle
19.	Set the Condition for this to IsWalking = false
20.	Right-click ‘Any State’ and Make Transition to Death
21.	Set the Condition for this to Die (trigger)
22.	Select Player game object, component -> Physics -> Rigidbody
23.	Set Drag & Angular Drag to Infinity
24.	Expand the Constraints, Freeze the Y Position and Freeze the X and Z Rotations
25.	Select Player game object, Add Component -> Physics -> Capsule Collider
26.	Set Center to (0.2, 0.6, 0)
27.	Set Height to 1.2
28.	Add Component -> Audio -> Audio Source
29.	Audio Clip -> Circle Select Player Hurt
30.	Uncheck Play On Awake
31.	Locate PlayerMovement script in Scripts -> Player
32.	Drag & Drop this to Player game object in Hierarchy
33.	Save your Scene (CMD-S / CTRL-S)
34.	Double-click the icon of the PlayerMovement script to open it in the Script editor
