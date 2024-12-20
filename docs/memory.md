# Memory
This file documents what is known about memory management in the game.
- [Allocation IDs](#allocation-ids)

## Allocation IDs
Many heap-allocated objects have a 4-character ID associated with it. This table shows all known IDs and their respective
meanings or translations.

> [!NOTE]
> These IDs will appear in memory in reverse order. This is because allocation IDs are often interpreted as 32-bit integers,
> and integers are stored in little-endian which effectively "reverses" the character order.

 ID    | Translation     | Meaning
-------|-----------------|---------
`EDGM` | Edge manager    | ?
`EXPH` | ?               | SysObject
`MESG` | Message manager | ?
`IMNG` | Item manager    | ?
