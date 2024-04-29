---
date: 
sessionNumber: 
involvedPC: 
involvedNPC: 
involvedLocation: 
tags: 
summary: ""
cssclasses:
  - wide-page
---


>[!note | right color-red]- Campaign Sessions
>``` dataview
> LIST
> FROM #eoesession 
> sort date descending
>```


> [!tldr| bg-c-white alt-line clean dim]- Previous Session
>> [! recap | bg-c-orange alt-line clean dim] 
>> ```dataview
>> LIST WITHOUT ID
>> summary
>> from #eoesession 
>> where date(date) < date(this.date)
>> sort date descending
>> limit 1
>> ```

> [!interest | clean dim alt-line]- Active Thread(s)
>> [!column | 3 clean no-icon no-title alt-line]
>>> [!Rumor | bg-c-gray clean]- 
>>> - [ ] 
>>
>>> [!Story | bg-c-gray clean]- 
>>> - [ ] 
>>
>>> [!NPC | bg-c-gray clean]- Party
>>> - [ ] 

### Overview
>[!cards| dataview 2]
>
> ```dataview 
>TABLE 
>FROM #gmscreen 
>```


> [!infobox]
> ###### 
>  |
> ---|---|
> **Session Date** | `INPUT[datePicker:date]` |
> **Involved NPC(s)** | `INPUT[inlineListSuggester(optionQuery(#eoenpc), useLinks(partial)):involvedNPC]` |
> **Involved Location(s)** | `INPUT[inlineListSuggester(optionQuery(#eoeloc)):involvedLocation]` |


>[!|no-i clean]+ Current Party
>>[!cards| dataview 2]
>>
>> ```dataview 
TABLE 
FROM #eoepc
WHERE status != "dead" AND status != "left"

>[!|no-i clean]- Previous Party Members
>>[!cards|dataview 2]
>>
>> ```dataview 
>>TABLE 
>>FROM #eoepc
>>WHERE status = "dead" OR  status = "left"

### Pre-`=this.file.name`

> [!column | 3 clean no-icon no-title alt-line]
>> [!scene | bg-c-gray clean]- 
>> - [ ] 
>
>> [!scene | bg-c-gray clean]- 
>> - [ ] 
>
>> [!scene | bg-c-gray clean]- 
>> - [ ] 

> [!rumor | bg-c-purple clean alt-line] Secrets and Clues
> - 

> [!column | 3 clean no-icon no-title alt-line]
>> [!location | bg-c-green clean]- Locations
>> - 
>
>> [!npc | bg-c-blue clean]- NPCs
>> - 
>
>> [!encounter | bg-c-red clean]- Encounter(s)
>> - 

> [!reward | bg-c-yellow clean alt-line]- Rewards
> - [ ] 

### Notes

> [!calendar | clean dim alt-line]-
> ```calendarium
> calendar: Calus Solaris
> ```


> [!summary| clean dim alt-line]-  <font color=Orange>**Scratch Pad: **</font>
> ```meta-bind
> INPUT[editor]
> ```

### Post Session-Notes

> [!column | 4 clean no-icon alt-line]+ New
>> [!quest | clean dim alt-line] New Quest(s)
>> -  
>> - 
>
>> [!location | clean] New Location(s)
>> - 
>> - 
>
>> [!npc | clean] New NPC(s)
>> - 
>> - 
>
>> [!item | clean] New Item(s)
>> - 
>> - 

> [!tldr | bg-c-white alt-line clean dim]+ Summary
>  Prompt: Make a session summary using the info below
> ```meta-bind
> INPUT[editor(title(Session Notes)):summary]
> ```

> [!column | clean no-icon no-title alt-line]
>> [!info  | clean dim] Ideas
>> - 
>
>> [!todo | clean dim] To-Do
>> **Session Specific**
>> - [ ]  
>>
>> **Worldbuilding**
>> - [ ]  
>>
>> **Admin**
>> - [ ]  s


### AI Summary

Prompt: Make a session recap summary for Obsidian markdowns:

# Credits
Based Of @Nell and @BipolarTopographer templates, and personal template