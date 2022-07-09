### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Secure the Area

## Step 1
让小机器人建造 **橡木 栅栏**. 小机器人需要在它的右侧建造 **橡木 栅栏** , 并且破坏阻拦行动的土块. 这面栅栏墙应当有 **17 格长** . 

#### ~ tutorialhint
确保小机器人在右侧放置栅栏并破坏阻拦前行的方块。

```blocks
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
            }
})
```
```ghost
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
        agent.place(RIGHT)
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    }
})
``` 

