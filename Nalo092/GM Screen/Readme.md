# Adding to your Vault
There are two folders, one labeled `gm_5escreen.zip` and `5e GM Screen.zip`. The zip with `gm_` is intended to be drag and drop into your vault with no (knock-on-wood) compatibility issues with your current vault. This is due to all notes, attachments and files being named `gm_fileName`.

If you are starting a fresh vault or do not believe compatibility or name conflicts will be an issue feel free to use the other ZIP. I made two variants due to conflicts I encountered in my own vault when integrating. 

Most people who probably will grab this vault will already have the plugins enabled below, but if not the plugins below are listed.


# Required Plugins
1. [Dataview](obsidian://show-plugin?id=dataview)
2. [Meta Bind](obsidian://show-plugin?id=obsidian-meta-bind-plugin)
3. [Pathfinder 2e Icons](obsidian://show-plugin?id=pf2-action-icons)
	- Only needed if using the PF2e GM screen, and only if you want Icons.

## Optional Plugins (Highly Recommended)
1. [ITS Theme](https://github.com/SlRvb/Obsidian--ITS-Theme)
	- [ITS Documenation](https://publish.obsidian.md/slrvb-docs/ITS+Theme/ITS+Theme)
2. [Admonition](obsidian://show-plugin?id=obsidian-admonition)
3. [Dice Roller](obsidian://show-plugin?id=obsidian-dice-roller) 
4. [Style Settings](obsidian://show-plugin?id=obsidian-style-settings)
5. [Leaflet](obsidian://show-plugin?id=obsidian-leaflet-plugin)

# Adjustments for your Campaign
This part is meant for people who are new to Obsidian to help show what they need to change in order to apply this to their campaign.

## Cards
1. On the section of "Campaign Maps" of the DM screen replaces the tag `#campaginmaps` with whatever universal tag you use for your current campaign. (see aside)
 >[! aside| clean]
>
>>```
>>[!cards| dataview] 
>> ```dataview 
>> TABLE
>> FROM #campaginmaps
>> ```
>
> **to** 
> 
>> ```
>>[!cards| dataview] 
>> ```dataview 
>> TABLE
>> FROM #CoSmaps
>> ```
2. To add actions, house rules, or system rules to your **Rules Reference** or **Actions Reference** section include the following in your Front Matter
	1. add the tag `#5eR-ref`  to the rule you want to reference
	2. add the tag `#5eaction` to the action you want to reference
## Tables
1. To add any custom healing items or conditions to your screen make sure the following applies
	1. For healing items,  include in your Front Matter `effect: short exerpt of effect` , `cost: ## gp` and use the tag `#5ehealing`
	2. For conditions, include in your Front Matter  `effect: short exerpt of effect` and use the tag `#5econdition`
	3. This will add whatever your notes you have tagged to your tables


>[! info| background-color-yellow]- Sources
> ##### Exploration and Downtime Activities
> - [Nothing to Do: A Guide on Downtime](https://www.reddit.com/r/dndnext/comments/apblrv/nothing_to_do_a_guide_on_downtime/)
> ##### Icons and Images
> - [Baldur's Gate 3 Wiki](https://bg3.wiki/)
> - [Map of Faerun](https://www.reddit.com/r/TyrannyOfDragons/comments/157u4ri/map_of_faerun/)
> ##### Settings
> - Map Template (A wizard named Dave37)