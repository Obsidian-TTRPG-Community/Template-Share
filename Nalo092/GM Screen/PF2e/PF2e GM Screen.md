---
sessions: 
tags:
  - gmscreen
---

![[GMScreen.png]]

>[!tldr | bg-c-gray  ttl-c]- DM Tools
>
>>[!cards| dataview]
>> ```dataview 
>> TABLE 
>> FROM #dmtool OR #eoetool
>> ```

>[!npc | bg-c-purple ttl-c]- Party Reference Info
>>[!column | no-i no-t]
>>>[!info | clean]-  Known Languages
>>>```dataview 
>>>TABLE WITHOUT ID languages AS "Language", rows.file.name AS "Spoken By" 
>>>FROM #eoepc 
>>>WHERE status != "dead" AND status != "left" AND !contains(file.name, "Session")
>>>FLATTEN languages 
>>>GROUP BY languages
>>>```
>>
>>>[!info | clean ]- Player Overview
>>> ```dataview
>>>TABLE WITHOUT ID  aliases as Name, ac as AC, classDC as DC, passPer as "Passive Perception", level as Level
>>>FROM #eoepc
>>>WHERE status != "dead" AND status != "left" AND !contains(file.name, "Session")
>>>


>[! | bg-c-orange  ttl-c]- Campaign Maps
>
>>[!cards| dataview] 
>> ```dataview 
TABLE WITHOUT ID link(file.link, file.aliases[0])
FROM #eoemaps 
SORT file.link ASC

>[! important |color-yellow ttl-c n-th]- Conditions
>```dataview
>TABLE WITHOUT ID file.link AS Type, effect
>FROM #pf2econdition
>SORT file.link ASC
>```

> [!example |  ttl-c ]- Rules Reference
>>[!cards| dataview]
>>```dataview
>>TABLE 
>>FROM #pf2er-ref

>[!danger | bg-c-green  ttl-c]- Action References
>>[!cards| dataview]
>> ```dataview 
>> TABLE WITHOUT ID link(file.link, file.aliases[0]) as Name
>> FROM #pf2eaction
>> SORT file.link ASC


>[! health |  bg-c-red ttl-c n-th]- Healing
>
>```dataview
>TABLE WITHOUT ID file.link AS Type, effect, cost
>FROM #pf2eheal
>```



>[!creature |  ttl-c ]- Quick Creature Stats
>> [!example | clean no-t]
>> ![[Quick Creature Stats]]



>[!creature | background-color-red ttl-c ]- Creature Adjustments
>>[! column | no-i no-t 2 ]
>>>[!info |  bg-c-yellow  ] Elite Adjustments
>>>
>>>*   +2 to AC, attack bonus, DCs, saves, Perception, skills.
>>>*    +2 to damage for Strikes and offensive abilities, or +4 to abilities that can be used a limited number of times.
>>>
| **Starting Level** | **HP Increase** |
| --- | --- |
| 1 or lower | 10 |
| 2-4 | 15 |
| 5-19 | 20 |
| 20+ | 30 |
>>
>>>[!info |  bg-c-green  ] Weak Adjustment
>>>*   \-2 to AC, attack bonus, DCs, saves, Perception, skills.
>>>*    \-2 to damage for Strikes and offensive abilities, or +4 to abilities that can be used a limited number of times.
>>>
| **Starting Level** | **HP Decrease** |
| ------------------ | --------------- |
| 1-2                | 10              |
| 3-5                | 15              |
| 6-20               | 20              |
| 21+                | 30              |
|                    |                 |

> [!location| bg-c-b ttl-c]- Exploration and Downtime Activities
>>[!cards| dataview]
>> ```dataview 
TABLE
FROM #Exploration OR #Downtime

