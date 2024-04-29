---
tags:
  - dmtool
---

# Active Rumors
 ```dataview
 TABLE join(aliases, ", ") AS Aliases, quicknote as Rumors, session as Session, campaign as Campagin
 FROM #eoerumor 
WHERE active = true

```

# Inactive Rumors
 ```dataview
 TABLE join(aliases, ", ") AS Aliases, quicknote as Rumors, session as Session, campaign as Campagin
 FROM #eoerumor 
WHERE active = false
```