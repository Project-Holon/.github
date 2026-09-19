# Project Holon

A from-scratch decompilation of Pokémon Black, a native PC port built on it,
and a modding suite for the port.

The repositories are private while the work is in progress, so the overview
below describes what each one holds rather than linking to it. They open
publicly as they reach a state worth reading.

## Projects

| project | what it is | state |
|---|---|---|
| aletheia | Byte-matching decompilation of Pokémon Black with its own tooling and asset converters; rebuilds a ROM identical to the original from your dump | Matching in progress; all asset formats decoded with round-trip converters |
| eidos | Native PC port: the matched game code compiled for the host, with our own platform layer and DS hardware shims | 2D engine and frame loop running matched code; opens a window and draws |
| kenon | Modding suite for the port: script assembler, table and sprite editors, mod packaging | Planned; starts when eidos runs the game |

## How they fit together

```
your own cartridge dump
        |
     aletheia   extracts, disassembles, matches; ships tools and matched C
        |
      eidos     compiles the matched C for PC, replaces the DS hardware
        |
      kenon     edits the unpacked data the port loads
```

## Rules that hold across every repository

- No game data is ever committed or distributed: no ROMs, no extracted or
  converted assets, no disassembly, no vendor SDK. Everything is derived from
  the user's own legally obtained cartridge on their own machine.
- The tooling, the port and the modding suite are MIT licensed. The
  reverse-engineered game source in aletheia carries no license grant and
  remains the property of Nintendo, Creatures Inc. and GAME FREAK inc. Each
  repository has a `LEGAL.md`.
- Pokémon and Nintendo DS are trademarks of Nintendo. This organisation is
  not affiliated with or endorsed by Nintendo, Creatures Inc. or GAME FREAK inc.

## Where to start

Each project's README covers its own state: aletheia's the state of the
decompilation and how to build the matching ROM from your dump, eidos's the
port, its tests and the first-run design, kenon's what the modding suite will
cover.
