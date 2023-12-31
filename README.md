# Osu-Replay-Editor

This thing let you edit .osr files (osu! replays)

CLI was separated from [this repository](https://github.com/OlegSuperBro/Osu-Replay-Editor)

## How to use it

#### Installation

1. Install python
2. Install requirement by running ```pip install -r osrparse==7.0.0```
3. Run ```python CLI.py``` too see all avalable commands or check [CLI](#cli) section

There only 1 known issue:

Replay that have skips, getting broken. It's problem in osrparse module. You can check [this issue](https://github.com/kszlim/osu-replay-parser/issues/41) to get more info

### From Build

#### CLI

| Argument   | Usage                                    | Description                     |
|------------|:----------------------------------------:|---------------------------------|
| path       | ```CLI.py [path] ```                   | Path to replay/directory with replays|
| -o         | ```CLI.py -o [path] ```                | Can be either file name (for single file) or directory (for single and multiple files). If it's file name, write edited replay in \[path\]. If it's directory, write all replays in that directory with names from 0 to inf (0.osr, 1.osr, ...) |
| --info     | ```CLI.py --info ```                   | Show info about replay/replays (Show info AFTER changing)|
| --nickname | ```CLI.py --nickname [name] ```        | Change nickname in replay to provided |
| --n300     | ```CLI.py --n300 [0-65535] ```         | Change amount of 300s. Represented as unsigned short |
| --n100     | ```CLI.py --n100 [0-65535] ```         | Change amount of 100s. Represented as unsigned short |
| --n50      | ```CLI.py --n50 [0-65535] ```          | Change amount of 50s. Represented as unsigned short |
| --ngekis   | ```CLI.py --ngekis [0-65535] ```       | Change amount of gekus. Represented as unsigned short |
| --nkatus   | ```CLI.py --nkatus [0-65535] ```       | Change amount of katus. Represented as unsigned short |
| --nmisses  | ```CLI.py --n300 [0-65535] ```         | Change amount of misses. Represented as unsigned short |
| --score    | ```CLI.py --score [0-2147483647] ```   | Change displayed total score. Represented as int (can be negative if bigger than 2.147.483.647 ) |
| --maxcombo | ```CLI.py --maxcombo [0-65535] ```     | Change displayed maximum combo. Represented as unsigned short |
| --pfc      | ```CLI.py --pfc [True/False] ```       | Change visibility of "Perfect" text in life graph. |
| --mods     | ```CLI.py --mods [mod,mod,...] ```     | Change mods. Gameplay changing mods (hr, mr) can possibly break replay (but you can still make ez+hr :D). If ```--rawmods``` also provided, this arg is ignored|
| --rawmods  | ```CLI.py --rawmods [0-2147483647] ``` | Same as ```--mods``` but you can use [mod codes](https://osu.ppy.sh/wiki/en/mainent/File_formats/Osr_(file_format)) |
| --time     | ```CLI.py --time [0-inf] ```           | Change when replay was played. Use [converter](https://www.datetimetoticks-converter.com/) |
