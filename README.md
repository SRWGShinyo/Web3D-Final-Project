# Web3D Introduction - Final Project

## Foreword

You will find here the rules for the project evaluating our Web3D introduction class.
It is split into **steps**. The more you will do, the better the grade. Please however, keep in mind a few things:

- Pay attention to the way you write and structure your code, as I will also be evaluating this.
- I will give you all instructions on what I want to see, but you are free to do what your imagination tells you for what I did not mention (scale, position, rotation...)
- Web3D is also a matter of creativity. Do not hesitate to do more!
- You can do all the steps in any order you want! The validation criterias are displayed at the end of each section.

And, of course, have fun!

A **huge** thank you to [**Bruno Simon**](https://bruno-simon.com/) and his Three.Js journey content, from which I take a lot of the resources I give you here (textures, models...)

Some models were found on the [ThreeJS Examples](https://github.com/mrdoob/three.js/tree/dev/examples/models).

**You can always contact me, after a class or by mail, for any question**

## How to submit

- Send a mail to yohann.degliesposti@gmail.com
- Title: [WEB3D][PROJ] - login
- Send the code as a zip file. You can send me a google drive link if the package is too heavy.

**Be careful**: You will lose points if the project does not compile or if the node_modules are still there.

## Deadline

You have until **Sunday, 10th of December, 2023 - 11:42PM** to submit the project.

## Building and Launching

- The project should be built with vite.js
- All assets should be served under a `/static/` folder, and each should be put in a proper folder (3D models under `models`, textures under `textures`...)

I will do `npm run dev` to launch your project. **Make sure that it works**

# Step 0 - Set up and debug

This step is basically setting up a project, with the debugger.

First **create a new project**, as we did in class. I want it to be built and ran with **vite.js**.
All the static content should be served through a folder named `/static/`.

Then, install the **three.js package**.

**Create a new scene, a new camera (perspective), and a cube.**

Then, make the scene fullscreen. I should be able to have a proper ratio and see the scene in its entirety.

Add the `lil-gui` package, and instantiate the debugger.


## This step is finished when...

- The project is running on `vite.js`, by doing `npm run dev`
- The scene is displayed on a web page, in fullscreen, with a cube and a perspective camera
- The debugger is installed, it is instantiated in the scene.

# Step 1 - My own little home

Let's build a basic home ! You'll see, it'll be very, very basic.

Add the `OrbitControls` to your camera. they should make it so that the cube is at the center of everything. You will have to create an update function.

Then, add a property in the debugger to scale the cube, and to change its position. Position it as you wish.

Add a `ConeGeometry` to the scene. It will be the roof of our home. Add a property to scale it and position it on the debugger, and position it properly on your house.

We are almost there ! Let's add a door. Create a `Plane`, rotate it so that it is upwards and scale it so that it ressembles a door. Put it on one of the faces of the cube.

Finally, we want a ground. Let's create another `Plane`, color it green, and put it horizontally under your house. Make it realistic! Add a way on the debugger to scale your ground.

On the debugger, also add a way to change the cube's and the roof's material colors.

## This step is finished when...

- The OrbitControls are in the scene and working.
- The Cube, Cone, and two planes are in the scene, and create a house with the cube as body, the cone as roof, one plane as door and one plane as ground.
- The ground plane is green.
- The debugger displays ways to change the cube and the roof position, scale and color.
- The door is properly dimensioned, and positioned horizontally on a wall.


# Step 2 - What a door, what a door

I find our door to be a bit bland. So let's change this!

In this github folder, you will find a folder 'textures/door'. These textures are the one we will use for our door.

This step is simple: load all the textures of the door (height, normal, ambientOcclusion, metlaness, roughness, alpha, color...) and put them on the door. I want to see a beautiful door!

If one of the texture does not manage to be loaded, I want to see the message 'Texture could not load'.

Let's do the same for the house. In the folder 'textures/house', you will see a lot of textures you can use to create a proper brick house.

Load all those textures, and put them on the cube. If any of them fail, you should display the message 'Texture could not load' in the console.

**Be careful to choose the proper material for this, it has to be able to receive lighting!**

## This step is finished when...

- All textures for the door are loaded properly.
- The door displays height, normals, AO, metalness, rougness, alpha, color
- In case of a loading problem, the code will display the message 'Texture could not load'.
- All textures for the house are loaded properly.
- The cube displays ambient, normals, roughness,  AO
- In case of a loading problem, the code will display the message 'Texture could not load'.

# Step 3 - Ambiance and Animals

Let's add life in this scene. Don't be afraid of what I'm gonna ask you, it's simply to be able to evaluate your skills on this

First, start by adding a directionnal light. It should come from above and hit the roof, as the sun would.

Then, let's add some bushes. Let's not make it complicated: a bush is a sphere in a green material. Put different 'bushes' in your floor.

Now, let's create flowers. We can do it easy as well: a flower is simply a `CylinderGeometry`, with on top of it a `ConeGeomtry`, reversed. Scale them properly, position them well, and you have a flower!

I want flowers to be different colors, and to shine. So, **make the material of the ConeGeometry receptive to light**, and change the color of the cone. Then for each flower, create a `pointlight` that shines the color of the cone.

Ex: a purple cone will have a purple pointlight attached to it.

Tips: you should use [**Groups**](https://threejs.org/docs/?q=Group#api/en/objects/Group) to simplify this one.

Create and position at least 3 flowers of different color.

Then let's talk animals !
Inside this folder, you will find a /models/ folder.

In it, you will find `flamingo.glb` and `parrot.glb`. Load those two models. **Do not be afraid, glb are just binary GLTF, you can load them with the GLTF loader**.

Have them play their flying animation. Then, make them rotate around the house.

If all goes well, the two birds should be flapping their wings and rotating around the house.

For a final touch, change the color of the renderer to blue. Black background just doesn't cut it !

## This step is finished when...

- A directional light is shining on the roof
- At least three 'bushes' are in the scene
- At least three flowers of different colors are shining, with proper pointlights attached.
- The parrot and the flamingo are in the scene.
- The parrot and the flamingo are flapping their wings, and rotating around the house.
- The renderer color is blue.

# Step 4 - Knock on your door

To finish it, let's add two things.

First I want your login displayed on the door. Create a new 3D text, scale it properly. This text should display your login. Hang the login on the door.

Then, I want to be able to knock on your door. Add a raycast to the door, and when I click on it, log 'knock knock' in the console. Yep, that's all.

## This step is finished when...

- Your login is displayed on the door through a 3D TextMesh
- When clicking on the door, the message 'knock knock' is displayed in the console.

# BONUS - Some cool effects

Feel free to do whatever you want, from there! Add more animals ? Add more animations ? Make the house move ? Make the ground more realistic ?

Add particle effects, add post processing... do whatever !!

I will add bonus points of course if you did this seriously, all work deserves praise!