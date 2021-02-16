# Open Game Asset Structure

## Open Game Asset Structure for Artists 
The Open Game Asset Structure is a simple structure for storing game assets and getting them into a game. It aimes to simplyfy asset managment for Artists because they are free to store the assets any way they like, without impacting the Coders. There are benefits in storing the assets in a semantic way, but that is not mandatory. 

General considerations for Artists are: 
* Binary files like Assets in a Game differ from text files like code and data formats, because it's hard to diff them. Storing diffs in a Version Control System like Git is pointless as graphics and sound change greatly by tools and automatic compression. Git and GitHub support the Large File System (LFS) repositories who do not diff the files, but store them as a whole, making them asset specific repositories. 
* being able to compare file versions side by side and thus quickly judge if the changes are an improvement, is most easily done by having multiple versions of the file worked on saved with a postfix version number. For instance figure_v01.png, figure_v02.png, figure_v03.png in the same folder can be put into a slideshow to see the progress of the figure.png file, much faster then any the UI of a version control system can. The folder with the multiple versions may be considered a "Working" folder and the final version may end up in it's parent folder or somewhere else.
* The sort order in the folder is important as that enables quick comparisons. Grouping files by prepending something to their filenames is common practice.
* Working versions of drawings generally have much more features then a final version. It's common for a Working versions to have a layer with colored boxes functioning as a color pallet and layers to be able to add or remove features of the image. Final versions are generally optimized for display and stripped of all baggage. It makes sense to keep Working and Final version in separate folders, mimicked folder structures, separate branches or even separate repositories.
* Often an artist has to keep a Character consistent throughout the game. This concern is simplified if all things related to that character are put in the same folder. In another case the Scene is distinct from the rest of the game making it the nucleus where all related things should cluster around, thus everything related to the Scene should be in the same folder.
* Many formats have build in change tracking and layering, like for instance Adobe Photoshop files. Putting these files in a Version Control System could be unhelpful. 
* File extensions identify the type of the file quite clearly making functional folders like audio and image redundant as an indication method, although it can work as a division of labor for the Sound Technician and Graphic Artist.
* Artists do have a division of labor like audio, video and graphics designer, but generally there is much more image work in a game then anything else, making those divisions unbalanced. As graphics are divided up among artists, there will arise some logical scheme, around for instance components, scenes or characters, to not be in each others way.


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
      * characters
        * Shopkeeper
          * BaseImage_CUT_cutout
      * groups
        * faction
        * nation
        * city
        * tribe
      * locations
        * Home
          * Bedroom
          * Bathroom
          * Livingroom
        * Restaurant
      * determinations
        * statistics
        * trade
        * producers
        * consumers
      * props
        * BaseImage_CUT_cutout
      * supernumerary
        * NPC1
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
    

The multiplicity of the theatrical versions of Core Knowledge folders is done because it suggests these are broad terms containing many items.
    
The supernumerary is a term generally used in theatre. In film these are generally called Extra's.
Extra would be confusion, because such a general term could mean anything in a multidimensional folder structure.
