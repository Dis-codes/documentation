# Developer documentation
Using [Obsidian](https://obsidian.md/) to write docs, using [Quartz](https://quartz.jzhao.xyz/) to transfer it to a website

## View locally
```bash
npm i
quartz build --serve
```

## synchronize
```bash
npx quartz sync
```

## Updating quartz
```bash
npx quartz update
```
## Restoring content from cache, if merge conflict
```bash
npx quartz restore
```
## Authoring Content
- `title` : Title of the page. If it isn’t provided, Quartz will use the name of the file as the title.
- `aliases` : Other names for this note. This is a list of strings.
- `draft` : Whether to publish the page or not. This is one way to make pages private in Quartz.
- `date` : A string representing the day the note was published. Normally uses YYYY-MM-DD format
