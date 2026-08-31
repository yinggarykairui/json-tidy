# json-tidy

Paste JSON, get a collapsible tree, and copy the JSONPath of any node with one click — one HTML file, nothing leaves the tab.

![Screenshot of json-tidy: a paste box holding a sample API response, and below it a collapsible tree expanded two levels, with the copy button on one row reading "copied".](screenshot.png)

**[Live demo](https://yinggarykairui.github.io/json-tidy/)**

## What it does

Paste or type JSON into the box and a collapsible tree appears below it, up to two million characters; past that it waits for the Tidy button. The root opens one level, and below that a chevron — or the row's own label — opens each container that has children, 200 at a time, while every row carries a copy button for that node's JSONPath: a dot for plain keys, quoted brackets for anything else, so `$.items[0]['user name']` comes out correct. Editing does not throw your place away — a change that cannot alter the tree leaves the tree alone, and a real edit, or a document that is briefly invalid while you fix it, rebuilds the tree and puts every node back the way you left it, open or closed, with the batches you had opened under each one and roughly where you were scrolled. Tidy says when nothing changed and reports how many of the nodes you opened survived a rebuild; Load sample and Clear always start over from scratch. Bad input gets a plain-language line under the box with the parser's own message under that, and numbers go through `JSON.parse`, so a large integer id can change on the way in: `9007199254740993` shows as `9007199254740992`.

## How to run

```
git clone https://github.com/yinggarykairui/json-tidy.git
cd json-tidy
open index.html
```

On Linux use `xdg-open index.html`; on Windows use `start index.html`. Or just double-click `index.html`. There is no server, no build step, and no dependency — the whole thing is one file, and it works offline. The live demo is the same file.

## Why it exists

Reading a minified API response in a text editor is miserable, and hand-typing a JSONPath from a tree view is where the typos come from. Seeded as day 018's idea: paste, expand, click, paste the path somewhere useful.

---

*Day 018 of an autonomous build factory — [factory-hub](https://github.com/yinggarykairui/factory-hub)*
