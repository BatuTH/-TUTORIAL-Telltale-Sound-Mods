# Telltale-Sound-Mods-Tutorial
A tutorial detailing how to create sound mods for any Telltale Game. I will be demonstrating how to achieve this with the Telltale Definitive Edition, but this can also be done for any earlier games or versions using this method.

NOTE: This is subject to change as we continue to work on the mod tools (which will allow the creation and installation of these mods with ease), but for the time being. This is how you create a sound mod.

A brief summary of the steps and process necessary to create a sound mod for a Telltale Title. 
```
1. Locate the game archive in which you wish to modify. 
2. Extract the archives contents to a location.
3. Replace the files that you wish to change.
4. Repackage the game archive.
5. Replace the archive in the game files with the modified one.
```

## STEP 1: Locate the game archive in which you wish to modify. 
**What is an Archive File?** An archive is a packaged file containing the resources and assets that the game utilizes, their extension ends in ".ttarch2". There are multiple archives associated with a game and each contain different resources. As to what an archive contains can be inffered by their naming scheme. For example "txmesh" stands for textures and meshes, meaning that the archive contains the textures and model assets. In this case we are looking for "ms" which stands for music and sound. Another archive that has sounds as well is the "voice" archive, which contains all of the voice recordings for the characters. 

**How do I know what sounds I can replace?** For exploring the sounds/assets that are in an archive I recomend that you use the **Telltale File Explorer** tool, which allows you to browse through the archive to the view textures, sounds, and even scripts (it can also be used for extracting this data as well). 

The **Telltale File Explorer** tool can be downloaded with the following link.
https://quickandeasysoftware.net/software/telltale-explorer

**I recomend making two copies of the archive you will be modifying, one as a backup incase your modifications end up making the game not load. The other is the archive you will be modifying and overwriting.**

## STEP 2: Extract the archives contents to a location.
Using a tool called **ttarchext**, which is a command line application (meaning that you will need to use command prompt to use it, I will teach you how to use this in a moment). This tool will extract the raw data from an archive and dump it into a desired folder.

The tool can be found in this website, and it's full name is **Telltale TTARCH files extractor/rebuilder 0.3.2**
https://aluigi.altervista.org/papers.htm

Before extracting an archive, create a folder that will contain the extracted data of the archive.
When you have the application downloaded and extracted (preferably in a seperate folder) open up windows command prompt and use the following **pusdeo** command to extract the archive **(NOT EXACTLY AS WRITTEN)**

```
"ttarchext.exe path" 67 ".ttarch2 archive path" "output folder path"
```

- Where **"ttarchext.exe path"** is the path/location of the ttarchext.exe application. You can write the path of the ttarchext.exe application or drag it to the command prompt window and it will automatically write the path.
- Where **67** is the value used by the ttarchext application to determine what game version to use to extract/build the archive. 67 in this case is for the Definitive Series version, if you are using a different game/version then just write (or drag) the path of the ttarchext.exe application and hit enter. This will give you the version numbers as well as additional information on how to use the application.
- Where **".ttarch2 archive location"** is the path/location of the archive you wish to extract. Again you can write the path of the .ttarch2 archive in command prompt, or you can drag it to the command prompt window and it will automatically write the path.
- Where **"output folder path"** is the path/location of the folder you wish to dump the .ttarch2 archive's contents to. In this case it should be a folder you created to contain the contents of the extracted archive. Once again with command prompt you can write the path of your output folder, or you can drag the output folder to command prompt and it will write the path for you.

If everything is done correctly it should look something like this

```
C:\Users\[name]>A:\Steam\twd-definitive\ttarchext\ttarchext.exe 67 A:\Steam\twd-definitive\weaponSoundMod\season1-sounds\WDC_pc_ProjectSeason1_ms.ttarch2 A:\Steam\twd-definitive\weaponSoundMod\season1-sounds\WDC_pc_ProjectSeason1_ms
```

