## Práctica Final: Prototipo juego 2D.

The project is a 2D side-scrolling platform game that will have a character who runs, jumps and avoids obstacles and needs to go from the beginning to the end of the level. It will have a little loading system so that when you finish a particular level it will load into the next level and so on using the unit TileMap system.

The first thing that has been done in the search for some spirtes, these are the sprites used for this project:

 ![Paso 1](imgs/Captura5.png)
 
Once chosen, change the size of pixels per unit from 100 to 32, then change the sprite from single to multiple, I continued adjusting the slice of each pixel
 
 ![Paso 2](imgs/Captura1.png)
 
Throughout the development I was creating different TileMap capabilities for the design of the different levels, the capabilities are the following:
 
 ![Paso 3](imgs/Captura2.png)
 
This is the TileMap as I have it in the project:

 ![Paso 3](imgs/Captura3.png)

When I found different layers in the TileMap I adjusted them by adding different layers and assigning them to the different layers and thanks to the sorting layers I was able to adjust them at will. Here I show the different layers created and the order in which I assign them.

 ![Paso 3](imgs/Captura4.png)

 ![Paso 3](imgs/Captura6.png)
 
If you look at the first image I provide about the sprites I have created a Rule Tile , they are programmable tiles, which are smart enough to use the appropriate adjacent tiles and handle tile animation, bounds and collisions on the fly. This has been one of the most difficult parts to carry out, since implementing the logic of how the level should be was quite imaginative, but in the long run it is something that has helped me learn and optimize the time in level design. Here I show you how I did the Tiling Rules
 
 ![Paso 3](imgs/Captura7.png)

 ![Paso 3](imgs/Captura8.png)
 
Once the TileRules logic is implemented, move on to the character animations, which are handled by the player, just as we were taught in class, we assign the different sprites that we will use for the animation, creating an animation, then creating an animator controller to define the different states through which the player will pass, always remember that when creating an animation we must activate the loop time option. In this particular case of the palyer, since it will have the states of Idle, Climbing, Running and Death, this logic that I comment on, as can be seen in the image, was applied to the different interactive elements that the player will see, in this case the enemies and the coins you collect.

  ![Paso 3](imgs/Captura9.png)
  
  ![Paso 3](imgs/Captura10.png)
  
Now we find that the character must interact with the map, as far as I have explained it is not possible, since we must apply collisions on the map, in this case I apply them on the Platforms Tilemap layer, adding a 2D Tilemap Collider and a Composite Collider2D which in turn adds a RigidBody2D that we are going to leave in Static, this also implies adding a collider2D to the player which in this case is a Capsule Collider 2D, which is adjusted to the size of the sprite, together with a Rigidbody2D marking the Freeze Rotation Z option, as we saw in class.

  ![Paso 3](imgs/Captura11.png)
  
  ![Paso 3](imgs/Captura12.png)
 
For the player controls I have decided to apply an input system by installing the package manager of the same name, to apply it we give the create actions option once we add it as a component to the player, it has some actions defined by default such as movement and shooting. In this case I added the jump action with the spacebar, to apply it I create the PlayerMovement script, it uses the InputSystem to detect player input and updates the player movement and animation accordingly.

  ![Paso 3](imgs/Captura13.png)
  
  ![Paso 3](imgs/Captura14.png)
 
  ![Paso 3](imgs/Captura15.png)

At this point we already have the animations, so we must apply in this script the different actions that the player will do, including correcting the flip of the character, the movement and the jump.

That's why the PlayerMovement script includes methods to run, flip the sprite, climb stairs, shoot, jump, and die.
Run() is the method that takes care of updating the character's speed based on player input. FlipSprite() is the method that is responsible for flipping the character's sprite when it changes direction. ClimbLadder() is the method that is responsible for updating the speed and gravity of the character when it is climbing. OnFire() is the method that is responsible for generating a bullet when the player presses the fire button. OnMove() is the method that takes care of getting input from the player's movement. OnJump() is the method that is responsible for updating the speed of the character when the player presses the jump button and finally Die() is the method that is responsible for killing the character when it collides with enemies or hazards.

In the Update() method it is verified if the character is alive, if it is alive the Run(), FlipSprite(), ClimbLadder() and Die() methods are called.

  ![Paso 3](imgs/Captura16.png)
  
  ![Paso 3](imgs/Captura17.png)
 
  ![Paso 3](imgs/Captura18.png)
  
  ![Paso 3](imgs/Captura19.png)
  
To prevent the player from jumping indefinitely, we take advantage of the layers, and we adjust how the character can interact, for this I create a layer called ground, so that the character can jump when he is only touching the ground, as can be seen in the image above in the OnJump function. I also leave here how I have adjusted the interactions of the layers.

  ![Paso 3](imgs/Captura20.png)
