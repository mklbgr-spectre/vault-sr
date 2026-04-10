Use the Agent tool with subagent_type "general-purpose" and model "haiku" to clean up formatting artifacts in this Obsidian markdown file: $ARGUMENTS

Give the Haiku agent exactly this prompt (fill in the actual file path for $ARGUMENTS):

---
You are cleaning up a markdown file that was created by manually copy-pasting text from a PDF rulebook. The file is: $ARGUMENTS

Read the file, fix all formatting issues listed below, then write the cleaned content back to the same path. Do NOT rewrite, summarize, paraphrase, or add anything — only fix formatting artifacts.

**Fixes to apply:**

1. **Broken mid-word line wraps** — PDF copy-paste sometimes splits words with a space (e.g., "Kith ain" → "Kithain", "S ides" → "Sides", "change ling" → "changeling"). Rejoin them.

2. **Stray page numbers and headers** — Lines that are just a number, or "Changeling: The Dreaming" / "Contents" appearing mid-text, are PDF page headers/footers. Remove them.

3. **Two-column interleaving** — PDF columns sometimes bleed into each other. A sentence that suddenly makes no sense, followed by a short fragment that seems to belong somewhere else, is a column bleed. Remove the intrusive fragment; do not try to relocate it.

4. **Bullet points** — The PDF uses `¶¶` as a bullet marker. Convert every `¶¶` to a proper markdown bullet `-`. Some list entries may be missing the `¶¶` entirely due to copy-paste line splits — use context (surrounding list items, consistent paragraph style) to identify and add `-` to those as well.

5. **Unformatted section headings** — Lines that are a short title standing alone (not part of a sentence, not already prefixed with #) are section headings from the PDF that lost their formatting. Format them as ## headings. If a heading sits inside a section that already has a ## heading, use ###.

6. **Heading spacing** — Ensure one blank line before each heading and one blank line after.

7. **Code blocks are intentional asides** — Any content already in a fenced code block (``` ```) represents a PDF sidebar/callout box. Convert it to an Obsidian callout using this format:
   ```
   > [!example]
   > Content line one
   > Content line two
   ```
   Every line of the former code block content must be prefixed with `> `. Also apply fixes 1–3 to the text inside.

8. **Obsidian wiki-links** — Where the text mentions proper nouns that correspond to other notes in this vault (kith names like Boggans, Pooka, Sluagh; court names like Seelie, Unseelie; system terms like Glamour, Banality, Cantrips, Arts, Realms, Wyrd, Dreaming, Chimera, Chrysalis, Mists; place names like Arcadia, Concordia, Tara Nar — never hyphenated as "Tara-Nar"; events like the Shattering, Sundering, Interregnum, Resurgence, Accordance War, Evanescence; the Changeling Way; Kithain, Trods, Freeholds, Glades, Balefires, Parliament of Dreams, Caliburn, Treaty of Concord, Fomorians, Elder Dark; Noble Houses: Aesin, Ailil, Balor, Beaumayn, Danaan, Daireann, Dougal, Eiluned, Fiona, Gwydion, Leanhaun, Liam, Scathach, Varich), wrap every occurrence as [[Name]].

Write the result back to the same file path. Report how many fixes of each type you made.
---
