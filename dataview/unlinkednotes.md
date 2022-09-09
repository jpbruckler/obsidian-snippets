
# Unlinked notes

The snippet below will show all notes that are not linked from any other note. This can be useful to find notes that are not linked from any other note and thus might be candidates for deletion.

```dataview
list 
where !file.outlinks
limit 40
sort file.cday desc
```

I'd like to develop this into something that would populate a count in a callout. Would need to use dataviewjs for that.