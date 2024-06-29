# Visualization patterns
Created to edit the properties of a file in read mode. Information from the frontmatter is displayed in the chart.

## Radar chart with UI control
The colors of the chart represent the specific group to which a particular characteristic belongs. The sum of the values of all characteristics is shown above the chart.
The number of groups and characteristics is optional.

![](https://i.imgur.com/VhEe1nk.png)

Callout introduces the ability to edit features using sliders. The method of data input can be changed.
At the bottom there is a button to clear all characteristics.

❗ When changing characteristics don't forget to change clear.md (it also contains a characteristics array).
❗ Sometimes clearing works incorrectly, then you should change another value and wait for JS update (time is set in Dataview settings).

![](https://i.imgur.com/4PoVc2w.png)

# Required plugins
- [Meta Bind](https://github.com/mProjectsCode/obsidian-meta-bind-plugin)
- [Dataview](https://github.com/blacksmithgu/obsidian-dataview)
- [JS Engine](https://github.com/mProjectsCode/obsidian-js-engine-plugin)
- [Charts View](https://github.com/caronchen/obsidian-chartsview-plugin)