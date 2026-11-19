# Platform Jumper

### @explicitHints true

## Introduction @showdialog

Build a mini platform game: jump over the rocks with button **A**. How many can you clear?

Stuck on a step? Click the **lightbulb** to see what the finished code for that step looks like.

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Make the player

1. Click ``||basic:Basic||`` and drag ``||basic:on start||`` onto the workspace.
2. Click ``||variables:Variables||``, then **Make a Variable...**. Name it **player** and click **OK**.
3. Drag ``||variables:set player to 0||`` into ``||basic:on start||``.
4. Click **Advanced**, then ``||game:Game||``. Drag ``||game:create sprite at x: 2 y: 2||`` into the **0** of ``||variables:set player to||``.
5. Change **x** to **1** and **y** to **4**. That's you, at the bottom of the screen.

```blocks
let player = game.createSprite(1, 4)
```

## Make a rock

1. Click ``||variables:Variables||``, then **Make a Variable...**. Name it **rock**.
2. Drag ``||variables:set rock to 0||`` into ``||basic:on start||``, under the player.
3. From ``||game:Game||``, drag ``||game:create sprite at x: 2 y: 2||`` into its **0**.
4. Change **x** to **4** and **y** to **4**.

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
```

## Move the rock

1. Click ``||basic:Basic||`` and drag ``||basic:forever||`` onto the workspace.
2. From ``||game:Game||``, drag ``||game:sprite change x by 1||`` into ``||basic:forever||``.
3. Click the sprite name in the block and pick **rock**. Change **1** to **-1**.
4. From ``||basic:Basic||``, drag ``||basic:pause (ms) 100||`` under it. Change **100** to **300**.

```blocks
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
basic.forever(function () {
    rock.change(LedSpriteProperty.X, -1)
    basic.pause(300)
})
```

## Send it round again

1. From ``||logic:Logic||``, drag ``||logic:if true then||`` into ``||basic:forever||``, under the pause.
2. From ``||logic:Logic||``, drag ``||logic:0 = 0||`` into the **true** slot.
3. From ``||game:Game||``, drag ``||game:sprite x||`` into the first **0**. Pick **rock**. Leave the second **0** as it is.
4. From ``||game:Game||``, drag ``||game:sprite set x to 0||`` inside the **if**. Pick **rock** and change **0** to **4**.
5. From ``||game:Game||``, drag ``||game:change score by 1||`` under it.

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

1. Click ``||input:Input||`` and drag ``||input:on button A pressed||`` onto an empty space.
2. From ``||game:Game||``, drag ``||game:sprite change x by 1||`` into it. Pick **player**, change **x** to **y**, and **1** to **-1**.
3. From ``||basic:Basic||``, drag ``||basic:pause (ms) 100||`` under it. Change it to **500**.
4. Add another ``||game:sprite change x by 1||`` under the pause. Pick **player**, change **x** to **y**, and keep **1**.

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

1. From ``||logic:Logic||``, drag another ``||logic:if true then||`` to the bottom of ``||basic:forever||``.
2. From ``||game:Game||``, drag ``||game:sprite touching||`` into the **true** slot. Pick **player** first, then **rock**.
3. From ``||game:Game||``, drag ``||game:game over||`` inside the **if**.
4. Press **A** in the simulator to jump over the rocks. Can you beat 10?

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

## Add your mission key

1. From ``||basic:Basic||``, drag ``||basic:show number 0||`` to the **very top** of ``||basic:on start||``, above **set player**.
2. From ``||math:Math||``, drag ``||math:0 + 0||`` into its **0**.
3. From ``||math:Math||``, drag ``||math:0 × 0||`` into the **first** box of the **+**.
4. In the **×** block, type your **mission key** in the first box and **2** in the second.
5. In the last box of the **+**, type **31**.

```blocks
basic.showNumber(1234 * 2 + 31)
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
```

## Get your code

1. Press the **restart** button under the simulator.
2. The number that scrolls before the game starts is your code.
3. Go back to the RAD Labs tab and type it in.
4. Bonus: make the rocks speed up as your score grows.

```blocks
basic.showNumber(1234 * 2 + 31)
let player = game.createSprite(1, 4)
let rock = game.createSprite(4, 4)
input.onButtonPressed(Button.A, function () {
    player.change(LedSpriteProperty.Y, -1)
    basic.pause(500)
    player.change(LedSpriteProperty.Y, 1)
})
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

```template
//
```
