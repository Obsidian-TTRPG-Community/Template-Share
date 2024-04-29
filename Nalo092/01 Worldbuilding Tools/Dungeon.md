---
mapdata:
  tags:
    - large
---
%% 
    Credit: https://watabou.github.io/
    for the generator

    Note, this will not work without the following plugins:
    -   dataview: https://github.com/blacksmithgu/obsidian-dataview
    -   open gate:https://github.com/nguyenvanduocit/obsidian-open-gate
    -   metabind: https://github.com/mProjectsCode/obsidian-meta-bind-plugin
    the intended use for this is as follows:
    ```meta-bind-embed
    [[Dungeon]]
    ```
    insert this code block into your note, and tada, one working generator.
%%

```meta-bind
INPUT[inlineListSuggester(
option(chaotic), option(dangerous), option(multi-level), option(no backdoor), option(secret), option(treasure), option(winding), option(backdoor), option(colonnades), option(compact), option(crammed), option(crumbling), option(deep), option(dry), option(dwelling), option(flat), option(flooded), option(large), option(medium), option(no secrets), option(ordered), option(round), option(single-level), option(small), option(spacious), option(square), option(string), option(temple), option(tomb), option(wet)
):mapdata.tags]
```


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
	"tags": mapdata?.tags ?? [],
	"seed": mapdata?.seed ?? stringToSeed(c.file.name)
};

const base_url = `https://watabou.github.io/one-page-dungeon/?`;


function buildFullUrl(config, base_url) {
    return base_url + Object.entries(config).filter(([key, value]) => {
        if (Array.isArray(value)) {
            return value.length > 0;
        }
        return value;
    }).map(([key, value]) => {
        if (Array.isArray(value)) {
            //return `${encodeURIComponent(key)}=${value.map(v => encodeURIComponent(v)).join(',')}`;
            return `${encodeURIComponent(key)}=${value.map(v => encodeURIComponent(v)).join(',')}`;
        }
        return `${encodeURIComponent(key)}=${encodeURIComponent(value)}`;
    }).join('&');
}
if (c.file.name != "Dungeon") {
dv.span(
`\`\`\`gate
url: ${buildFullUrl(config, base_url)}
height: "600px"
\`\`\``
);
}
```