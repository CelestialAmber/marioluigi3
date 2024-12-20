# Items
This file documents what is known about items in the game.
- [Item IDs](#item-ids)
- [Item flags](#item-flags)

## Item IDs
See [Item.hpp](/include/Item/Item.hpp) for a list of known item IDs. Feel free to contribute to the list!

## Item flags
See [Item.hpp](/include/Item/Item.hpp) for a list of known item flags. Feel free to contribute to the list!

The item flags are different from item IDs, as the flags are used as an index to the `mItemFlags` in the [`ItemManager`](/include/Item/ItemManager.hpp)
class.

Interestingly, flags 0 through 10 are also the IDs of equipment items:

0. Sword
1. Shield
2. Boomerang
3. Shovel
4. Bomb Bag
5. Bow
6. Grappling Hook
7. Bombchu Bag
8. Hammer
9. Potion A
10. Potion B
