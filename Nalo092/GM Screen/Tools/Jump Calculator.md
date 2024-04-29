---
TotalDist: 20.615528128088304
factor: 1.3119165215094772
PC_select: "[[Callie Alma Teres|Callie Alma Teres]]"
RunningStart: 1
LongJump: 20
HighJump: 5
---
> [!infobox | wmed left]
> # Diagonal Jump Calculator
> | |
> -|-
> `INPUT[suggester(optionQuery(#eoepc)):PC_select]` | **Str:** `$=dv.page(dv.current().PC_select).strength`
> Running start? (10ft) | `INPUT[inlineSelect(option(1, Yes), option(0.5, No)):RunningStart]`
> Long Jump Distance | `INPUT[number(class(nb-mb-45)):LongJump]` ft 
> High Jump Distance | `INPUT[number(class(nb-mb-45)):HighJump]` ft
> DC | `$=10+dv.current().factor*(dv.current().TotalDist-Math.sqrt(Math.pow(dv.current().RunningStart*dv.page(dv.current().PC_select).strength,2) + Math.pow(dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2)),2))) > 10 ? Math.ceil(10+dv.current().factor*(dv.current().TotalDist-Math.sqrt(Math.pow(dv.current().RunningStart*dv.page(dv.current().PC_select).strength,2) + Math.pow(dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2)),2)))) : "No Roll Required"`
^DiagonalJump


> [!infobox | no-t]+ Details
> # Extra details
> | |
> -|-
> Total distance | `VIEW[round({TotalDist},1)]` ft `VIEW[sqrt({LongJump}^2+{HighJump}^2)][math(hidden):TotalDist]`
> Factor | `VIEW[round({factor},2)]` `VIEW[4*atan(max(0, {HighJump})/max(0,{LongJump}))/pi + 1][math(hidden):factor]`
> Max long jump | `$=dv.current().RunningStart*dv.page(dv.current().PC_select).strength` ft
> Max High Jump | `$=dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2))` ft
> Max distance | `$=Math.sqrt(Math.pow(dv.current().RunningStart*dv.page(dv.current().PC_select).strength,2) + Math.pow(dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2)),2))`
> Distance Surplus | `$=dv.current().TotalDist-Math.sqrt(Math.pow(dv.current().RunningStart*dv.page(dv.current().PC_select).strength,2) + Math.pow(dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2)),2))`
> DC factor | `$=10+dv.current().factor*(dv.current().TotalDist-Math.sqrt(Math.pow(dv.current().RunningStart*dv.page(dv.current().PC_select).strength,2) + Math.pow(dv.current().RunningStart*Math.max(0, 3+Math.floor((dv.page(dv.current().PC_select).strength-10)/2)),2)))`