For your convience here is the list of game version values used by ttarchext.
```
 0   Wallace & Gromit: Episode 1: Fright of the Bumblebees
 1   Wallace & Gromit: Episode 2: The Last Resort
 2   Wallace & Gromit: Episode 3: Muzzled
 3   Telltale Texas Hold'em
 4   Bone: Out From Boneville
 5   Bone: The Great Cow Race
 6   Sam & Max: Episode 101 - Culture Shock
 7   Sam & Max: Episode 102 - Situation: Comedy
 8   Sam & Max: Episode 103 - The Mole, The Mob, and the Meatball
 9   Sam & Max: Episode 104 - Abe Lincoln Must Die!
 10  Sam & Max: Episode 105 - Reality 2.0
 11  Sam & Max: Episode 106 - Bright Side of the Moon
 12  Sam & Max: Episode 201 - Ice Station Santa
 13  Sam & Max: Episode 202 - Moai Better Blues
 14  Sam & Max: Episode 203 - Night of the Raving Dead
 15  Sam & Max: Episode 204 - Chariots of the Dogs
 16  Sam & Max: Episode 205 - What's New, Beelzebub
 17  Strong Bad: Episode 1 - Homestar Ruiner
 18  Strong Bad: Episode 2 - Strong Badia the Free
 19  Strong Bad: Episode 3 - Baddest of the Bands
 20  Strong Bad: Episode 4 - Daneresque 3
 21  Strong Bad: Episode 5 - 8-Bit Is Enough
 22  CSI 3 - Dimensions of Murder / Bone demo
 23  CSI 4 - Hard Evidence (demo)
 24  Tales of Monkey Island 101: Launch of the Screaming Narwhal
 25  Wallace & Gromit: Episode 4: The Bogey Man
 26  Tales of Monkey Island 102: The Siege of Spinner Cay
 27  Tales of Monkey Island 103: Lair of the Leviathan
 28  CSI 5 - Deadly Intent
 29  Tales of Monkey Island 104: The Trial and Execution of Guybrush Threepwood
 30  CSI 4 - Hard Evidence
 31  Tales of Monkey Island 105: Rise of the Pirate God
 32  CSI 5 - Deadly Intent (demo)
 33  Sam & Max: Episode 301 - The Penal Zone
 34  Sam & Max: Episode 302 - The Tomb of Sammun-Mak
 35  Sam & Max: Episode 303 - They Stole Max's Brain!
 36  Puzzle Agent - The Mystery of Scoggins
 37  Sam & Max: Episode 304 - Beyond the Alley of the Dolls
 38  Sam & Max: Episode 305 - The City That Dares Not Sleep
 39  Poker Night at the Inventory
 40  CSI 6 - Fatal Conspiracy
 41  Back To The Future: Episode 1 - It's About Time
 42  Back To The Future: Episode 2 - Get Tannen!
 43  Back To The Future: Episode 3 - Citizen Brown
 44  Hector: Episode 1 - We Negotiate with Terrorists
 45  Back To The Future: Episode 4 - Double Visions
 46  Back To The Future: Episode 5 - OUTATIME
 47  Puzzle Agent 2
 48  Jurassik Park: The Game
 49  Hector: Episode 2 - Senseless Act of Justice
 50  Hector: Episode 3 - Beyond Reasonable Doom
 51  Law and Order: Legacies
 52  Walking Dead: A New Day
 53  Poker Night 2
 54  The Wolf Among Us
 55  The Walking Dead: Season 2
 56  Tales from the Borderlands (all episodes)
 57  Game of Thrones (all episodes)
 58  Minecraft: Story Mode
 59  The Walking Dead: Michonne
 60  Batman: The Telltale Series
 61  The Walking Dead: A New Frontier
 62  Marvel's Guardians of the Galaxy
 63  Minecraft: Story Mode - Season Two
 64  Batman: The Enemy Within
 65  Bone: Out From Boneville 2.0
 66  Bone: The Great Cow Race 2.0
 67  The Walking Dead: The Telltale Definitive Series
```

Now you just hit return to execute the program and extract the contents, be sure that the game is not open, or that the archive is open in another application like **Telltale File Explorer** for example or it will error. The final result return something like this.

