---
type: setting
aliases: []
cover:
world: Saltmarrow
status: active
rating: sfw
version: 1
tags: [setting]
created: 2026-11-05
---
# Saltmarrow
> A tidal harbor town where every hull pays the Tithe Court, and anyone who can't pay works it off.

*Untagged lines are canon. **[draft]** marks proposals waiting on approval.*

## Premise
Saltmarrow sits on a mudflat bay that empties twice a day. The Tithe Court owns the only deep-water berths and taxes everything that ties up. Debts to the Court are bought, sold and collected in person.

## Tone
Wet, cold harbor noir. Lamplight, rope, rot and money. Nobody here is clean.

## Core rules
*How magic, power and the setting's key mechanics work.*
- No magic. Power is berths, ledgers and who holds your paper.
- A Court debt can be paid in coin, cargo or labor, at the warden's rate.

## The wider world
*Only what presses on this setting. Leave the rest of the map alone.*
- 

## Places
- **The Long Quay:** the Court's deep-water berths and its counting house.
- **The flats:** mud at low tide, where the night market sets up.

## Peoples
*Species, kin and factions. For nonhumans, say how they think and communicate.*
- Humans only in this sample. Factions: the Court, the free captains, the dock gangs.

## Conflict axes
- Debtors against the Court.
- Free captains against the berth monopoly.

## Arc
*Stages or beats a story here moves through.*
1. A debt comes due.
2. Terms are set.
3. The terms change.

## Protagonist slot
*What's fixed for the user's character and what's left open.*
- **Fixed:** you owe the Court, or you collect for it.
- **Open:** who, how much, and why.

## Cast notes
*Who lives here and what they want. Full details go on character pages and profiles.*
- [[Mara Quill]]: a smuggler captain behind on her berth tithe.
- [[Tobias Rook]]: the tithe-warden who holds her paper.

## Lore entries
*One bullet each: a bold key, then a short entry. An entry loads into play when its key comes up; add more keys with slashes: **The Tithe Court / tithe-wardens / wardens:***
- **The Tithe Court / tithe-wardens / wardens:** the harbor's ruling guild; wardens collect in person and set their own rates.
- **The Low Tide Market / night market:** stalls on the exposed flats, gone when the water comes back.
- **The Long Quay:** the Court's berths; a ship without a tithe seal can't unload there.

## Open questions
- [draft] Who funds the free captains?

## Characters
```base
filters:
  and:
    - 'type == "character"'
    - file.hasLink(this.file)
views:
  - type: cards
    name: Characters
    image: note.cover
    imageFit: cover
    order:
      - file.name
      - status
```

## Stories
```base
filters:
  and:
    - 'type == "story"'
    - file.hasLink(this.file)
views:
  - type: list
    name: Stories
    order:
      - file.name
      - status
      - rating
```

## Notes


## Changelog
- v1 (2026-11-05): created
