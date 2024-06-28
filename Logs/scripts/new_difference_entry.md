<%*
let description = await tp.system.prompt("Entry text");
let score = 0;
let old_score = 0;

const file = tp.file.find_tfile(tp.file.title);
const data = tp.file.content.split('\n');
for (let i = 0; i < data.length; i++) {
	// change "value" to set another field
	if (data[i].includes('value:')) {
		score = +data[i].split(':')[1];
	}

	// change "Add entry" if button has different label
	// also replace the label in the button itself below
	if (data[i].includes('label: "Add difference entry"')) {
		old_score = data[i + 2].split('"')[1];
		console.log('old_score: ', old_score);
	}
}
_%>
```meta-bind-button
label: "Add difference entry"
style: default
id: "<%* tR += score %>"
actions:
  - type: replaceSelf
    replacement: scripts/new_difference_entry.md
    templater: true
```
- `[<%* tR += (score - old_score > 0) ? '+' : '' %><%* tR += score - old_score %>]` <%* tR += description %>