# Project Holon

A from-scratch decompilation of Pokémon Black (and eventually White), a native PC port built on it,
and a modding suite for the port.

The repositories are private while the work is in progress, so the overview
below describes what each one holds rather than linking to it. They will open
publicly when they reach a state worth reading.

## Projects

| project | what it is | progression | state |
|---|---|---|---|
| aletheia | Byte-matching decompilation of Pokémon Black with its own tooling and asset converters; rebuilds a ROM identical to the original from your dump | 37% matched | Matching in progress; all asset formats decoded with round-trip converters |
| eidos | Native PC port: the matched game code compiled for the host, with our own platform layer and DS hardware shims | 46% of milestones | 2D engine and frame loop running matched code; opens a window and draws |
| kenon | Modding suite for the port: script assembler, table and sprite editors, mod packaging | 0% | Planned; starts when eidos runs the game |

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

## Where to start

Each project's README covers its own state: aletheia's the state of the
decompilation and how to build the matching ROM from your dump, eidos's the
port, its tests and the first-run design, kenon's what the modding suite will
cover.
