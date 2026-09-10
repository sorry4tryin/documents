* goal: when the user inputs into the ai agent, opencode or pi.dev have the ability to use a template prompt. this is used to produce a better output from the selected agent/model
	* name: prompt-autoload
	* description: loads a prompt for each user input
	* template prompt: this consist of a selected cluster of words that dictate how an local machine model will respond
		* location: ~/.opencode/plugin/prompt-autoload.ts
	* function: user inputs a response -> selected prompt is used -> machine model receives -> prompt applied -> machine output