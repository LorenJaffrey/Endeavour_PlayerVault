```dataviewjs
try {
    // Only proceed if "Übung.Werkzeuge" exists and contains items
    if (dv.current().Übung?.Werkzeuge && dv.current().Übung.Werkzeuge.length > 0) {
	    dv.header(3, "Werkzeuge");
        dv.list(
            dv.pages("#Gegenstand/Werkzeug")
                .where(page => dv.current().Übung.Werkzeuge.some(link => link.path === page.file.path))
                .sort(page => page.file.name)
                .map(page => page.file.link)
        );
    }
} catch (error) {
    console.error("An error occurred in DataviewJS:", error);
}
```