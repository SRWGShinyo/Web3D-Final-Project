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

- [Drop your code, as a zip file, in here](https://drive.google.com/drive/folders/1B4TgjEEfdOYjTHp9lK81HVvfOH6FCRh0?usp=drive_link)
- Name of the zip: <login>.zip
- Send the code as a zip file. You can send me a google drive link if the package is too heavy.

**Be careful**: You will lose points if the project does not compile or if the node_modules are still there.

## Deadline

You have until **Sunday, 15th of January, 2024 - 11:42PM** to submit the project.

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

# Step 1 - Set up a basic switcharoo

What I want you to build here is a kind of **carousel**. We will alternate between different models of your creation.

So first, let's create the basics for that.

Add the `OrbitControls` to your camera. they should make it so that the cube is at the center of everything. You will have to create an update function.

Then, add a property in the debugger to **scale the cube, and to change its material color.**

Next, add an **event listener** on the **space** keyboard touch.

- When "space" is pressed, the displayed 3D model (whatever it is) should scale down to 0 and the next 3D model in the list should slowly scale up to 1.

**Tip: you can use gsap for this.**

For now, have the cube transition to a `ConeGeometry`. Then, when pressing space again, it should transition to a cube again.

The `ConeGeometry` should have a `ToonMaterial` attached to it, and be of a color of your choice which is not the same as the cube.

To our lil-gui, add the option to **change the color of the cone**.

## This step is finished when...

- Your camera has OrbitControls attached and can **rotate around a 3D model at its center.**
- Through our debugger, we can scale the cube and change its color.
- When pressing `space`, our cube scales down to 0 and a `ConeGeometry`scales up to 1.
- It is possible to change **the color of the cone through our debugger**

# Step 2 - My own little home

Let's build a basic home ! You'll see, it'll be very, very basic.

**Let's get back to our cube**

Add a `ConeGeometry` to the scene. It will be the roof of our home. Add a property on the debugger to scale it and position it on the debugger, and position it properly on top of the cube so it acts as our roof.

Let's add a door. Create a `Plane`, rotate it so that it is upwards and scale it so that it ressembles a door. Put it on one of the faces of the cube.

**Tips: you should use [**Groups**](https://threejs.org/docs/?q=Group#api/en/objects/Group) to simplify this one.**

On the debugger, also add a way to change the roof's material colors.

In this github folder, you will find a folder 'textures/door'. These textures are the one we will use for our door.

This step is simple: load all the textures of the door (height, normal, ambientOcclusion, metlaness, roughness, alpha, color...) and put them on the door. I want to see a beautiful door!

If one of the texture does not manage to be loaded, I want to see the message 'Texture could not load'.

Let's do the same for the house. In the folder 'textures/house', you will see a lot of textures you can use to create a proper brick house.

Load all those textures, and put them on the cube. If any of them fail, you should display the message 'Texture could not load' in the console.

Be careful to choose the proper material for this, it has to be able to receive lighting!

**Finally, make sure that when we press `space` our carousel still works. The house and the cone should alternate each other.**

## This step is finished when...

- The cone and plane are in the scene, with the cone acting as a roof on our cube.
- The debugger displays ways to change the cone position, scale and color.
- The plane has all textures needed to act as a door, is properly positioned.
- The cube has all textures loaded to resemble a brick house.
- When a texture fails to load, the message 'Texture could not load' is displayed.
- When pressing `space`, the model at the center rotates between our cone in ToonShader and our house.

# Step 3 - Animals

Let's add life in this scene. Don't be afraid of what I'm gonna ask you, it's simply to be able to evaluate your skills on this

First, import the Fox model. This will also be a new 3D model in our rotation.
Import it, scale it properly. And make it so that **when I press space, the displayed model switches between our house, the cone and the renard**.

Second, import the flamingo and parrot model **in our house model**. Position them as you wish, around the house.

## This step is finished when...

- The fox is imported and properly scaled.
- The flamingo and parrot are imported and properly scaled.
- The fox appears as a standalone 3D models that will rotate out when we press space.
- The parrot and flamingo are part of our "house" 3D Model and rotate out when it rotates out.

# Step 4 - Lights

Let's add some lights!

Add a spotlight. It should properly light our 3D models from the top, and be intense enough so we can see them properly.

Add a property in our debugger to change the light(s) color.

To be fair, you can be free on this step, as long as I can see the models properly and that I can change the lights color.

**FORBIDDEN: NO AMBIANT LIGHTING.**

## This step is finished when...

- One or multiple lights light properly our models.
- I can change the color of the lights through the debugger.
- NO AMBIANT LIGHTING

# Step 5 - Naming and Animations

Here is the final boss guys, you're almost there!

First add 3D text(s). This should display
- "The Fox", when the fox is the displayed 3D model.
- "My House - login" with your login when the house is the displayed 3D model.
- "The cone of toons" when the cone is the displayed 3D model.

Second, let's animate our 3D models.
- When I click on the fox, it should start its 'running' animation **in place**. When I click again, it should stop.
- When I click on the house, the flamingo and parrot should start **flapping their wings and rotating around the house.**. They should stop if I click on the house again.

**NB: Think about reusability and performances**

## This step is finished when...

- A 3D text 'The Fox' is displayed when the fox is the active 3D model
- A 3D text 'My Home - login' is displayed when the house is the active 3D model.
- A 3D text 'The cone of toons' is displayed when the cone is the active 3D model.
- The fox starts animating when I Click on it. An animated fox stops when I click again.
- The flamingo and parrot start flapping their wings and rotating around the house when I Click on the house. They stop when I click again.

# BONUS - Some cool effects

Feel free to do whatever you want, from there! Add more animals ? Add more animations ? Make the house move ? Make the ground more realistic ?

Add particle effects, add post processing... do whatever !!

I will add bonus points of course if you did this seriously, all work deserves praise!
