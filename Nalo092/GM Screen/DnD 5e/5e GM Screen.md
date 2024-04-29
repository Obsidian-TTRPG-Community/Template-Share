---
tags:
  - gmscreen
---

![[5eGMScreen.png]]

>[!tldr | bg-c-gray  ttl-c]- DM Tools
>
>>[!cards| dataview]
>> ```dataview 
TABLE
FROM #dmtool
SORT file.link ASC

>[! | bg-c-orange  ttl-c]- Campaign Maps
>
>>[!cards| dataview] 
>> ```dataview 
TABLE
FROM #campaginmaps
SORT file.link ASC


>[! important  |color-yellow ttl-c n-th]- Conditions
>```dataview
>TABLE WITHOUT ID file.link AS Type, effect
>FROM #5econdition
>SORT file.link ASC
>```


> [!example |  ttl-c ]- Rules Reference
>>[!cards| dataview]
>>```dataview
>>TABLE 
>>FROM #5er-ref
>>SORT file.link ASC

>[!danger | bg-c-green  ttl-c]- Action References
>>[!cards| dataview]
>> ```dataview 
TABLE
FROM #5eAction
SORT file.link ASC

>[! health |  bg-c-red ttl-c n-th]- Healing
>```dataview
>TABLE WITHOUT ID file.link AS Type, effect, cost
>FROM #5ehealing
>SORT file.link ASC
>```

> [!example|  ttl-c]- Exploration and Downtime Activities
>>[!cards| dataview]
>> ```dataview 
>> TABLE
>> FROM #5edowntime or #5e-exploration
>> SORT file.link ASC