
source:: discord
user:: deezy
discordId:: 163075234155593730
date: 2022-08-09

```dataviewjs
let d = {};
function process(k, v) {
  Object.keys(v).forEach(x => {
    if(!input.ignoredNonExisting.includes(x.toLowerCase())) {
        x = dv.fileLink(x);
        if (d[x]==undefined) { d[x] = []; }
        if(!input.ignoredExisting.includes(k)) {
            d[x].push(dv.fileLink(k));
        }
    }
  });
}

Object.entries(dv.app.metadataCache.unresolvedLinks)
    .filter(([k,v])=>Object.keys(v).length)
    .forEach(([k,v]) => process(k, v));

dv.table(["Non existing notes", "Linked from"],
         Object.entries(d)
         .filter(([k, v]) => v.length >= input.count)
         .sort((a, b) => b[1].length - a[1].length)
         .map(([k,v])=> [k, v.join(" • ")]))
```