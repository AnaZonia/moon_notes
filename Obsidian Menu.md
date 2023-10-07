## Excalidraw
- exporting a region of the drawing as a group will allow updates to go smoothly on the note it's inserted in!

## Tasks

due before in one week
group by filename (if in different files)
hide backlink or short mode

## Calendar
[Calendar Cheatsheet](https://github.com/liamcain/obsidian-calendar-plugin/blob/master/README.md)

## Templater
[Introduction - Templater (silentvoid13.github.io)](https://silentvoid13.github.io/Templater/)

## Callouts

[Callouts Cheatsheet](https://help.obsidian.md/Editing+and+formatting/Callouts)

> [!abstract]

> [!note]

>[!info]

> [!todo]

> [!tip]

> [!success]

> [!question]

> [!warning]

> [!failure]

> [!danger]

> [!bug]

> [!example]

> [!quote]

## Dataview

[Dataview Cheatsheet](https://github.com/seburbandev/obsidian-dataview-cheatsheet)
[Dataview Query Builder](https://s-blu.github.io/basic-dataview-query-builder/)

## Checkbox

![[Obsidian Menu.png]]![[Obsidian Menu-1.png]]

## Zotero tag import snippet
{% if tags.length > 0 -%}{% for t in tags -%}#{% if t.tag == "secondary" %}source/secondary{% if not loop.last %}{% endif %}{% elif t.tag == "primary" %}source/primary{% if not loop.last %}{% endif %}{% elif "-project" in t.tag %}project/{{t.tag | lower | replace(" ", "-") | replace("-project", "")}}{% else %}subject/{{t.tag | lower | replace(" ", "-")}}{% endif %}{% if not loop.last %} {% endif %}{%- endfor %}{%- endif %}
## Transform tags into links
cd to your vault folder and execute the following command:

`sed -i 's/#MYTAG/\[\[MYTAG\]\]/g' *.md`

Replace `MYTAG` with the name of the tag you want to convert to a link.

The above command will replace all occurrences of `#MYTAG` with `[[MYTAG]]` in all of your markdown files in the current directory.