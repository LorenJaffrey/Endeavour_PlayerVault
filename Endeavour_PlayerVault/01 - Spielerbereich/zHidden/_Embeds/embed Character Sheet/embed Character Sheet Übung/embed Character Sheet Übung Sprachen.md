```dataviewjs
try {
    // Only proceed if "Übung.Sprachen" exists and contains items
    if (dv.current().Übung?.Sprachen && dv.current().Übung.Sprachen.length > 0) {
	    dv.header(3, "Sprachen");
        dv.list(
            dv.pages("#Sprache")
                .where(page => dv.current().Übung.Sprachen.some(link => link.path === page.file.path))
                .sort(page => page.file.name)
                .map(page => page.file.link)
        );
    }
} catch (error) {
    console.error("An error occurred in DataviewJS:", error);
}
```