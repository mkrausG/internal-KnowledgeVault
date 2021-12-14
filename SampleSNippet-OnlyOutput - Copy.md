---
title: <% tp.file.title %>
date: <% tp.file.creation_date("YYYY-MM-dd HH:mm") %>
modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
author: mkraus
id: 
tag: 
Mood today: <% tp.system.suggester(["Happy", "Sad", "Confused"], ["Happy", "Sad", "Confused"]) %>
note type: seedling
---

# <% tp.file.title %>

I have the mood: <% tp.frontmatter["Mood today"] %>
The id is <% tp.frontmatter["id"] %>
Note's type: <% tp.frontmatter["note type"] %>
