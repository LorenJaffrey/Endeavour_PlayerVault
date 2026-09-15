```dataviewjs
try {
    const attacks = getAttacks();
    const attributes = dv.current().Attribute

    if (attacks && hasMeleeAttacks()) {

        dv.header(3, "Nahkampf");

        dv.table(
            ["Waffe", "Reichweite", "Angriff", "Schaden", "Schadensart", "Eigenschaften"],
            dv.pages("#Gegenstand/Waffe/Klasse/Nahkampfwaffe or #Angriff/Nahkampf")
                .where(p => attacks && attacks.some(link => link.path === p.file.path)) 
                .sort(page => page.file.name)
                .map(page => {
                    // Calculate Angriff
                    let magicStat = getMagicStat();
                    let attackStat = attributes.Stärke;
                    if (page?.Eigenschaften?.some(link => link?.path?.includes("Gegenstände/Waffen/Waffeneigenschaften/Finesse.md"))){
	                    attackStat = Math.max(attackStat, attributes.Geschicklichkeit);
                    }
                    if (page?.Eigenschaften?.some(link => link?.path?.includes("Gegenstände/Waffen/Waffeneigenschaften/Magische Präzision.md"))){
	                    attackStat = Math.max(attackStat, attributes[magicStat]);
					}
                    const attackModifier = Math.floor((attackStat - 10) / 2);
                    const proficiencyBonus = getProficiencyBonus(page);
                    const attackRoll = `\`dice:1d20+${attackModifier + proficiencyBonus + (page?.Angriffsbonus ?? 0)}\``;

                    // Calculate Schaden
                    const damageRoll = `\`dice:${page.Schaden}+${attackModifier+(page?.Schadensbonus ?? 0)}\``;

                    return [
                        page.file.link,
                        page.Reichweite,
                        attackRoll,
                        damageRoll,
                        page.Schadensart,
                        page.Eigenschaften
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

    function hasMeleeAttacks() {
        let isMeleeAttack = false;

        for (let item of attacks) {
            let page = dv.page(item.path);
            let targetTagMeleeWeapon = "Gegenstand/Waffe/Klasse/Nahkampfwaffe";
            let targetTagMeleeAttack = "Angriff/Nahkampf";

            isMeleeAttack = hasTag(page, targetTagMeleeWeapon) || hasTag(page, targetTagMeleeAttack);

            if (isMeleeAttack) {
                break;
            }
        }
        return isMeleeAttack
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


