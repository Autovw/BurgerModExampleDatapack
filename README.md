### Creating a Datapack for the Burger Mod.

When I first started developing the Burger Mod I wanted the mod to support datapacks.

Datapacks can be useful to modify crafting recipes, loot drops, store commands etc. What's so cool about datapacks is that you don't have to change any of the code in the game or mod!

As of version 1.6.0 of the Burger Mod you are given to ability to overwrite/change crafting recipes and advancement recipes using a datapack.

If you don't know how to create a datapack I recommend watching [this tutorial by Legitimoose](https://www.youtube.com/watch?v=ac6V5-KT6Rg) first.

The datapack I created is called ``exampledatapack``.
So keep in mind to change ``exampledatapack`` to whatever namespace you're going to use.

#### Step 1:
Go into the ``datapacks`` folder of your world, and create a new folder with the name of your datapack.

#### Step 2:
Open the folder you've just created in Visual Studio Code (or whatever program you're using).

#### Step 3:
Create a new file called ``pack.mcmeta`` and copy/paste to code below.
```mcmeta
{
    "pack": {
        "pack_format": 6,
        "description": "Example Datapack"
    }
}
```
The ``pack_format`` for Minecraft version _1.15 - 1.16.1_ is ``5``, _1.16.2 - 1.16.5_ is ``6`` and _1.17_ is ``7``.

You can change ``Example Datapack`` to whatever you like.

#### Step 4:
Inside the folder you've just created, create a new folder called ``data``.

Within the ``data`` folder, create 3 new folders:
* ``burgermod``
* ``exampledatapack`` _Note: make sure to use your own namespace!_
* ``minecraft``

#### Step 5:
Go into the ``minecraft`` folder, and create a new folder called ``tags``.
Inside ``tags`` create another folder called ``functions``.

Inside ``functions`` create 2 new files and copy/paste the code.
* ``load.json``

```json
{
    "values": [
        "exampledatapack:load"
    ]
}
```
* ``tick.json``

```json
{
    "values": [
        "exampledatapack:tick"
    ]
}
```

_Note: Again, make sure to use your own namespace instead of_ ``exampledatapack``_._

#### Step 6:
Now go back into your ``data`` folder. Then go into ``exampledatapack`` (namespace) and create a new file and copy/paste the code.
* ``load.mcfunction``

```mcfunction
tellraw @a [{"text":"[Datapack]"},{"text":" Example Datapack has been enabled","color":"green"}]
```

Whatever is inside this file will be executed when the ``/reload`` command is executed.

#### Step 7: Crafting Recipes:
Go back into your ``data`` folder, then go into the ``burgermod`` folder and create a ``recipes`` folder.

In this folder you can add/overwrite (burgermod only) crafting recipes. 

As an example, I'm going to overwrite the crafting recipe of the **Beef Burger**.

**Important!** When overwriting a crafting recipe make sure the file has the same name as the original crafting recipe json. These files can be viewed [here!](https://github.com/Autovw/BurgerMod/tree/1.16.X-MCP/src/generated/resources/data/burgermod/recipes)

#### Example recipe, original can be found [here!](https://github.com/Autovw/BurgerMod/blob/1.16.X-MCP/src/generated/resources/data/burgermod/recipes/beef_burger.json)
```json
{
    "type": "minecraft:crafting_shaped",
    "pattern": [
      " B",
      "EC",
      " B"
    ],
    "key": {
      "B": {
        "item": "minecraft:wheat"
      },
      "C": {
        "item": "minecraft:cooked_beef"
      },
      "E": {
        "item": "burgermod:fried_scrambled_egg"
      }
    },
    "result": {
      "item": "burgermod:beef_burger",
      "count": 4
    }
}
```

As an example I changed ``minecraft:bread`` to ``minecraft:wheat`` and increased the amount of **Beef Burger**s given upon crafting to ``4`` instead of ``2``.

Don't want to write these ``.JSON`` files? Use [this generator for crafting recipes instead](https://crafting.thedestruc7i0n.ca)!

#### Step 8: Advancements Recipes:
Go back into the ``burgermod`` folder and create a new folder called ``advancements`` inside.

Inside the ``advancements`` folder create a new ``recipes`` folder, and inside ``recipes`` a new folder called ``burgermod``.

You can find the files inside this folder [here!](https://github.com/Autovw/BurgerMod/tree/1.16.X-MCP/src/generated/resources/data/burgermod/advancements/recipes/burgermod)

When overwriting an advancement recipe make sure to use the exact same names.

#### Step 9: Loading the datapack in the game:
What's so cool about datapacks is that you can work on it while also being in the game. Make sure all of the files are correctly saved and use the ``/reload`` command to apply the changes to the game.


##### And... That should be it!

There are so many other things you can do with datapacks, but I can't make a tutorial on all of them of course.

Want to create an Add-on for the Burger Mod? I have a short guide on [how to start developing with the mod](https://github.com/Autovw/BurgerMod/wiki/Developing)!

### The Example Datapack I created can be viewed/downloaded [here!](https://github.com/Autovw/BurgerModExampleDatapack)
