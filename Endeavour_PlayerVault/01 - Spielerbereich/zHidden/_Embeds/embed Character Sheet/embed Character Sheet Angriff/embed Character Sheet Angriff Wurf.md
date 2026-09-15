```dataviewjs
try {
	const attacks = getAttacks();
    const attributes = dv.current().Attribute

    if (attacks && hasThrowingAttack()) {

        dv.header(3, "Wurf");

        // Create table with headers
        dv.table(
            ["Waffe", "Min RW", "Gnd RW", "Max RW", "Angriff", "Schaden", "Schadensart", "Eigenschaften"],
            dv.pages("#Gegenstand/Waffe/Klasse/Fernkampfwaffe/Wurfwaffe")
                .where(p => attacks && attacks.some(link => link.path === p.file.path)) 
                .sort(page => page.file.name)
                .map(page => {
                    // Determine the attribute modifier based on Finesse property
                    let magicStat = getMagicStat();
                    let attackStat = attributes.Stärke;
                    if (page?.Eigenschaften?.some(link => link?.path?.includes("Gegenstände/Waffen/Waffeneigenschaften/Finesse.md"))){
	                    attackStat = Math.max(attackStat, attributes.Geschicklichkeit);
                    }
                    if (page?.Eigenschaften?.some(link => link?.path?.includes("Gegenstände/Waffen/Waffeneigenschaften/Magische Präzision.md"))){
	                    attackStat = Math.max(attackStat, attributes[magicStat]);
					}

                    // Calculate attack roll
                    const attackModifier = Math.floor((attackStat - 10) / 2);
                    const proficiencyBonus = getProficiencyBonus(page);
                    const rangedAttackBonus = dv.current().AngriffsbonusFern || 0;
                    const attackRoll = `\`dice:1d20+${attackModifier + proficiencyBonus + rangedAttackBonus}\``;

                    // Calculate damage roll
                    const damageRoll = `\`dice:${page.SchadenFern}+${attackModifier+(page?.SchadensbonusFern ?? 0)}\``;

                    return [
                        page.file.link,
                        page.Range1,
                        page.Range2,
                        page.Range3,
                        attackRoll,
                        damageRoll,
                        page.SchadensartFern,
                        page.EigenschaftenFern
                    ];
                })
        );
    }

	function getProficiencyBonus(page) {
		if (!dv.current().Übung) {
			return (Math.ceil(getLevelStat() / 4) + 1)
		}
		const hasDirectProficiency = dv.current().Übung.Waffen.filter(item => item.path == page.file.path).length === 1;
		const hasGlobalProficiency = dv.current().Übung.Waffen.filter(item => item.path == page.Kategorie.path).length === 1;
		return (hasDirectProficiency || hasGlobalProficiency) ? (Math.ceil(getLevelStat() / 4) + 1) : 0;		 
	}


	function getAttacks() {
		if(dv.current().Waffen) {
			return dv.current().Waffen;
		} 
		else if (dv.current().Angriff)
			return dv.current().Angriff;
	}

    function hasTag(page, targetTag) {
        return page?.tags && page?.tags?.some(tag => tag === targetTag);
    }

	// Helper function to check if the weapon is a throwable ranged weapon
    function hasThrowingAttack() {
        let isThrowable = false;

        for (let item of attacks) {
            let page = dv.page(item.path);
            let targetTag = "Gegenstand/Waffe/Klasse/Fernkampfwaffe/Wurfwaffe";

            isThrowable = hasTag(page, targetTag);

            if (isThrowable) {
                break;
            }
        }

        return isThrowable;
    }

	function getMagicStat() {
		let magicStat = null;
		if (dv.current().Hintergrund) {
			magicStat = dv.page(dv.current().Hintergrund.Klasse).Zauberattribut ? dv.page(dv.current().Hintergrund.Klasse).Zauberattribut.fileName() : null;
		}
		else if (dv.current().Zauberwirken) {
			magicStat = dv.page(dv.current().Zauberwirken.Zauberattribut) ? dv.page(dv.current().Zauberwirken.Zauberattribut).file.name : null;
		}
		return magicStat;
	}

	function getLevelStat() {
		if (dv.current().Herausforderungsgrad) {
			return dv.current().Herausforderungsgrad;
		}
		else {
			return dv.current().Stufe;
		}
	}


} catch (error) {
    console.error("An error occurred in DataviewJS:", error);
}

```