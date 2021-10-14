## Creating a datapack for the Burger Mod

Ever wanted to change the crafting recipes from the Burger Mod? \
Well, that's possible using datapacks!

### Datapacks, what are they?
Datapacks can be useful to modify crafting recipes, loot drops, store commands etc. What's so cool about datapacks is that you don't have to change any of the code in the game or mod!

**This tutorial will target Burger Mod 2.0.0 and higher!**

If you do not know how to create a datapack I recommend watching [this tutorial by Legitimoose](https://www.youtube.com/watch?v=ac6V5-KT6Rg) first.
There's also documentation on the [Minecraft Wiki](https://minecraft.fandom.com/wiki/Data_pack).

For this tutorial I have created a datapack called ``exampledatapack``.
So keep in mind to change ``exampledatapack`` to whatever namespace you're going to use.
Make sure it's unique!

***

#### Step 1:
Go into the ``datapacks`` folder of your world, and create a new folder with the name of your datapack.

***

#### Step 2:
Open the folder you've just created in Visual Studio Code (or whatever program you're using).

***

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
Make sure you are using the correct ``pack_format``!

| Version range |``pack_format``|
|---------------|---------------|
|1.13 - 1.14.4  |``4``          |
|1.15 - 1.16.1  |``5``          |
|1.16.2 - 1.16.5|``6``          |
|1.17 - 1.17.1  |``7``          |
|1.18           |``8``          |


You may change ``Example Datapack`` to whatever you like.

***

#### Step 4:
Inside the folder you've just created, create a new folder called ``data``.

Create a new folder within the ``data`` folder called ``burgermod``.

***

#### Step 5: Crafting recipes:
Go back into your ``data`` folder, then go into the ``burgermod`` folder and create a ``recipes`` folder. \
In this folder you may add/overwrite (burgermod only) crafting recipes. 

As an example, I'm going to overwrite the crafting recipe of the **Beef Burger**.

**Important!** When overwriting a crafting recipe make sure the file has the same name as the original crafting recipe json. These files can be viewed [here!](https://github.com/Autovw/BurgerMod/blob/1.16.X/src/main/resources/data/burgermod/recipes)

#### Example recipe, original can be found [here!](https://github.com/Autovw/BurgerMod/blob/1.16.X/src/main/resources/data/burgermod/recipes/beef_burger.json)
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

As an example I have changed ``minecraft:bread`` to ``minecraft:wheat`` and increased the amount of **Beef Burger**s given upon crafting to ``4`` instead of ``2``.

Don't want to write these ``.JSON`` files? Use [this generator for crafting recipes instead](https://crafting.thedestruc7i0n.ca)!

***

#### Step 6: Advancement recipes:
Go back into the ``burgermod`` folder and create a new folder called ``advancements`` inside. \
Inside the ``advancements`` folder create a new folder called ``recipes``.

You can find the files inside this folder [here!](https://github.com/Autovw/BurgerMod/blob/1.16.X/src/main/resources/data/burgermod/advancements/recipes)

When overwriting an advancement recipe make sure to use the exact same names.

***

#### Step 7: Loading the datapack in the game:
What's so cool about datapacks is that you can work on it while also being in the game. Make sure all the files are correctly saved and use the ``/reload`` command to apply the changes to the game.

***

##### And... that should be it!

There are so many other things you can do with datapacks, but I can't make a tutorial on all of them of course.

Want to create an Add-on for the Burger Mod? I have a short guide on [how to start developing with the mod](https://github.com/Autovw/BurgerMod/wiki/Developing)!

### The Example Datapack I created can be viewed/downloaded [here!](https://github.com/Autovw/BurgerModExampleDatapack)
