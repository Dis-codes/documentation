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
### Adding block to toolbox
All toolbox blocks are located inside a `/lib/entries` folder under specific category
### Using Toolbox
Toolbox is defined inside `entries/index.ts` you must import the folder and then define it in the toolbox bellow, select a color, name.

For creating the folder you can look at others, but it´s very basic. it exports an array of blocks like
```js
export default [
    {
        kind: "block",
        type: "categoryName_blockName"
    },
]
```

You can also add a text in there
```js
{
    kind: "label",
    text: "Custom text inside a toolbox!"
},
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