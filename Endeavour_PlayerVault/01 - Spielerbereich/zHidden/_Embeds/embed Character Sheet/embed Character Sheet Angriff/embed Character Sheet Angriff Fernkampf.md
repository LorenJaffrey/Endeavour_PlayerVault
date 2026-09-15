```dataviewjs
try {
    const attacks = getAttacks();
    const attributes = dv.current().Attribute

    if (attacks && hasRangedAttacks()) {

        dv.header(3, "Fernkampf");

        dv.table(
            ["Waffe", "Min RW", "Gnd RW", "Max RW", "Angriff", "Schaden", "Schadensart", "Eigenschaften"],
            dv.pages("#Gegenstand/Waffe/Klasse/Fernkampfwaffe/Schusswaffe or #Angriff/Fernkampf")
                .where(p => attacks && attacks.some(link => link.path === p.file.path))
                .sort(page => page.file.name)
                .map(page => {
                    // Calculate Angriff
                    let magicStat = getMagicStat();
                    let attackStat = attributes.Geschicklichkeit;
                    if (page?.Eigenschaften?.some(link => link?.path?.includes("Gegenstände/Waffen/Waffeneigenschaften/Magische Präzision.md"))){
	                    attackStat = Math.max(attackStat, attributes[magicStat]);
					}
                    let attackModifier = Math.floor((attackStat - 10) / 2);
                    const proficiencyBonus = getProficiencyBonus(page);
                    let attackRoll = `\`dice:1d20+${attackModifier + proficiencyBonus + (page?.AngriffsbonusFern ?? 0)}\``;

                    // Calculate Schaden
                    let damageRoll = `\`dice:${page.SchadenFern}+${attackModifier+(page?.SchadensbonusFern ?? 0)}\``;

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

    function hasRangedAttacks() {
        let isRangedWeapon = false;

        for (let item of attacks) {
            let page = dv.page(item.path);
            let targetTagRangedWeapon = "Gegenstand/Waffe/Klasse/Fernkampfwaffe/Schusswaffe";
            let targetTagRangedAttack = "Angriff/Fernkampf";

            // Call the function and store the result
            isRangedWeapon = hasTag(page, targetTagRangedWeapon) || hasTag(page, targetTagRangedAttack);

            if (isRangedWeapon) {
                break;
            }
        }

        return isRangedWeapon;
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