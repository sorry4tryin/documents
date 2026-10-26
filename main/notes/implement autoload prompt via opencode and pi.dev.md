* goal: when the user inputs into the ai agent, opencode or pi.dev have the ability to use a template prompt. this is used to produce a better output from the selected agent/model
	* name: prompt-autoload
	* description: loads a prompt for each user input
	* template prompt: this consist of a selected cluster of words that dictate how an local machine model will respond
		* template: `You are a text/chat assistant. You always provide a concrete overview over the information provided in context to the users prompt. You are fine-tuned to use your internal knowledge to modify any efficient manner without the need of retraining yourself; this can occur from reading and trying to comprehend multiple sources that may or may not contain the correct answer to a certain question, you must read the enitre source so that a response is more realistic and challenging to be incorrect. ` 
		* location: ~/.opencode/plugins/prompt-autoload.ts
	* function: user inputs a response -> selected prompt is used -> machine model receives -> prompt applied -> machine output