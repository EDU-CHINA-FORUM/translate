﻿
# Agent Pyramid: Blocks


## Step 1
Create an ``||agent:on chat||`` command and name it **“pyramid”**. Click the **(+)** and create a new **size** variable.

```blocks
player.onChat("pyramid", function (size){ 
 
}) 
```

## Step 2
Get an ``||logic:if-then||`` and drag it into the **pyramid** ``||agent:on chat||`` command. Drag a ``||comparison||`` into the **true** argument of the ``||if-then conditional||``  and set it to **>** (greater than). Then, insert the **size** variable into the first argument **left**. Leave the right argument empty.

```blocks
player.onChat("pyramid", function (size)){ 
    let size = 0 
    if (size > 0) { 
      
    } 
```

## Step 3

Add an ``||agent:set block or item||`` into the ``||if-then conditional||`` and select **Sandstone**. Drag a ``||math return||`` into the **count** field, set it to **multiply**, drag the **size** variable into BOTH arguments of the product (multiplication template), and set the **in slot** argument to **1**. 

```blocks
player.onChat("pyramid", function (size){ 
    let size = 0 
    if (size > 0) { 
        agent.setItem(SANDSTONE, size * size, 1) 
    } 
}) 
```

## Step 4

Add an ``||agent:set active slot||`` into the ``||if-then conditional||`` and set the **slot** argument to 1.

```blocks
        agent.setItem(SANDSTONE, size * size, 1) 
        agent.setSlot(1) 
    } 
})
```

## Step 5

Add an ``||agent:place on move||`` into the ``||if-then conditional||`` and set the **logical** argument to **true**.

```blocks
        agent.setSlot(1) 
        agent.setAssist(PLACE_ON_MOVE, true) 
    } 
}) 
```

## Step 6

Get a ``||for loop||`` and drag it into the ``||if-then conditional||``. Create a new variable with the name **I** and drag it into the **index** of the ``||for loop||``. Add a ``||math difference||`` of two numbers and set it to 4 minus 1.
	
```blocks
    agent.setAssist(PLACE_ON_MOVE, true) 
        for (let i = 0; i <= 0 - 0; i++) { 
          
        } 
    } 
```

## Step 7

Add an ``||agent move||`` into the ``||for loop||``, set the first argument to **forward** and set the second argument to **size**.

```blocks
        for (let i = 0; i <= 0 - 0; i++) { 
            agent.move(FORWARD, size) 
        } 
```

## Step 8

 Add an ``||agent turn||`` into the ``||for loop||`` and set it to **left turn**.

```blocks
for (let i = 0; i <= 0 - 0; i++) { 
            agent.move(FORWARD, size) 
            agent.turn(LEFT_TURN) 
        } 
```

## Step 9

Outside the for loop, add another ``||agent move||``, set it to **up by 1**, and then drag it into the end of the ``|if-then conditional||`` .

```blocks
   } 
        agent.move(UP, 1) 
    } 
```


## Step 10

Add an ``||agent:place on move||``, set it to **false**, and drag it into the end of the ``|if-then conditional||``. Add another ``||agent:move||``, set it to **forward by 1**, and drag it into the end ``|if-then conditional||``.

```blocks
  agent.move(UP, 1) 
        agent.setAssist(PLACE_ON_MOVE, false)
```

## Step 11


Get a ``||run chat||`` command and drag it into the workspace. Get a ``||text join||`` and drag it into the **string** argument of the ``||run chat||`` command. Type **pyramid** into the first string argument of the ``||text join||``.  Get a ``||math return difference||`` and drag it into the second string argument of the ``||text join||``. Add the **size** variable into the first field in the ``||math return difference||``, then set the second field of the ``||math return difference||`` to **2**. Drag the completed ``||run chat||`` command into the end ``|if-then conditional||``.

```blocks
        agent.setAssist(PLACE_ON_MOVE, false) 
        player.runChatCommand("pyramid" + (size - 2)) 
    } 
}) 
```

## Step 12

Go into Minecraft and test the **pyramid** chat command.

### Full Code: 

```blocks
player.onChat("pyramid", function (size) { 
    if (size > 0) { 
        agent.setItem(SANDSTONE, size * size, 1) 
        agent.setSlot(1) 
        agent.setAssist(PLACE_ON_MOVE, true) 
        for (let i = 0; i <= 0 - 0; i++) { 
            agent.move(FORWARD, size) 
            agent.turn(LEFT_TURN) 
        } 
        agent.move(UP, 1) 
        agent.setAssist(PLACE_ON_MOVE, false) 
        player.runChatCommand("pyramid" + (size - 2)) 
    } 
}) 
```
