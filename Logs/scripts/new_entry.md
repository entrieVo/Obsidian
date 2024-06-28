<%*
let description = await tp.system.prompt("Entry text");
let count = 0;

const file = tp.file.find_tfile(tp.file.title);
const data = tp.file.content.split('\n');
for (let i = 0; i < data.length; i++) {

	if (data[i].includes('label: "Add entry"')) {
		count = +(data[i + 2].split('"')[1]) + 1;
		console.log(count);
	}
}
_%>
```meta-bind-button
label: "Add entry"
style: default
id: "<%* tR += count %>"
actions:
  - type: replaceSelf
    replacement: scripts/new_entry.md
    templater: true
```
- `[<%* tR += count %>]` <%* tR += description %>