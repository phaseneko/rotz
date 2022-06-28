# About RotZ
Retro of the Zombie (RotZ) is a text based roguelike game for NEC PC-8201 laptop computer.

# How to Play?
You can play RotZ either on a real NEC PC-8201 laptop or with VirtualT Emulator

## Play on NEC PC-8201
1. Make sure your laptop has at least 8K extended memory
2. Git clone the repo
3. Transfer all files inside 'Source' directory from PC to laptop via serial connection:
	For all '.DO' files, use Load(f1) COM:9N81XN from main menu before transfering the file, then save the file to '.DO' format
	For all '.BA' files, inside BASIC, execute command 'LOAD "COM:9N81XN"' and press enter before transfering the file, then 'SAVE' the file to '.BA' format
	Check https://www.web8201.net/default.asp?content=tech.asp to learn more about PC-Laptop file transfering
4. Run MKDATA.BA from main menu. Use the tool to build runtime item/tile/enemy data to be used by the game
	Now you should have these files:
	ITEM.DO ITEM.CO ITNAM.DO
	TILE.DO TILE.CO TLNAM.DO
	ENEMY.DO ENEMY.CO ENNAM.DO
	INTRO.DO
	MKDATA.BA MAPGEN.BA	ROTZ.BA
5. Run MAPGEN.BA to generate your own maps. Generated maps are stored in '.CO' format files
6. Run ROTZ.BA to launch the main game. When prompted asking for map name, input name of the map you've generate in step 5 (case sensitive. without '.CO' postfix)
7. Read 'Retro of the Zombie Survival Guide.pdf' for a complete explanation of how to play the game
8. Enjoy it! :)

![](https://github.com/phaseneko/rotz/blob/main/Image/Photo0.jpg)
![](https://github.com/phaseneko/rotz/blob/main/Image/Photo1.jpg)

## Play with VirtualT Emulator
1. Download VirtualT Emulator package from https://sourceforge.net/projects/virtualt/ and extract it
2. Copy PC8201 directory to the working directory of VirtualT Emulator, overwrite all. (You may want to backup all original files in case of data loss)
3. Launch VirtualT
4. Select menu Emulation->Model->PC-8201
					Emulation->Speed->Very CPU Friendly
					Emulation->Display->Solid Chars
5. Navigate to ROTZ.BA and press Enter
6. When asked Map Name, input one from TOWN1/TOWN2/TOWN3 and press Enter
7. Read 'Retro of the Zombie Survival Guide.pdf' for a complete explanation of how to play the game
8. Enjoy it! :)

![](https://github.com/phaseneko/rotz/blob/main/Image/Screenshot0.png)
![](https://github.com/phaseneko/rotz/blob/main/Image/Screenshot1.png)
![](https://github.com/phaseneko/rotz/blob/main/Image/Screenshot2.png)

# Modifying the Game
You can edit data assets ITEM.DO / TILE.DO / ENEMY.DO and use MKDATA.BA to build runtime data for game

## Data Asset Format

### ITEM.DO
(Max item num: 50)
ItemNum
ItemName
0. Break Chance /20
1. Fail Chance /20
2. Exception Chance /20
3. Weight
4. Function1
5. Function2
6. Value1
7. Value2

Item Functions:
0. Simple Item
1. Weapon
2. Food
3. Medicine
4. (Reserved)
5. (Reserved)
6. Carpentry
7. (Reserved)
8. Protection
9. Trading (Not implemented)
10. (Reserved)

### TILE.DO
(Max enemy num: 20)
0. Travel Cost /12
1. Search Cost /12
2. Encounter Chance /20
3. Item Drop Num
4. Max to 10 Pairs {Item Index & Item Drop Chance /20} (Must end with id=0)

### ENEMY.DO
(Max enemy num: 5)
0. Encounter Weight
1. Appear Day
2. Min Attack
3. Max Attack
4. Infect Chance /20
5. Miss Chance /20
6. HP
7. Min Num
8. Max Num
9. Item Drop Num
10. Max to 5 Pairs {Item Index & Item Drop Chance /20} (Must end with id=0)

## Code

All source code and data of this game are published under GPL licence. Please read LICENSE for detail.


