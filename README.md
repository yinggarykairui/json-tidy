# json-tidy

Paste JSON, get a collapsible tree, and copy the JSONPath of any node with one click — one HTML file, nothing leaves the tab.

![Screenshot of json-tidy: a paste box holding a sample API response, and below it a collapsible tree expanded two levels, with the copy button on one row reading "copied".](screenshot.png)

**[Live demo](https://yinggarykairui.github.io/json-tidy/)**

## What it does

Paste or type JSON into the box and a tree appears below it. The root opens one level; everything below it starts collapsed. A chevron opens each container, and large containers open 200 children at a time so a multi-megabyte document does not freeze the page. Every row has a copy button that puts that node's JSONPath on the clipboard, using dot notation for plain keys and quoted brackets for anything else, so `$.items[0]['user name']` comes out correct rather than merely plausible. Bad input gets one plain-language line under the box with the line and column when the parser reports one, and the page keeps working. The screenshot shows the sample document expanded two levels, with the copy button on the `user name` row reading `copied` just after it handed over `$.items[0]['user name']`.

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
