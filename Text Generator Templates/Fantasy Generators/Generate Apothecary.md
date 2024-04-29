---
PromptInfo:
 promptId: GenApothecary
 name: 🎲 Generate Apothecary Shop ☘️
 description: Generate a fantasy magic shop. 
 author: JoshP
 tags: fantasy, ttrpg
 version: 0.0.1
---

{{#if selection}}
Use this Information for flavoring the Prompt:
*Main Focus*
{{title}} ({{type}}:
{{#each sum}}
- {{this}}
{{/each}}
{{selection}}
*Less important things, but maybe helpful in Context*:
{{#each children}}
{{#if frontmatter.sum}}
{{this.basename}}:
{{#each frontmatter.sum}}
- {{this}}
{{/each}}
{{/if}}
{{/each}}
Use the above information JUST FOR CONTEXT. Come up with new Ideas inspired by the things above, but do not just iterate things from above
{{/if}}

## prompt: Store Name
Prompt: Store Name and description of a small fantasy shop that sells Apothecary items such as potions. 

### Prompt: Store Keeper Name 
Prompt: Provide a description of the store owner and any employees here. 

What is the store owner doing when the players walk in?

## Wares
Prompt: Create a table in Markdown here of 10 random general Apothecary items that might be found in a generic fantasy shop. The items should come from the list of items in Dungeons and Dragons 5th Edition. Please include 4 potions in the list that are common or uncommon. The other items should be mainly uncommon or rare with 1 very rare item. Please include columns for: Item Name, Rarity, Type, Cost, a 1 line description and a source acronym. Please format the item name as a link by formatting it like this [[item name]]. 