---
Title: ToDel Sample test
alias:
---

## Sample usage of Tasks
- [ ] task starting with a hyphen 
	* [ ] task starting with an asterisk 
+ [ ] task starting with a plus sign 
1. [ ] a task in a numbered list
      [clock::2025-02-22T22:04:28--2025-02-22T22:04:51]
      [clock::2025-02-22T22:04:55--2025-02-22T22:04:58]
2. [/] * [/] task starting with an asterisk ⛔ j9p1a3 ⏬
	+ [ ] task starting with a plus sign 🆔 j9p1a3
	1. [w] a task in a numbered list ⏬ #aspnet

TODO das machen

```tasks
in progress
```

```tasks
not done
heading includes Sample usage of Tasks
has tags
```

```tasks
heading includes Sample usage of Tasks
status.name includes In Progress
```

## Query

```dataview
Table file.link as "File"
	where contains(Title, "Sample")
```



``` tracker
searchType: tag
searchTarget: DailyNote
folder: Daily-Notes
endDate: 2026-01-31
fixedScale: 1.1
bullet:
    title: "Clean Up"
    dataset: 0
    orientation: horizontal
    range: 10, 20, 40
    rangeColor: darkgray, silver, lightgray
    value: 12.5
    valueUnit: times
    valueColor: '#69b3a2'
    showMarker: true
    markerValue: 30
    markerColor: black
```


