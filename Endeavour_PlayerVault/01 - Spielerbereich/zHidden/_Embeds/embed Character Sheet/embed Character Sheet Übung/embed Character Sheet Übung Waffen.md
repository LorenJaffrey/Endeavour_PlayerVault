```dataviewjs
try {
    // Only proceed if "Übung.Waffen" exists and contains items
    if (dv.current().Übung?.Waffen && dv.current().Übung.Waffen.length > 0) {
	    dv.header(3, "Waffen");
        dv.list(
            dv.pages("#Gegenstand/Waffe")
                .concat(dv.pages("#Liste/Waffen"))
                .where(page => dv.current().Übung.Waffen.some(link => link.path === page.file.path))
                .sort(page => page.file.name)
                .map(page => page.file.link)
        );
    }
} catch (error) {
    console.error("An error occurred in DataviewJS:", error);
}
```