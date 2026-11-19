# LED Art

### @explicitHints true

## Introduction @showdialog

Design your own pictures on the lights and make them move like a cartoon.

Stuck on a step? Click the **lightbulb** to see what the finished code for that step looks like.

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Add a button

1. Click ``||input:Input||``.
2. Drag ``||input:on button A pressed||`` onto the workspace.

```blocks
input.onButtonPressed(Button.A, function () {
})
```

## Draw a picture

1. Click ``||basic:Basic||``.
2. Drag ``||basic:show leds||`` into ``||input:on button A pressed||``.
3. Click the squares to draw your first picture.
4. Press **A** in the simulator to see it.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
})
```

## Draw the next picture

1. From ``||basic:Basic||``, drag another ``||basic:show leds||`` under the first one.
2. Draw a slightly different picture: smaller, moved, or changed.
3. Press **A**. The pictures play one after another, in order. That's a **sequence**.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .
        `)
})
```

## Set the timing

1. From ``||basic:Basic||``, drag ``||basic:pause (ms) 100||`` under the first picture.
2. Drag another ``||basic:pause (ms) 100||`` under the second picture.
3. Change both to **200**. Then try **1000**. The pause is **timing**: it sets how fast your animation plays.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
    basic.pause(200)
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(200)
})
```

## Play it on repeat

1. Click ``||loops:Loops||``.
2. Drag ``||loops:repeat 4 times||`` into ``||input:on button A pressed||``.
3. Move both pictures and both pauses inside the **repeat**.
4. Press **A**. Your animation plays 4 times. That's a **loop**.

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        basic.showLeds(`
            . # . # .
            # # # # #
            # # # # #
            . # # # .
            . . # . .
            `)
        basic.pause(200)
        basic.showLeds(`
            . . . . .
            . # . # .
            . # # # .
            . . # . .
            . . . . .
            `)
        basic.pause(200)
    }
})
```

## Add a button B block

1. Click ``||input:Input||``.
2. Drag another ``||input:on button A pressed||`` onto an empty space.
3. Change its **A** to **B**.
4. From ``||basic:Basic||``, drag ``||basic:show number 0||`` into it.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(0)
})
```

## Add your mission key

1. From ``||math:Math||``, drag ``||math:0 + 0||`` into the **0** of ``||basic:show number||``.
2. From ``||math:Math||``, drag ``||math:0 × 0||`` into the **first** box of the **+**.
3. In the **×** block, type your **mission key** in the first box and **2** in the second.
4. In the last box of the **+**, type **7**.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 * 2 + 7)
})
```

## Get your code

1. Press **B** on the board in the simulator.
2. The number that scrolls is your code.
3. Go back to the RAD Labs tab and type it in to collect your badge.
4. Bonus: add a third picture to your animation.

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        basic.showLeds(`
            . # . # .
            # # # # #
            # # # # #
            . # # # .
            . . # . .
            `)
        basic.pause(200)
        basic.showLeds(`
            . . . . .
            . # . # .
            . # # # .
            . . # . .
            . . . . .
            `)
        basic.pause(200)
    }
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 * 2 + 7)
})
```

```template
//
```
