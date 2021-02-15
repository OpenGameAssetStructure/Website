# Open Game Asset Structure

## Open Game Asset Structure for Artists 
The Open Game Asset Structure is a simple structure for storing game assets and getting them into a game. It aimes to simplyfy asset managment for Artists because they are free to store the assets any way they like, without impacting the Coders. There are benefits in storing the assets in a semantic way, but that is not mandatory. 

Binary files like Assets in a Game differ from text files like code and dataformats because it's hard to diff them. Storing diffs in a Version Control System like Git is pointless as graphics and sound change greatly by tools and automatic compression. Git and GitHub support the Large File System (LFS) repositories who do not diff the files, but store them as a whole, making them asset specific repositories. 

General considerations for Artists are: 
* being able to compare file versions side by side and thus quickly judge if the changes are an impovement, is most easily done by having multiple versions of the file worked on saved with a postfix version number. For instance figure_v01.png, figure_v02.png, figure_v03.png in the same folder can be put into a slideshow to see the progress of the figure.png file, much faster then any the UI of a version control system can. The folder with the multiple versions may be considered a "Working" folder and the final version may end up in it's parent folder or somewhere else.
* Working versions of drawings generelay have mcuh more features then a final version. Working versions generaly have a layer with colored boxes functioning as a color pallet and layers to be able to add or remove features of the image. Final versions are generaly optimised for display and stripped of all bagage. It makes sense to keep Working and Final version in seperate folders, branches or even repositories.
* Often an artist has to keep a Character consistent throughout the game. This concern is simplefied if all things related to that character are put in the same folder. In another case the Scene is distinct from the rest of the game making it the nucleus where all related things should cluster around, thus everything related to the Scene should be in the same folder.
* Many formats have build in change tracking and layering, like for instance Adobe PhotoShop files. Putting these files in a Version Control System could be unhelpfull. 
* File extensions identify the type of the file quite clearly making functional folders like audio and image redundant as an indication method, although it can work as a division of labor for the Sound Technisian and Graphic Artist. 

## Open Game Asset Structure for Coders
The Open Game Asset Structure is a layer of indirection insulating the code from changes to game assets. It also possible to complement missing assets to a previously downloaded assets zip file, by changing the ID-Asset list. The ID-Asset list is in the code repository and thus under full control of the coders.

Switching from game engine is currently harder then it needs to be. For high level game engines the bulk of the work is in the assets and less into coding. Coding is mainly limited to declarations and adding special effects. Idealy it should be possible to move the game from simple Gamebook, to Interactive Fixtion, to Visual Novel and ultimatly full fledged RPG without having to change the asset structure.


## Semantic Folder Structure
Example:

* assets
  * core
    * act1_prologue
      * scene_001_Home
      * scene_002_Work
      * scene_003_Hobby
    * act2_conflict    
      * scene_004_incitingIncident
    * act3_risingAction
      * scene_005_GoGoGoJustDoIt
    * act4_midpoint  
      * scene_006_ThinkAboutIt
    * act5_fallingAction    
      * scene_007_LearnNewWay
    * act6_finale
      * scene_008_Triump
    * act7_epilogue
      * scene_009_HappilyEverAfter
    * base
      * character
        * Shopkeeper
          * BaseImage_CUT_cutout
      * group
        * faction
        * nation
        * city
        * tribe
      * location
        * Home
          * Bedroom
          * Bathroom
          * Livingroom
        * Restaurant
      * determination
        * statistics
        * trade
        * producers
        * consumers
      * prop
        * BaseImage_CUT_cutout
    * static
      * ConfigurationMenu      
      * Credits
      * GameUi
      * generic
      * MainMenu
      * manual
      * PersistenceMenu
        * border
        * button
        * font
  * dlc
  * expansion
  * episode2
* code
  * C#_DCI
  * Python
  * Javascript
* data
  * Save
  * Maps
  * Config
* engine
  * renpy
    * Version1.25
  * gamemaker
    * version
* setup
  * renpy
  * gamemaker
    * installscripts
    * installers
