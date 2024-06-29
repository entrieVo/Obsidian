const skill = [
'logic', 'encyclopedia', 'rhetoric', 'drama', 'conceptualization', 'visual_calculus', 'volition', 'inland_empire', 'empathy', 'authority', 'esprit_de_corps', 'suggestion', 'endurance', 'pain_threshold', 'physical_instrumen', 'electrochemistry', 'shivers', 'half_light', 'hand_eye_coordination', 'perception', 'reaction_speed', 'savoir_faire', 'interfacing', 'composure'
];

const file = app.workspace.getActiveFile();
app.vault.process(file, (data) => {

	const text = data.split('\n').map(string => {

		skill.forEach((s) => {
			if (string.includes(s + ':'))
			string = s + ': ';
		})

		return string;
	}).join('\n');

	return text;
});
