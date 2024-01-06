# MultiPad Skin Template
This is a skin model supported exclusively by MultiPad, in order to be easier to create, as you won't need to [create an APK for a skin](https://github.com/kimjisub/UniPad-theme-template) to use in MultiPad, and also to be more "Specific" to customize as much detail as possible of your virtual Launchpad.
# Details
## General
All skin templates have a ["skin_info.json"](#The "skin_info.json" file) file that will store all the information necessary for MultiPad to recognize and correctly apply the skin. The file structure may vary depending on the skin model, currently [basic](#Basic Model) and [advanced](#Advanced Template) model. All the information you need to be able to work with the skins is just below (The file structure you can use from the samples available in this repository). The Skins directory is "/MultiPad/Skins"
## The "skin_info.json" file
This file allows MultiPad to identify that directory as a Skin, so it is mandatory to have this file in your skin directory (Example: /MultiPad/Skins/My Custom Skin/skin_info.json). In it, there will be the necessary information that MultiPad needs to obtain the name, author, and version of that particular skin. In addition to this information, there will be some other information that will be needed to identify the type of skin.
## Basic Model
The basic model works the same as the Unipad skins, as I only need the common PNG's renamed as "chainled", "btn", "btn_", "phatom", "pahtom_", "playbg" and etc. In the basic model, the structure of the "skin_info.json" file will be as follows:
```
{
	"skin_name": "SKIN_NAME",
	"skin_author": "SKIN_AUTHOR_NAME",
	"skin_version": "SKIN_VERSION",
	"skin_type": "basic"
}
```
## Advanced Model
The advanced skin model is for those who are not lazy and want to make the skin as cool as possible, as you will be able to customize the pads individually. The difference between [Advanced Model](#Advanced Template) and [Basic Model](#Basic Model) is the ability to use a .png for each pad to create very specific skins, for example a very real skin from a Novation Launchpad. In the basic model, the structure of the "skin_info.json" files will be as follows:
```
{
	"skin_name": "SKIN_NAME",
	"skin_author": "SKIN_AUTHOR_NAME",
	"skin_version": "SKIN_VERSION",
	"skin_type": "advanced"
	"skin_pads": {
		"0,1": "png1.png",
		"0,2": "png2.png"
	}
}
```
Since this is a more advanced skin, it will soon be laborious, so I'll explain how this structure works:
- The "skin_pads" variable is a dictionary that should contain '"X_Y_COORDINATES": "PNG_NAME"', where '"X_Y_COORDINATES"' is the X and Y coordinates of the pad ('"1,5", "5,9", "4,6"', etc...) and '"PNG_NAME"' is the name of the png you want to use on this pad ('"pad1.png", "custompad.png", "37.png"', etc...) ... (Yes, I stated the obvious).

If you forget a button, MultiPad will replace it with the default PNG, for example:
- if you forget the coordinates "4.4", "4.5", "5.4" and "5.5", MultiPad will use the PNG "phatom_" present in the skin.
- if you forget the coordinate of the buttons that are not the "Chain/CC" buttons and the ones mentioned above, MultiPad will use the PNG "phantom" present in the skin.
- if you forget the coordinate for the "Chain/CC", MultiPad will use the "chainled" PNG present in the skin.
If a default PNG is not present in the skin, MultiPad will use the default skin's PNG.
Take a look at "skin_info.json" to better understand what I'm saying.
