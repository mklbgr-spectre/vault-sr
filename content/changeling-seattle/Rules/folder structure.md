# Repair Hints — Quick Reference

Use these tags to leave file-specific instructions for the `/repair-md` agent.
The agent applies the instruction to the content between the tags, then deletes both tag lines.

## Syntax

```
%% REPAIR START: your instruction here %%
...affected content...
%% REPAIR END %%
```

## Copy-paste templates

**Missing bullet markers:**
```
%% REPAIR START: the list below is missing bullet markers on every entry %%

%% REPAIR END %%
```

**Interleaved columns:**
```
%% REPAIR START: this block has two PDF columns interleaved — remove the intrusive fragments %%

%% REPAIR END %%
```

**Broken word wraps:**
```
%% REPAIR START: rejoin the broken mid-word line wraps in this block %%

%% REPAIR END %%
```

**PDF table (columns pasted as a flat list):**

The raw paste looks like this — header row followed by all values jumbled together with line breaks between each cell:
```
Repair Job
 Difficulty # of Successes
Simple mechanical repair
 4
 3
Soldering job
 5
 2
```
Use this hint to reconstruct it as a proper markdown table:
```
%% REPAIR START: this is a PDF table pasted as a flat list — reconstruct it as a markdown table with the correct columns and one row per entry %%

%% REPAIR END %%
```

**Folder table of contents:**

Place this anywhere in a file (typically near the top of an overview/intro file). The agent will list all other `.md` files in the same folder as a wiki-linked bullet list, then delete the tags.
```
%% REPAIR START: replace this block with a markdown bullet list of wiki-links to all other .md files in the same folder as this file, as a table of contents — use the file name without the .md extension as the link text %%

%% REPAIR END %%
```

**Custom instruction:**
```
%% REPAIR START: %%

%% REPAIR END %%
```
