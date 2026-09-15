| Tab                   |                      Ein-/Ausblenden                      |
| --------------------- |:---------------------------------------------------------:|
| Waffen Angriff        |  `INPUT[toggle:InputData.ShowHideSection.WeaponAttack]`   |
| Magischer Angriff     |   `INPUT[toggle:InputData.ShowHideSection.MagicAttack]`   |
| Fähigkeiten           |     `INPUT[toggle:InputData.ShowHideSection.Skills]`      |
| Persönlichkeit        |   `INPUT[toggle:InputData.ShowHideSection.Personality]`   |
| Statistik             |    `INPUT[toggle:InputData.ShowHideSection.Statistic]`    |
| Vergangenheit         |      `INPUT[toggle:InputData.ShowHideSection.Past]`       |
| Hintergrundgeschichte | `INPUT[toggle:InputData.ShowHideSection.BackgroundStory]` |


```js-engine
// Grab the Meta Bind API and extract metadata fields
const mb = engine.getPlugin('obsidian-meta-bind-plugin').api;
const showHideSectionMetadata = context.metadata.frontmatter.InputData.ShowHideSection;

const toggleViewWeaponAttackMetaData = mb.parseBindTarget('InputData.ShowHideSection.WeaponAttack', context.file.path);
const changeEventPointerWeaponAttack = engine.reactive((value) => {onToogleChange(value, 'Angriff')}, mb.getMetadata(toggleViewWeaponAttackMetaData));
const toggleViewMagicAttackMetaData = mb.parseBindTarget('InputData.ShowHideSection.MagicAttack', context.file.path);
const changeEventPointerMagicAttack = engine.reactive((value) => {onToogleChange(value, 'Magie')}, mb.getMetadata(toggleViewMagicAttackMetaData));
const toggleViewSkillsMetaData = mb.parseBindTarget('InputData.ShowHideSection.Skills', context.file.path);
const changeEventPointerSkills = engine.reactive((value) => {onToogleChange(value, 'Fähigkeiten')}, mb.getMetadata(toggleViewSkillsMetaData));
const toggleViewPersonalityMetaData = mb.parseBindTarget('InputData.ShowHideSection.Personality', context.file.path);
const changeEventPointerPersonality = engine.reactive((value) => {onToogleChange(value, 'Persönlichkeit')}, mb.getMetadata(toggleViewPersonalityMetaData));
const toggleViewPastMetaData = mb.parseBindTarget('InputData.ShowHideSection.Past', context.file.path);
const changeEventPointerPast = engine.reactive((value) => {onToogleChange(value, 'Vergangenheit')}, mb.getMetadata(toggleViewPastMetaData));
const toggleViewBackgroundStoryMetaData = mb.parseBindTarget('InputData.ShowHideSection.BackgroundStory', context.file.path);
const changeEventPointerBackgroundStory = engine.reactive((value) => {onToogleChange(value, 'Hintergrundgeschichte')}, mb.getMetadata(toggleViewBackgroundStoryMetaData));
const toggleViewStatisticMetaData = mb.parseBindTarget('InputData.ShowHideSection.Statistic', context.file.path);
const changeEventPointerStatistic = engine.reactive((value) => {onToogleChange(value, 'Statistik')}, mb.getMetadata(toggleViewStatisticMetaData));

let eventIsTriggered = false;

function onToogleChange(value, headerValue) {
	const header = document.querySelector(`h2[data-heading="${headerValue}"]`);

	if(header) {
		const parentDivElement = header.parentElement;
		if (parentDivElement) {
			const contentContainer = parentDivElement.nextElementSibling;

			if(value) {
				parentDivElement.style.display = 'block';
				
				if(contentContainer) {
					contentContainer.style.display = 'block';
				}				
			} else {
				parentDivElement.style.display = 'none';

				if(contentContainer) {
					contentContainer.style.display = 'none';
				}
			}
		}
	}
}

setTimeout(()=>{
	mb.subscribeToMetadata(toggleViewWeaponAttackMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerWeaponAttack.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewMagicAttackMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerMagicAttack.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewSkillsMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerSkills.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewPersonalityMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerPersonality.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewPastMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerPast.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewBackgroundStoryMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerBackgroundStory.refresh(value); }); 
	mb.subscribeToMetadata(toggleViewStatisticMetaData, component, (value) => { eventIsTriggered = true; changeEventPointerStatistic.refresh(value); }); 
	onToogleChange(false, 'Versteckte Logiken & Button Konfigurationen');
}, 80);

//let triggerCounter = 0;

function initMetaBindings(){
	if(eventIsTriggered) {
		//no changes are needed anymore
		//console.log('eventIsTriggered: ' + eventIsTriggered);
		onToogleChange(false, 'Versteckte Logiken & Button Konfigurationen');
		return;
	}
	
	//console.log(++triggerCounter);

	//initial view
	changeEventPointerWeaponAttack.refresh(showHideSectionMetadata.WeaponAttack);
	changeEventPointerMagicAttack.refresh(showHideSectionMetadata.MagicAttack);
	changeEventPointerSkills.refresh(showHideSectionMetadata.Skills);
	changeEventPointerPersonality.refresh(showHideSectionMetadata.Personality);
	changeEventPointerPast.refresh(showHideSectionMetadata.Past);
	changeEventPointerBackgroundStory.refresh(showHideSectionMetadata.BackgroundStory);
	changeEventPointerStatistic.refresh(showHideSectionMetadata.Statistic);
	onToogleChange(false, 'Versteckte Logiken & Button Konfigurationen');
}

// Function to start observing the specific container for added <div> elements
function observeDivElements() {
	const container = document.querySelector('.markdown-preview-sizer.markdown-preview-section'); // Target container
	
	if (!container) {
		// If the container isn't present, retry after a delay
		setTimeout(observeDivElements, 500);
		return;
	}

	// MutationObserver callback to detect added <div> elements
	const observer = new MutationObserver((mutationsList, observer) => {
		for (let mutation of mutationsList) {
			if (mutation.type === 'childList') {
				mutation.addedNodes.forEach(node => {
					// Check if the added node is a <div> element
					if (node.nodeName === 'DIV') {
						initMetaBindings(); // Trigger event when <div> is added
					}
				});
			}
		}
	});

	// Start observing the container for child additions (additions of <div> elements)
	observer.observe(container, { childList: true, subtree: true });
}

// Start observing once the layout is ready
this.app.workspace.onLayoutReady(() => {
	observeDivElements(); // Start observing for dynamically added <div> elements
});

```