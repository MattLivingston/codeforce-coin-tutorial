# Coin Tutorial
## Micro-Tutorial for our Mario Platformer

# Part 1
We will need a sprite to test out our code. From the Sprites bucket, drag and drop this code block. 
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
```
Next choose a Sprite to be your main character. I am using Princess CodeForce
 ```blocks
 let mySprite = sprites.create(img`
    . . . . . . f f f f 4 4 f . . . 
    . . . . f f b f 5 4 5 5 4 f . . 
    . . . f b 3 3 e 4 5 5 5 5 f . . 
    . . f b 3 3 3 3 e 4 4 4 e f . . 
    . . f 3 3 3 3 3 3 3 3 3 3 f . . 
    . . f 3 3 3 3 e b 3 e e 3 3 f . 
    . . f 3 3 3 3 f f e e e 3 3 f . 
    . . f b b b b f b f e e e 3 f . 
    . . f b b b b e 1 f 4 4 e f . . 
    . f f b b b b f 4 4 4 4 f . . . 
    . f b b b b f f f e e e f . . . 
    . . f b b f 4 4 e d d d f . . . 
    . . . f f e 4 4 e d d d f . . . 
    . . . . f b e e b d b d b f . . 
    . . . . f f d 1 d 1 d 1 f f . . 
    . . . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
```
Finally, don't forget to rename your sprite from MySprite. Click the down carrot and select Rename Variable

```blocks
let PrincessCodeForce = sprites.create(img`
    . . . . . . f f f f 4 4 f . . . 
    . . . . f f b f 5 4 5 5 4 f . . 
    . . . f b 3 3 e 4 5 5 5 5 f . . 
    . . f b 3 3 3 3 e 4 4 4 e f . . 
    . . f 3 3 3 3 3 3 3 3 3 3 f . . 
    . . f 3 3 3 3 e b 3 e e 3 3 f . 
    . . f 3 3 3 3 f f e e e 3 3 f . 
    . . f b b b b f b f e e e 3 f . 
    . . f b b b b e 1 f 4 4 e f . . 
    . f f b b b b f 4 4 4 4 f . . . 
    . f b b b b f f f e e e f . . . 
    . . f b b f 4 4 e d d d f . . . 
    . . . f f e 4 4 e d d d f . . . 
    . . . . f b e e b d b d b f . . 
    . . . . f f d 1 d 1 d 1 f f . . 
    . . . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
```
Next, add the code for our TileMap. We want a basic floor. Grab the following block from the Tilemap bucket. Set the size to 32,8 and create a floor for our character to run on.
```blocks
tiles.setCurrentTilemap(tilemap`level1`)
```
Gravity! We need gravity. Grab the following code block:
```blocks
let MySprite.ay = 300
```
Lets wrap up Part 1 by finishing up the last couple of blocks to use the controller and have the camera follow our hero. Make sure to click on the + button on the move block. Set vx to 100 and vy to 0. This will prevent the player from moving up with the up arrow. Your code should now look like:
```blocks
let PrincessCodeForce = sprites.create(img`
    . . . . . . f f f f 4 4 f . . . 
    . . . . f f b f 5 4 5 5 4 f . . 
    . . . f b 3 3 e 4 5 5 5 5 f . . 
    . . f b 3 3 3 3 e 4 4 4 e f . . 
    . . f 3 3 3 3 3 3 3 3 3 3 f . . 
    . . f 3 3 3 3 e b 3 e e 3 3 f . 
    . . f 3 3 3 3 f f e e e 3 3 f . 
    . . f b b b b f b f e e e 3 f . 
    . . f b b b b e 1 f 4 4 e f . . 
    . f f b b b b f 4 4 4 4 f . . . 
    . f b b b b f f f e e e f . . . 
    . . f b b f 4 4 e d d d f . . . 
    . . . f f e 4 4 e d d d f . . . 
    . . . . f b e e b d b d b f . . 
    . . . . f f d 1 d 1 d 1 f f . . 
    . . . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
tiles.setCurrentTilemap(tilemap`level1`)
PrincessCodeForce.ay = 300
controller.moveSprite(PrincessCodeForce, 100, 0)
scene.cameraFollowSprite(PrincessCodeForce)
```

# Part 2
## Jumping
To implement jump, we will use a little more logic. We want to prevent double jumping and add some pre-work for when our hero gets a mushroom that gives them a higher jump.
Grab the following code blocks:
```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (true) {
    	
    }
})
```
Hint: The if block is located in the Logic bucket.

Grab another set x to 0 block 
```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (true) {
        PrincessCodeForce.x = 0
    }
})
```
Change the ``x`` to ``vy`` and set the value to ``-150``
```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (true) {
        PrincessCodeForce.vx = -150
    }
})
```

This is great! But, it doesn't prevent the user from double jumping. Lets fix that now. 
Change your code to look like this. Hint: Its in the Logic bucket
```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (0 == 0) {
        PrincessCodeForce.vy = -150
    }
})
```
From the Sprites bucket, get the following blocks
```blocks 
MySprite.x = 0
```


