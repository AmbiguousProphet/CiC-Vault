---
type: character
aliases: []
cover:
world: Saltmarrow
species: human
mind:
age:
body_age:
status: active
rating: sfw
based_on:
tags: [character]
created: 2026-11-05
---
# Mara Quill
> A smuggler captain who'd rather sink her own ship than hand it over.

*Essentials only: what holds in every story. Story-specific ages, roles and drift go in profiles.*
*`age` and `body_age` only when they hold in every story; otherwise set them on each profile. `mind` is for nonhumans: how it thinks and communicates.*

## Signature features
*What survives every story, stage and setting: silhouette, colors, voice tics, core drive.*
- Oilskin coat, a burn scar across one palm, and a habit of counting exits.

## Appearance
*The core look, head to toe. Drift between stories belongs in profiles.*
- **Build:** wiry, rope-strong
- **Skin:** 
- **Hair:** black, cropped short
- **Eyes:** grey
- **Face:** 
- **Distinguishing marks:** 
- **Default outfit:** 

## Personality
- Proud, funny when cornered, and bad at asking for anything.

## Under pressure
*How they react when cornered, threatened or overpowered: fight, bargain, freeze, comply, break. What it takes to get there.*
- Bargains first, mocks second. Goes quiet and obedient only when her crew is the price, and hates herself for it.

## Voice
*How they talk, then a few sample lines in different moods.*
- Short, dry, sailor's slang.
- "Put it on the tab. The big one."
- "You want the ship, you swim for it."

## Variants
*Recurring versions: life stages, forms, later fates, one-off reuses. One line each; the details live in that version's profile.*
- **Variant** (stage): what changes

## Core history
*Only what's true in every story. Story-specific backstory goes in profiles.*


## Recurring ties
*Relationships that hold in most stories. Story-specific family and roles go in profiles.*
- [[ ]] — 

## Profiles
```base
filters:
  and:
    - 'type == "profile"'
    - file.hasLink(this.file)
views:
  - type: table
    name: Profiles
    order:
      - file.name
      - profile_type
      - stage
      - age
      - rating
```

## Gallery
*Drop images into this character's `images` folder. Adult images go in `images/adult` and stay out of this view.*
```base
formulas:
  pic: 'image(file.path)'
filters:
  and:
    - 'file.inFolder(this.file.folder + "/images")'
    - 'file.ext == "png" || file.ext == "jpg" || file.ext == "jpeg" || file.ext == "webp"'
    - not:
        - 'file.inFolder(this.file.folder + "/images/adult")'
views:
  - type: cards
    name: Gallery
    image: formula.pic
    imageFit: cover
    order:
      - file.name
    sort:
      - property: file.ctime
        direction: DESC
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

