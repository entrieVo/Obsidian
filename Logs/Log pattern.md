---
value: 0
---
# Log with counter
```meta-bind-button
label: "Add entry"
style: default
id: "4"
actions:
  - type: replaceSelf
    replacement: scripts/new_entry.md
    templater: true
```
- `[3]` Make sure there is no other button in the file that defines "id" by number.
- `[2]` You can specify the number from which the entry will start in the "id" field.
- `[1]` When deleting an entry, the id will remain the same.

# Log calculating the difference
Change the position of the progress bar, and then click `Add difference entry`. The difference between the old and new value will be recorded in square brackets.
The calculation will be performed according to the value recorded after the last entry.

```meta-bind
INPUT[progressBar(minValue(-10), maxValue(10)):value]
```
___
```meta-bind-button
label: "Add difference entry"
style: default
id: "0"
actions:
  - type: replaceSelf
    replacement: scripts/new_difference_entry.md
    templater: true
```
- `[-4]` Calculates the difference between the new value (frontmatter: value) and the old value ("id").
- `[0]` If button or frontmatter field have different label, check the script to change it.
