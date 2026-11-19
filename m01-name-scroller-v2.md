# Name Scroller

### @explicitHints true

## Introduction @showdialog

Make your name scroll across the lights, then make it wait for a button press.

Stuck on a step? Click the **lightbulb** to see what the finished code for that step looks like.

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Start your program

1. Click ``||basic:Basic||``.
2. Drag ``||basic:forever||`` onto the workspace.

```blocks
basic.forever(function () {
})
```

## Show your name

1. Click ``||basic:Basic||`` again.
2. Drag ``||basic:show string "Hello!"||`` into ``||basic:forever||``.
3. Click the text and type your name.
4. Watch the board on the left: your name scrolls across the lights.

```blocks
basic.forever(function () {
    basic.showString("Thando")
})
```

## Change it

1. Click the text in ``||basic:show string||``.
2. Type something new: your favourite game, your pet's name, or **HELLO**.
3. Watch the board change straight away. There's no save button.

```blocks
basic.forever(function () {
    basic.showString("HELLO")
})
```

## Wait for a button

1. Click ``||input:Input||``.
2. Drag ``||input:on button A pressed||`` onto an empty space.
3. Move ``||basic:show string||`` out of ``||basic:forever||`` and into ``||input:on button A pressed||``.
4. Leave ``||basic:forever||`` empty.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
basic.forever(function () {
})
```

## Press A

1. Find button **A** on the board in the simulator.
2. Click it.
3. Nothing happened until you pressed A. That's an **event**: the program waits for something to happen, then acts.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
basic.forever(function () {
})
```

## Add a button B block

1. Click ``||input:Input||``.
2. Drag another ``||input:on button A pressed||`` onto an empty space.
3. Click the **A** in the new block and change it to **B**.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
input.onButtonPressed(Button.B, function () {
})
```

## Show a number

1. Click ``||basic:Basic||``.
2. Drag ``||basic:show number 0||`` into ``||input:on button B pressed||``.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(0)
})
```

## Add your mission key

1. Click ``||math:Math||``.
2. Drag ``||math:0 + 0||`` into the **0** of ``||basic:show number||``.
3. In the first box, type your **mission key** (it's on the RAD Labs tab).
4. In the second box, type **11**.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 + 11)
})
```

## Get your code

1. Press **B** on the board in the simulator.
2. The number that scrolls is your code.
3. Go back to the RAD Labs tab and type it in to collect your badge.
4. Bonus: change what A shows, and add a message for **A+B**.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 + 11)
})
basic.forever(function () {
})
```

```template
//
```
