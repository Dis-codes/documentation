# Creating a new Category
Create a new folder inside `blocks/js`
```ts
import { OutputType, BlockShape, InputShape } from '$lib/utils/blockRegistryTool';
class XXXBlocks {
	getRegistry () {
		return {
		id: "Name",
		color: 60,
		blocks: [
			]
		};
	}
	//place for functions
}
  
export default XXXBlocks;
```

# Creating a new block
Inside the blocks array you will be defining the blocks.
```ts
{
	func: "teststatement",
	text: "statement block",
	shape: BlockShape.STATEMENT
},
```
Every block  needs a function to work
```ts
teststatement () {
	return 'void;';
}
```

### Defining the block
- `func` : function name of the block
- `text` : Text that is shown on the block, using brackets you can make`[ARGUMENTS]`, `/n` will makes a new line and if you use branches it will be on another branch.
- `shape` : For blocks that won´t return anything, but make functions
1. STATEMENT - Not actually required, but keeps code consistent.
2. EVENT - floating block with an input inside.Can be replaced with FLOATING, but keeps code consistent.
3. TERMINAL - block with no blocks allowed to attach after.
4. FLOATING - block that cannot have any parent blocks
5. TOPPER - cannot have any blocks attached before it
6. CUSTOM -  can be used if "manual" is used for the block.

- `output` : Blocks that return values. 
8. STRING - returns text
9. NUMBER - returns number
10. BOOLEAN - returns true/false
11. ARRY - returns a list / array
12. OBJECT - returns a JSON object.
13. ANY - can be put inside any block.
14. DISCORD - contains multiple values of discord objects
	1. SERVER
	2. CHANNEL
	3. MESSAGE
	4. MEMBER

- `branches` : allows you create multiple branches (even is 1 branch)
-  `inline` : true/false if the block should be inline or not default - false
- `arguments` : if you used any arguments you have to define them here. Mostly you will use type of value with check
	- `type` : defines which block can be put here. 
		1. VALUE - allows other blocks
		2. DUMMY - Can be used for seperating content on a block by a new line.
		3. SPACE - Similar to DUMMY.Can be used for seperating content on a block.
		4. IMAGE
		5. ANGLE - Angle field for directional inputs.
		6. CHECKBOX - Checkbox field usually for toggles.
		7. COLOR - Color field.
		8. MENU - Dropdown menu field with options.
		9. SERIALIZABLE_LABEL - Label that serializes to the project.
		10. NUMBER - Number field. Used for restricting to certain numbers.
		11. TEXT - Text field. Used if blocks shouldnt be used here,but text can still be input here.
		12. MULTILINE_TEXT - Multi-line text field.Similar to TEXT, but new line characters are allowed.
		13. VARIABLE - Variable field. Similar to MENU, but the options are all variables.
		14. DISCORD
			1. SERVER
			2. CHANNEL
			3. MESSAGE
	- `check` : check is used to check if the block that user puts has the same values. Same as **shape**
	- `options` : used for menu. as array of inputs where first value is shown and second is returned in the code. 

```ts
options: [
	['shown', 'codeshown'],
	['shown2', 'codeshown2']
]
```

## Advanced block
This block changes a variable to another value.
```ts
{
	func: "change_variable",
	text: "change [NAME] [CHANGE] [VALUE]",
	shape: BlockShape.STATEMENT,
	inline: true,
	arguments: {
		CHANGE: {
			type: InputShape.MENU,
			options: [
				['add', 'add'],
				['subtract', 'subtract'],
				['multiply by', 'multiply'],
				['divide by', 'divide'],
				['set to', 'set']
			]
		},
		NAME: {
			type: InputShape.VALUE,
			check: OutputType.STRING
		},
		VALUE: {
		type: InputShape.VALUE,
	},
}
...
change_variable(args: any) {
let newName = args.NAME.replace(/'/g, "");
switch (args.CHANGE) {
	case 'add':
		return `${newName} += ${args.VALUE}\n`;
	case 'subtract':
		return `${newName} -= ${args.VALUE}\n`;
	case 'multiply':
		return `${newName} *= ${args.VALUE}\n`;
	case 'divide':
		return `${newName} /= ${args.VALUE}\n`;
	case 'set':
		return `${newName} = ${args.VALUE}\n`;
	default:
		return '';
        }
    }
```