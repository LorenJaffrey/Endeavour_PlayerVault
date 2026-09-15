```dataviewjs
try {
    // Only proceed if "Übung.Rüstungen" exists and contains items
    if (dv.current().Übung?.Rüstungen && dv.current().Übung.Rüstungen.length > 0) {
	    dv.header(3, "Rüstung");
        dv.list(
            dv.pages("#Gegenstand/Rüstung")
                .where(page => dv.current().Übung.Rüstungen.some(link => link.path === page.file.path))
                .sort(page => page.file.name)
                .map(page => page.file.link)
        );
    }
} catch (error) {
    console.error("An error occurred in DataviewJS:", error);
}
```