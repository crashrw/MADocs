# File Formats
___
Quick reference guide of every format and what they do

## Archive Formats
___

### .mst
Archive Format

**M**a**st**er
___

An archive file that stores most of the other files within the game.
The easiest comparison is a .zip or .7z file with no compression.

MA_WIN can generate an asset log to "optimize load times" for the game, 
PASM can take this file and use it as a reference for how to "optimize" the MST to reduce load times.
This process also "locks" it to prevent further modifications. You can "unlock" the mst
however it undos the optimization.

- mettlearms_gc.mst - Found in all GameCube releases
- mettlearms_xb.mst - Found in all Xbox releases
- MASTRPS2.MST - Found in all PlayStation 2 releases

___

| Tool                                    | Description                 |
| --------------------------------------- | --------------------------- |
| [https://github.com/dj0wns/DJs\_MA\_TOOLs/blob/master/mst\_extract.py](https://github.com/dj0wns/DJs_MA_TOOLs/blob/master/mst_extract.py) | The most feature complete python script for extracting the contents of the MST file, currently works with GameCube and Xbox, PS2 is not supported.
| [https://github.com/amPerl/MATools/blob/master/tools/extract.py](https://github.com/amPerl/MATools/blob/master/tools/extract.py)             | The very first MST extractor ever created, rendered obsolete by the tool above, this one's only advantage is PS2 MST support.      

### .blt
Archive Format (PS2 Exclusive)

**B**o**lt**
___

Archive Format developed and used by Mass Media

## 3D Model Formats
___

### .ape
3D Model Format

**Ape**
___

No Documentation yet

### .wld
3D Model Format

**W**or**ld**
___

Wld Files are the format used to store each level in the game.

The terrain of the level is broken up into cells. Each cell is a region
of the level is formatted the same as the .ape file

## Texture Formats
___

### .tga
Texture Format

???
___

No Documentation yet

## Animation Formats
___

### .mtx
Model Animation Format

???
___

Mtx Files store the animation data for each of the ape files that store a hierarchy.

### .cam
Camera Animation Format

**Cam**era
___

Cam Files store camera animations used as part of scripted sequences

## Audio Formats
___

### .sfb
Audio Format

???
___

The file format is currently unknown as to it's purpose, more research
is required.

### .wvb
Audio Format

???
___

No Documentation yet

### .wvs
Audio Format

???
___

No Documentation yet

### .pss
Audio Format (PlayStation 2 Exclusive)

???
___

Pss is a file format found exclusively in the PS2 version of Metal Arms.

It can be implied these are video formats based on the observation that they
are found within folders named VIDEO1 and VIDEO2 on the PS2 ISO. Not much
beyond that however is known.

## Configuration Formats
___

### .csv
Config Format

**C**omma **S**eperated **V**alues (CSV)
___

Binary Files that control different components of the game such as what skybox to spawn
on a level or how large a clip for a weapon should be.

These files were originally .csv files similar to excel spreadsheets
or google sheets. It is possible to decompile them back into .csv but they
will lack comments or formatting

Each .csv is composed of tables and entries. Tables are pointers to regions of entries.
Each .csv will have it's own unique set of tables of entries whose purpose is only known
to the game code itself.

___

| Tool                                    | Description                 |
| --------------------------------------- | --------------------------- |
| [https://github.com/dj0wns/DJs\\_MA\\_TOOLs/blob/master/mst\\_extract.py](https://github.com/dj0wns/DJs_MA_TOOLs/blob/master/mst_extract.py) | When contents of the MST are extracted, the extractor automatically converts the binary CSV files back to their original CSV representation.

## Scripting Formats
___

### .sma
Script / Code Format

**sma**ll
___

Sma files are the script files used by the Small Programing Language.

It is believed that the Small language is interpreted, meaning that every
executable of Metal Arms has a Small interpreter compiled in.

Extensive testing along with R&D required.

## Miscellaneous Formats
___

### .rdx
Misc Format (Xbox Exclusive)

**R**egular **D**ata **X**box
___

No Documentation yet

### .rdg
Misc Format (GameCube Exclusive)

**R**egular **D**ata **G**ameCube
___

This file format, only found in GameCube Msts is related to sound effects.

6 variations

| Name                                    | Description                                                                     |
| ---                                     | ---                                                                             |
| snd_smpls.rdg                           | Renamed Musyx .samp file                                                        |
| snd_init.rdg                            | Musyx .sdir, .pool & .proj packaged together                                    |
| mabannerp.rdg                           | Renamed GameCube .tpl file, GameCube Save File Banner                           |
| maicon.rdg                              | Renamed GameCube .tpl file, GameCube Save File Icon                             |
| l?.rdg                                  | Where ? is the name of a wld without the first character, UNKNOWN PURPOSE       |
| ?.rdg                                   | Where ? corresponds to a .sfb file sharing the same name, audio related         |

| Tool                                    | Description                 |
| ---                                     | ---                         |
| [https://github.com/Nisto/musyx-extract](https://github.com/Nisto/musyx-extract)  | Tool that uses .sdir and .samp files as input and generates .dsp audio files that can be read by most Audio Players |            
| [https://github.com/libertyernie/brawltools/releases](https://github.com/libertyernie/brawltools/releases) | Tool that can read mabannerp.rdg & maicon.rdg when their extension is renamed to .tpl |  

## AI Pathfinding Formats
___

### .gt
Pathfinding Format

???
___

Gt files are responsible for all the AI pathing required for a wld. Pathfinding
relies on a series of connected nodes. From this information it can be inferred
that Metal Arms uses a form of A* pathfinding.

## Particle Effect Formats
___

### .fpr
Particle Effect Format

**F**ang **P**a**r**ticle
___

Stores particle effects.
All particles are made up of camera facing quads.

Particle files are proven to be quite powerful, even having the ability to cast
realtime shadows if enabled! However the full potential of the fpr file is currently
unknown, extensive testing required.

## Video Formats
___

### .bik
Video Format

**bik**
___

Bik is a file format for prerendered videos used for some of the cutscenes in the game.

## Font Formats
___

### .fnt
Video Format

**F**o**nt**
___

Used to indicate how a .tga texture can be rendered as a font


## Tool Formats
___

### .aid
Tool Format

???
___

Used as a metadata file when compiling an asset with PASM.






