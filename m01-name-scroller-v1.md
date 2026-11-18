# Name Scroller

### @explicitHints true

## Introduction @showdialog

Make your name scroll across the lights, then make it wait for a button press.

At the end you'll need your **mission key** from the RAD Labs tab. Keep that tab open.

## Show your name

From ``||basic:Basic||``, drag a ``||basic:show string||`` block into ``||basic:forever||``.

Click the text and type your name. Watch the board on the left: your name scrolls across the lights.

```blocks
basic.forever(function () {
    basic.showString("Thando")
})
```

## Change it

Try a different word: your favourite game, your pet's name, or **HELLO**.

The board changes straight away. There's no save button and nothing to wait for.

```blocks
basic.forever(function () {
    basic.showString("HELLO")
})
```

## Wait for a button

From ``||input:Input||``, drag ``||input:on button A pressed||`` onto an empty space.

Now move your ``||basic:show string||`` block out of ``||basic:forever||`` and into ``||input:on button A pressed||``. Leave ``||basic:forever||`` empty.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
basic.forever(function () {
})
```

## Press A

Click the **A** button on the board in the simulator.

Nothing happened until you pressed A. That's an **event**: the program waits for something to happen, then acts. A WhatsApp send button works the same way.

## Your mission key

Now prove it's your work. From ``||input:Input||``, drag another ``||input:on button A pressed||`` block onto the workspace and change **A** to **B**.

From ``||basic:Basic||``, put a ``||basic:show number||`` block inside it. From ``||math:Math||``, drop a ``||math:0 + 0||`` block into the number.

Type **your mission key** in the first box and **11** in the second.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Thando")
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(1234 + 11)
})
```

## Get your code

Press **B** on the board. The number that scrolls is your code.

Go back to the RAD Labs tab and type it in to collect your badge. Bonus: change what A shows, and add a message for **A+B**.

```template
basic.forever(function () {
})
```
