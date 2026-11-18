# LED Art

### @explicitHints true

## Introduction @showdialog

Design your own pictures on the lights and make them move like a cartoon.

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Draw a picture

From ``||input:Input||``, drag ``||input:on button A pressed||`` onto the workspace.

From ``||basic:Basic||``, put a ``||basic:show leds||`` block inside it. Click the squares to draw your first picture. Press **A** in the simulator to see it.

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

Add a second ``||basic:show leds||`` under the first one, and draw a slightly different picture: smaller, moved, or changed.

Press **A**. The two pictures play one after another, in order. That's a **sequence**.

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

From ``||basic:Basic||``, put a ``||basic:pause||`` block after each picture. Try **200** ms, then **1000** ms.

The pause is **timing**: it decides how fast your animation plays.

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

From ``||loops:Loops||``, drag a ``||loops:repeat 4 times||`` block into ``||input:on button A pressed||`` and move your pictures and pauses inside it.

Press **A**. Your animation plays 4 times. That's a **loop**.

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

## Your mission key

Now prove it's your work. Drag in another ``||input:on button A pressed||`` block and change **A** to **B**.

Put a ``||basic:show number||`` block inside it. From ``||math:Math||``, drop in a ``||math:0 × 0||`` block, then drop a ``||math:0 + 0||`` block into it so it reads **(key × 2) + 7**.

Type **your mission key** where it says 1234.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 * 2 + 7)
})
```

## Get your code

Press **B** on the board. The number that scrolls is your code.

Go back to the RAD Labs tab and type it in to collect your badge. Bonus: add a third picture to your animation.

```template
basic.forever(function () {
})
```
