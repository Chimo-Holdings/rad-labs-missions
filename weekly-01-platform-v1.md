# Platform Jumper

### @explicitHints true

## Introduction @showdialog

Build a mini platform game: jump over the rocks with button **A**. How many can you clear?

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Make the player

From ``||game:Game||``, drag ``||variables:set sprite to create sprite at x: 2 y: 2||`` into ``||basic:on start||``.

Rename the variable to **player** and set **x** to **1** and **y** to **4**. That's you, at the bottom of the screen.

```blocks
let player = game.createSprite(1, 4)
```

## Make a rock

Add another ``||variables:set sprite to create sprite||`` under it. Call this one **rock**, at **x 4** and **y 4**.

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
```

## Move the rock

In ``||basic:forever||``, add ``||game:rock change x by -1||`` and then ``||basic:pause 300||``.

The rock slides towards you.

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
basic.forever(function () {
    rock.change(LedSpriteProperty.X, -1)
    basic.pause(300)
})
```

## Send it round again

Still in ``||basic:forever||``, add ``||logic:if||``: if **rock x = 0**, then ``||game:set rock x to 4||`` and ``||game:change score by 1||``.

Each rock you get past is a point.

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
basic.forever(function () {
    rock.change(LedSpriteProperty.X, -1)
    basic.pause(300)
    if (rock.get(LedSpriteProperty.X) == 0) {
        rock.set(LedSpriteProperty.X, 4)
        game.addScore(1)
    }
})
```

## Jump!

From ``||input:Input||``, add ``||input:on button A pressed||``. Inside it: ``||game:player change y by -1||``, ``||basic:pause 500||``, then ``||game:player change y by 1||``.

Up, wait, down. That's a jump.

```blocks
input.onButtonPressed(Button.A, function () {
    player.change(LedSpriteProperty.Y, -1)
    basic.pause(500)
    player.change(LedSpriteProperty.Y, 1)
})
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
```

## Crash

At the end of ``||basic:forever||``, add ``||logic:if||`` ``||game:player touching rock||`` then ``||game:game over||``.

Now press **A** in the simulator to jump over the rocks. Can you beat 10?

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
basic.forever(function () {
    rock.change(LedSpriteProperty.X, -1)
    basic.pause(300)
    if (rock.get(LedSpriteProperty.X) == 0) {
        rock.set(LedSpriteProperty.X, 4)
        game.addScore(1)
    }
    if (player.isTouching(rock)) {
        game.gameOver()
    }
})
```

## Your mission key

Now prove it's your game. Drag a ``||basic:show number||`` to the **very top** of ``||basic:on start||``, above the player.

From ``||math:Math||``, make it **(your key × 2) + 31**. Type your mission key where it says 1234.

```blocks
basic.showNumber(1234 * 2 + 31)
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
```

## Get your code

Press the restart button under the simulator. The number that scrolls before the game starts is your code.

Go back to the RAD Labs tab and type it in. Bonus: make the rocks speed up as your score grows.

```template
basic.forever(function () {
})
```
