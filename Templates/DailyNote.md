# <% tp.file.title %>

<< [[<% tp.date.now("YYYY-MM-DD", -1) %>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>]] >>

## Tasks
<%* if (tp.file.title.startsWith("2021")) {%>
This is a hello file !
<%* } %>

<%* if (tp.frontmatter.type === "seedling") { %>
This is a seedling file !
<%* } else { %>
This is a normal file !
<%* } %>

%%Es muss rein:
- Daily nur mit Datum ohne daily note hinten
- Header muss dann gesetzt sein und dann alt-e :-)
- Wenn in "type" ist das oder das dann due anzeigen
- Wenn in tags contains xxx dann daas oder das  
- d.h. das unten einbauen das wir nur projekt einbauen wenn type x oder tag ?

see [Templater Example](https://silentvoid13.github.io/Templater/docs/commands/execution-command)
and
[Task Example Queries](https://schemar.github.io/obsidian-tasks/queries/examples/)
and
[Dataview Queries](https://blacksmithgu.github.io/obsidian-dataview/query/queries/)
%%

#### Over Due

```tasks
not done
due before <% tp.date.now("YYYY-MM-DD") %>
path does not include Templates
path does not include Daily-Notes
```

#### Due Today

```tasks
not done
due on <% tp.date.now("YYYY-MM-DD") %>
path does not include Templates
path does not include Daily-Notes
```

### Due in the next two weeks
```tasks
not done
due after <% tp.date.now("YYYY-MM-DD") %>
due before <% tp.date.now("YYYY-MM-DD",14) %>
path does not include Templates
path does not include Daily-Notes
```

#### New Today
- [ ] Some Task

## Meeting Log

### 0000:

## Daily Log

### [[Project 1]]


### [[Project 2]]


### [[Project 3]]

## Daily Check List

### Start of Day

- [ ] Check Email
- [ ] Check Teams
- [ ] Check showing online
- [ ] Check Calendar - Time Block

### End of Day

- [ ] Show Offline
- [ ] Clean Unused Headings in Daily Log
- [ ] Check tomorrow's calendar

## Other Tasks

#### No Due Date

```tasks
not done
no due date
path does not include Templates
path does not include Daily-Notes
```

#### Done Today

```tasks
done on <% tp.date.now("YYYY-MM-DD") %>
path does not include Templates
```