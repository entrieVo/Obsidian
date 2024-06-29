---
logic: 
encyclopedia: 
rhetoric: 
drama: 
conceptualization: 
visual_calculus: 
volition: 
inland_empire: 
empathy: 
authority: 
esprit_de_corps: 
suggestion: 
endurance: 
pain_threshold: 
physical_instrumen: 
electrochemistry: 
shivers: 
half_light: 
hand_eye_coordination: 
perception: 
reaction_speed: 
savoir_faire: 
interfacing: 
composure: 
---
<span style="color:#5b8ff9">🧠 INTELLECT: `VIEW[{logic} + {encyclopedia} + {rhetoric} + {drama} + {conceptualization} + {visual_calculus}]`

<span style="color:#5ad8a6">🗿 PSYCHE: `VIEW[{volition} + {inland_empire} + {empathy} + {authority} + {esprit_de_corps} + {suggestion}]`

<span style="color:#5d7092">💪🏼 PSYSIQUE: `VIEW[{endurance} + {pain_threshold} + {physical_instrumen} + {electrochemistry} + {shivers} + {half_light}]`

<span style="color:#f6bd16">🦾 MOTORICS: `VIEW[{hand_eye_coordination} + {perception} + {reaction_speed} + {savoir_faire} + {interfacing} + {composure}]`

```dataviewjs
const skill = [
'logic', 'encyclopedia', 'rhetoric', 'drama', 'conceptualization', 'visual_calculus', 'volition', 'inland_empire', 'empathy', 'authority', 'esprit_de_corps', 'suggestion', 'endurance', 'pain_threshold', 'physical_instrumen', 'electrochemistry', 'shivers', 'half_light', 'hand_eye_coordination', 'perception', 'reaction_speed', 'savoir_faire', 'interfacing', 'composure'
];
const class_name = [
'INTELLECT', 'PSYCHE', 'PSYSIQUE', 'MOTORICS'
];

const file = app.vault.getAbstractFileByPath(dv.current().file.path);
const metadata = app.metadataCache.getFileCache(file);
const frontmatter = metadata.frontmatter;

var chart = '\
```chartsview\n\
type: Radar\n\
\n\
data:\n';

const GROUP_NUM = skill.length / class_name.length;
for (let i = 0; i < GROUP_NUM; i++) {

	for (let k = 0; k < class_name.length; k++) {
		chart += '\
  - item: "' + skill[i + (k * GROUP_NUM)] + '"\n\
    user: "' + class_name[k] + '"\n\
    score: ' + frontmatter[skill[i + (k * GROUP_NUM)]] + '\n';
	}
}

chart += '\
options:\n\
  xField: "item"\n\
  yField: "score"\n\
  seriesField: "user"\n\
  meta:\n\
    score:\n\
      alias: "Score"\n\
      min: 0\n\
      nice: true\n\
  xAxis:\n\
    line: null\n\
    tickLine: null\n\
  yAxis:\n\
    label: false\n\
    grid:\n\
      alternateColor: "rgba(0, 0, 0, 0.04)"\n\
  point: {}\n\
  area: {}\n\
```';

dv.span(chart);
```

> [!danger]+ Characteristics control
> **INTELLECT**
> - Logic: `INPUT[slider(minValue(0), maxValue(10)):logic]` `VIEW[{logic}]`
> - Encyclopedia: `INPUT[slider(minValue(0), maxValue(10)):encyclopedia]` `VIEW[{encyclopedia}]`
> - Rhetoric: `INPUT[slider(minValue(0), maxValue(10)):rhetoric]` `VIEW[{rhetoric}]`
> - Drama: `INPUT[slider(minValue(0), maxValue(10)):drama]` `VIEW[{drama}]`
> - Conceptualization: `INPUT[slider(minValue(0), maxValue(10)):conceptualization]` `VIEW[{conceptualization}]`
> - Visual calculus: `INPUT[slider(minValue(0), maxValue(10)):visual_calculus]` `VIEW[{visual_calculus}]`
> 
> **PSYCHE**
> - Volition: `INPUT[slider(minValue(0), maxValue(10)):volition]` `VIEW[{volition}]`
> - Inland empire: `INPUT[slider(minValue(0), maxValue(10)):inland_empire]` `VIEW[{inland_empire}]`
> - Empathy: `INPUT[slider(minValue(0), maxValue(10)):empathy]` `VIEW[{empathy}]`
> - Authority: `INPUT[slider(minValue(0), maxValue(10)):authority]` `VIEW[{authority}]`
> - Esprit de corps: `INPUT[slider(minValue(0), maxValue(10)):esprit_de_corps]` `VIEW[{esprit_de_corps}]`
> - Suggestion: `INPUT[slider(minValue(0), maxValue(10)):suggestion]` `VIEW[{suggestion}]`
> 
> **PSYSIQUE**
> - Endurance: `INPUT[slider(minValue(0), maxValue(10)):endurance]` `VIEW[{endurance}]`
> - Pain threshold: `INPUT[slider(minValue(0), maxValue(10)):pain_threshold]` `VIEW[{pain_threshold}]`
> - Physical instrumen: `INPUT[slider(minValue(0), maxValue(10)):physical_instrumen]` `VIEW[{physical_instrumen}]`
> - Electrochemistry: `INPUT[slider(minValue(0), maxValue(10)):electrochemistry]` `VIEW[{electrochemistry}]`
> - Shivers: `INPUT[slider(minValue(0), maxValue(10)):shivers]` `VIEW[{shivers}]`
> - Half light: `INPUT[slider(minValue(0), maxValue(10)):half_light]` `VIEW[{half_light}]`
> 
> **MOTORICS**
> - Hand/eye coordination: `INPUT[slider(minValue(0), maxValue(10)):hand_eye_coordination]` `VIEW[{hand_eye_coordination}]`
> - Perception: `INPUT[slider(minValue(0), maxValue(10)):perception]` `VIEW[{perception}]`
> - Reaction speed: `INPUT[slider(minValue(0), maxValue(10)):reaction_speed]` `VIEW[{reaction_speed}]`
> - Savoir faire: `INPUT[slider(minValue(0), maxValue(10)):savoir_faire]` `VIEW[{savoir_faire}]`
> - Inerfacing: `INPUT[slider(minValue(0), maxValue(10)):interfacing]` `VIEW[{interfacing}]`
> - Composure: `INPUT[slider(minValue(0), maxValue(10)):composure]` `VIEW[{composure}]`
> 
> ```meta-bind-button
> style: destructive
> label: 🗑️ Clear
> action:
>   type: js
>   file: Visualization/scripts/clear.md
> ```