---
title: Contributing info
---
Thank you for wanting to help us! Here is some info before you get started.

Discodes is separeted into 3 parts

# Main page
---
If you want to update our page you can see repository [here](https://github.com/Dis-codes/discodes)
Resources that we use can be found in [[Helpers]] 
# Workspace
---
If you want to make blocks. You can find the repository [here](https://github.com/Dis-codes/workspace)
## Getting started
All you need is a code editor, then you can download your code, easiest way is to use GitHub desktop. In terminal write `cd app` to get inside of app folder run `npm install` to install all dependencies, then `npm run dev` to view it locally at http://localhost:5173/

## Creating a block
All blocks are located inside a `/lib/blocks/js` folder under specific category
Examples of using blocks can be found in [[Blocks]]
We are using the latest discord.js version `14.14`
## Toolbox
From now on toolbox is automatically generated. So you can only add the block definitions.

To change a color name or make it hidden you can add these properties in category definition
```ts
export default class {
    getRegistry() {
        return {
            id: "joins",
            name: "User Joins",//name of the categorz
            color: "#60cc6c", //color
            hidden: true, //hidden
            blocks: []
        };
    }
}
```
### Extended
extended is used to add default blocks or labels

#### Category
To change a category name or colors you can use extended
```json
"discord.js": {
          name: "Discord.JS",
          colour: "#5b80a5",
          expanded: false
}
```

Or you can add labels

```json
category: [{
    kind: "label",
    text: "Custom text inside a toolbox!"
}]
```
#### Group of blocks
And making a group of blocks when defining the block, using the same inputs.
You can define the blocks with either "shadow" or "block" shadow will act like a placeholder that can be overwritten by another block. while block can be removed entirely.
```js
{
    kind: "block",
    type: "text_forEach",
    inputs: {
        TEXT: {
            shadow: {         //This can be either shadow or block
                type: "text", //added a text with "Hello World!"
                fields: {
                    TEXT: "Hello World!"
                 }
            }
        }
    }
},
```
# Documentation
---
To help write the documentation, you need to understand what blocks does, you should specify the input, example and output. ideally what a code will output. Everything should be understandable for youngest users.
You can find the repository [here](https://github.com/Dis-codes/documentation)

## Getting started
To start you need to have code editor and obsidian. Once you have it downloaded you use in terminal `npm i` then `npx quartz build --serve` and you should be able to view it locally at http://localhost:8080/

## Using Markdown
Here you can find a detailed tutorial for using markdown in obsidian [[markdown]]
## Authoring Content
adds properties at the top of the page.
- `title` : Title of the page. If it isn’t provided, Quartz will use the name of the file as the title.
- `aliases` : Other names for this note. This is a list of strings.
- `draft` : Whether to publish the page or not. This is one way to make pages private in Quartz.
- `date` : A string representing the day the note was published. Normally uses YYYY-MM-DD format

Then you open your obsidian app and open the **content** folder, and you can start with updating the docs. Once you are done you simply make a pull request and wait for someone to review your changes.