```
  [bunch of other files]
  124a511e 468864     mus_loop_ambient_01_full.wav

- 2950 files found
- done
```

When you open the folder it will be filled with the contents and assets from the game archive.

## STEP 3. Replace the files that you wish to change.
The next step is to replace the files that you wish to change and this is fairly simple. 

The sound files found in Telltale Games are most often in a wavefront audio file format (.wav), though sometimes it could be .aif or even .mp3. **Make sure that when you create your sound file that it is of the same name and format as the orignal file that you are replacing.**

Assuming that all of your sound files are of the proper names and formats, for this step you just simply replace the files inside the extracted directory of the archive with your modified sound files and that's it!

## STEP 4. Repackage the game archive.
The next step now is to rebuild the archive with the modified contents. For this step, 

The following **pusdeo** command is used by ttarchext.exe to rebuild a game archive, **and you MUST rebuild the archive with the same game version value as you extracted the archive with.**

```
"ttarchext.exe path" -b -V 7 67 ".ttarch2 archive path" "input folder path"
```

- Where **"ttarchext.exe path"** is the path/location of the ttarchext.exe application. You can write the path of the ttarchext.exe application or drag it to the command prompt window and it will automatically write the path.
- Where **"-b -V 7"** is the arugments for telling ttarchext tool to rebuild an archive.
- Where **67** is the value used by the ttarchext application to determine what game version to use to extract/build the archive. 67 in this case is for the Definitive Series version, if you are using a different game/version then just write (or drag) the path of the ttarchext.exe application and hit enter. This will give you the version numbers as well as additional information on how to use the application. I've also listed the version numbers in **STEP 2** for your convience.
- Where **".ttarch2 archive location"** is the path/location of the archive you wish to replace. This should be the path of the .ttarch2 file that you duplicated earlier that will be modified. Again you can write the path of the .ttarch2 archive in command prompt, or you can drag it to the command prompt window and it will automatically write the path.
- Where **"input folder path"** is the path/location of the folder where extracted .ttarch2 archives contents that you modified. ttarchext.exe will take this folder and build it into a .ttarch2 archive. Once again with command prompt you can write the path of your input folder, or you can drag the input folder to command prompt and it will write the path for you.

If you've entered the commands in properly it should look something like this.

```
C:\Users\[name]>A:\Steam\twd-definitive\ttarchext\ttarchext.exe -b -V 7 67 A:\Steam\twd-definitive\weaponSoundMod\season1-sounds\WDC_pc_ProjectSeason1_ms.ttarch2 A:\Steam\twd-definitive\weaponSoundMod\season1-sounds\WDC_pc_ProjectSeason1_ms
```

When you hit return, ttarchext will ask you to overwrite the file. 

```
do you want to overwrite it (y/N/all)?
```

Type in "y" to overwrite the file and hit return to rebuild the folder into a .ttarch2 archive.
After completion the final output from command prompt should look something like this.

```
  [more files]
- import mus_loop_ambient_01_full.wav

- 2950 files found
- done
```

This means that the archive has been sucessfully rebuilt.

## STEP 5: Replace the archive in the game files with the modified one.
This step is fairly simple, you move the rebuilt archive file that you created into the game archive directory and replace it. Your done!

If you wish to share your mod with others you can put your modified archive file or files into a zip file and share them online with others.

## Conclusion
That's it, that is how you make a sound mod for a Telltale Game (Telltale Definitive Series) in this case. It's very simple to do and achieve, later on as work continues on the mod tools, it will be much simpler to make a sound mod (or other) without being as destructive as this is.

If you do not know where to start when it comes to creating, or editing sounds. You can use **Audacity** to create or edit sounds.
https://www.audacityteam.org/

If you do not know where to get sounds from, you can google around and find sound effects librarys to get sounds from, or you can download them from Youtube using a web based converter tool like **Youtube to MP3**
https://ytmp3.cc/en13/

If you wish to convert an audio file like .mp3 to a .wav format you can google for a web based converter tool like **Cloud Convert** for example.
https://cloudconvert.com/wav-converter
