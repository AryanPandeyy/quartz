---
title: 🪴 Quartz 3.3
enableToc: false
---

Host your second brain and [digital garden](https://jzhao.xyz/posts/networked-thought) for free. Quartz features
1. Extremely fast natural-language [[notes/search]]
```dataviewjs
let pages = dv.pages('"notes"')
.where(p => p.file.name != dv.current().file.name)
.sort(p => p.file.ctime)
.forEach(p => {
dv.header(2, p.file.name)
dv.el("div", 
  this.app.metadataCache
  .getCache(p.file.path)
  .headings.slice(1)
  .filter(h => h.level <= 3)
  .map(h => {
    let indent = "   ".repeat(h.level-1);
    let linkyHeading = "[[#" + h.heading + "]]";
    return indent + "- " + linkyHeading;
  }).join("\n"));
})
```
3. Customizable and hackable design based on [Hugo](https://gohugo.io/)
4. Automatically generated backlinks, link previews, and local graph
5. Built-in [[notes/CJK + Latex Support (测试) | CJK + Latex Support]] and [[notes/callouts | Admonition-style callouts]]
6. Support for both Markdown Links and Wikilinks

Check out some of the [amazing gardens that community members](notes/showcase.md) have published with Quartz or read about [why I made Quartz](notes/philosophy.md) to begin with.

## Get Started
> 📚 Step 1: [Setup your own digital garden using Quartz](notes/setup.md)

Returning user? Figure out how to [[notes/updating|update]] your existing Quartz garden.

If you prefer browsing the contents of this site through a list instead of a graph, you see a list of all [setup-related notes](/tags/setup).

### Troubleshooting
- 🚧 [Troubleshooting and FAQ](notes/troubleshooting.md)
- 🐛 [Submit an Issue](https://github.com/jackyzha0/quartz/issues)
- 👀 [Discord Community](https://discord.gg/cRFFHYye7t)

