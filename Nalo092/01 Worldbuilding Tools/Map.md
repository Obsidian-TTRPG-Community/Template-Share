%% 
    Credit: https://watabou.github.io/
    for the generator

    Note, this will not work without the following plugins:
    -   dataview: https://github.com/blacksmithgu/obsidian-dataview
    -   open gate:https://github.com/nguyenvanduocit/obsidian-open-gate
    -   metabind: https://github.com/mProjectsCode/obsidian-meta-bind-plugin
    the intended use for this is as follows:
    ```meta-bind-embed
    [[Map]]
    ```
    insert this code block into your note, and tada, one working generator.
%%

> [!metadata | clean]- Config
>> ``` dataviewjs
>> const c = dv.current()
>> const mapdata = c.mapdata
>> function stringToSeed(str) {
>>     let hash = 0;
>>     for (let i = 0; i < str.length; i++) {
>>         const char = str.charCodeAt(i);
>>         hash = (hash << 5) - hash + char;
>>         hash = hash & hash; // Convert to 32bit integer
>>     }
>>     return hash;
>> }
>> const config = {
>> 	"size": mapdata?.size ?? 35,
>> 	"seed": mapdata?.seed ?? stringToSeed(c.file.name),
>> 	"greens": mapdata?.greens ?? 1,
>> 	"citadel": mapdata?.citadel ?? 1,
>> 	"urban_castle": mapdata?.urban_castle ?? 1,
>> 	"plaza": mapdata?.plaza ?? 1,
>> 	"temple": mapdata?.temple?? 1,
>> 	"walls": mapdata?.walls ?? 1,
>> 	"shantytown": mapdata?.shantytown ?? 0,
>> 	"coast": mapdata?.coast ?? 0,
>> 	"river": mapdata?.river ?? 1,
>> 	"gates": mapdata?.gates ?? -1,
>> 	"sea": mapdata?.sea ?? 0
>> };
>> 
>> dv.table(["K", "V"], dv.array(Object.entries(config)).map(([k, v]) => [
>> 	k, `\`INPUT[number(defaultValue(${v})):mapdata.${k}]\``
>> ]))
>> 
>> ```


```dataviewjs

const c = dv.current()
const mapdata = c.mapdata


function stringToSeed(str) {
    let hash = 0;
    for (let i = 0; i < str.length; i++) {
        const char = str.charCodeAt(i);
        hash = (hash << 5) - hash + char;
        hash = hash & hash; // Convert to 32bit integer
    }
    return hash;
}

const config = {
	"name": c.file.name,
	"size": mapdata?.size ?? 35,
	"seed": mapdata?.seed ?? stringToSeed(c.file.name),
	"greens": mapdata?.greens ?? 1,
	"citadel": mapdata?.citadel ?? 1,
	"urban_castle": mapdata?.urban_castle ?? 1,
	"plaza": mapdata?.plaza ?? 1,
	"temple": mapdata?.temple?? 1,
	"walls": mapdata?.walls ?? 1,
	"shantytown": mapdata?.shantytown ?? 0,
	"coast": mapdata?.coast ?? 0,
	"river": mapdata?.river ?? 1,
	"gates": mapdata?.gates ?? -1,
	"sea": mapdata?.sea ?? 0
};

const base_url = `https://watabou.github.io/city-generator/?`;

function buildFullUrl(config, base_url) {
	return base_url + Object.entries(config).map(([key, value]) => {
		return `${encodeURIComponent(key)}=${encodeURIComponent(value)}`;
	}).join('&');
}

if (c.file.name != "Map") {
dv.span(
`\`\`\`gate
url: ${buildFullUrl(config, base_url)}
height: "600px"
\`\`\``
);
}
```
