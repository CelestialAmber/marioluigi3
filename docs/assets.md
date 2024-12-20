# Assets
This file documents the purpose of various asset files in the game.
- [`/Player`](#player)

## `/Player`
- [`item.bin` and `item.nsbtx`](#itembin-and-itemnsbtx)
- [`obj.bin` and `obj.nsbtx`](#objbin-and-objnsbtx)

### `item.bin` and `item.nsbtx`
These files contains models, textures and animations for Link's equipment items.

The items consist of arrow, headless arrow, bomb, bombchu, bombchu destination, bow, hammer, red potion, purple potion, yellow
potion, grapple hook, shovel, wooden shield, Oshus's sword and the phantom sword.

`item.bin` is compressed and contains three files:
- `item.nsbca`: Joint animations
    - Hammer idle/swing
    - Shield block
- `item.nsbma`: Unknown
- `item.nsbmd`: Models

Lastly, `item.nsbtx` contains textures.

These files are loaded by `ItemModelLoader` and are stored in `ItemManager` in the field `mItemModels`.

### `obj.bin` and `obj.nsbtx`
These files contains models, textures and animations for dungeon items.

The items consist of boss key, force gems, circle crystal, square crystal and triangle crystal.

`obj.bin` is compressed and contains two files:
- `obj.nsbmd`: Models
- `obj.nsbtp`: Material animations
    - Force gem colors

Lastly, `obj.nsbtx` contains textures.

These files are loaded by `ItemModelLoader` and are stored in `ItemManager` in the field `mDungeonItemModels`.
