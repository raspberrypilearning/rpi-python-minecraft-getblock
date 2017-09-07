- To find a block ID in Minecraft, the module needs to be imported and a connection made to the Minecraft game.

```python
import mcpi.minecraft as minecraft
mc = minecraft.Minecraft.create()
```

- You can find the block at any position in the Minecraft world, by using it's `x`, `y` and `z` coordinates.

```python
block_id = mc.getBlock(0, 0, 0)
print(block_id)
```

- You should see a number being printed in the Python shell. You can then lookup the block ID. For instance

	```
	Air:   0
	Stone: 1
	Grass: 2
	Dirt:  3
	Water: 8
	Sand: 12
	Ice:  79
	```
You can find a larger list of block IDs [here](http://www.stuffaboutcode.com/p/minecraft-api-reference.html){:target="_blank"}

- It is often more useful to know the block ID of a block relative to the player's position. To do this you need to first find the player's `x`, `y` and `z` coordinates. This code for instance, will find the ID of the block beneath the player.

	```python
	import mcpi.minecraft as minecraft
	mc = minecraft.Minecraft.create()

	x, y, z = mc.player.getTilePos()
	block = mc.getBlock(x, y-1, z)
	print(block)
	```
