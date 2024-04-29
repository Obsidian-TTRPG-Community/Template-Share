---
cssclasses:
  - wide-page
mapdata:
  greens: 0
  river: 0
  gates: 0
  coast: 0
  size: 25
  seed: 655382547
tags:
  - template
Inhabitants: []
Type: 
bind_target: false
NotableNPCs: 
rumors: []
---

> [!infobox|n-th right wikipedia]+
> # `=this.file.name`
> ![[PlaceholderImage.png]]
>   ## [[art.png|Show To Players]]
> ---
> 
> ## Geography
> | DataType | DataInfo  |
> | ---- | ---- |
> | **Type** | `INPUT[LocalType][inlineListSuggester():Type]` |
> | **Region** | `INPUT[suggester(optionQuery(#Region)):Region]` |
> ##### Society
> | DataType | DataInfo |
> | ---- | ---- |
> | **Inhabitants** | `INPUT[inlineListSuggester(optionQuery(#race)):Inhabitants]` |
> | **Religions** | `INPUT[inlineListSuggester(optionQuery(#Religion)):Religions]` |
> | **Factions** | `INPUT[inlineListSuggester(optionQuery(#eoefaction)):Factions]` |


# Map
%%uses @MissArticulatePython Map Template%%
```meta-bind-embed
[[Map]]
```

# Overview

>[!column |clean no-icon alt-line no-t]
>> [!Info | clean dim wmed] Description:
>> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus dignissim pharetra eros a fringilla. Morbi a magna eget mauris auctor cursus at in neque. Cras aliquam, lorem at semper luctus, ex libero suscipit nisi, id malesuada mi nibh sit amet erat.
>
>> [!note| clean dim wmed] Notables:
>> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus dignissim pharetra eros a fringilla. Morbi a magna eget mauris auctor cursus at in neque. Cras aliquam, lorem at semper luctus, ex libero suscipit nisi, id malesuada mi nibh sit amet erat.
>
>> [!important | clean dim wmed]  Features:
>> - Lorem ipsum dolor 
>> - sit amet, consectetur adipiscing elit. 
>> - Phasellus dignissim pharetra eros a fringilla. 
>
>> [!location| clean dim wmed]  Environment:
>> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus dignissim pharetra eros a fringilla. Morbi a magna eget mauris auctor cursus at in neque. Cras aliquam, lorem at semper luctus, ex libero suscipit nisi, id malesuada mi nibh sit amet erat.
>


> [!column| 6 clean no-icon alt-line]+  Locale Information
>>[!npc | clean dim]+ Races
>> ```meta-bind
>> INPUT[listSuggester(optionQuery(#race)):Inhabitants]
>> ```
>
>>[!npc| clean dim]+ NPCs
>> ```meta-bind
>> INPUT[listSuggester(optionQuery(#eoenpc)):npcs]
>> ```
>
>>[!location| clean dim]+ Nearby Locales
>> ```meta-bind
>> INPUT[listSuggester(optionQuery(#eoeloc)):places]
>> ```
>
>>[!scene| clean dim]- Point of Interest
>>
>> - Lorem ipsum dolor
>> - sit amet, consectetur adipiscing elit.
>> - Phasellus dignissim pharetra eros a fringilla.
>
>>[!tldr| clean dim]+ History
>>
>> ```meta-bind
>> INPUT[listSuggester(optionQuery(#eoeevent)):event]
>> ```
>
>>[!recap | clean dim]- Districts
>>
>> - Lorem 
>> - ipsum dolor
>> - sit amet, 
>> - consectetur adipiscing elit.
>> - Phasellus dignissim 
>> - pharetra eros a fringilla.
>

#  Information



>[!column|clean no-icon alt-line] DM Notes 
>>[!todo|bg-c-green clean dim] Side Quests/Job Boards
>>
>> - [ ] 
>> - [ ] 
>> - [ ]  
>> - [ ]  
>
>>[!pf2-note|bg-c-purple clean dim] Story Notables  
>> 
>> - [ ] 
>> - [ ] 
>> - [ ]  
>> - [ ]  
>
>>[!question|bg-c-blue clean dim] Rumors 
>>
>> ```meta-bind
>> INPUT[listSuggester(optionQuery(#eoerumor)):rumors]
>> ```
>
>>[!question|bg-c-orange clean dim] Secrets 
>>
>> - [ ] 
>> - [ ] 
>> - [ ]  
>> - [ ]  
