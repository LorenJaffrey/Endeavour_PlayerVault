```dataviewjs
try {
	const videoPath = dv.current().Hintergrund.Video.path; // Get the video path from the note's field
	const vaultPath = app.vault.adapter.basePath.replace(/\\\\/g, '').replace(/\\/g, '/');
	//there needs to be an image on the form so the reference is available "`="!" + this.Hintergrund.Bild`"
	const referenceImage = document.querySelector(`img[alt="${dv.current().Hintergrund.Bild.path.split('/').pop()}"]`)?.src ?? '';
	const appPart = referenceImage.split('/').slice(0, 3).join('/') + '/';

// Construct the video HTML tag with autoplay and loop attributes
const videoHTML = `
<video autoplay loop muted>
	<source src="${appPart}${vaultPath}/${videoPath}" type="video/mp4">
	Your browser does not support the video tag.
</video>
`;

	// Output the video tag into the note
	dv.el("div", videoHTML, { cls: "video-container" });

	// Function to restart the video
	function restartVideo() {
	  const video = document.getElementById("video-player");
	  if (video) {
	    video.currentTime = 0; // Restart the video
	    video.play();          // Play the video again
	  }
	}

	// Listen for the active note change in Obsidian
	app.workspace.on("active-leaf-change", function () {
	  if (document.hidden === false) {
	    restartVideo(); // Restart the video when the note is switched and becomes active
	  }
	});

} catch(error) {
	console.error("An error occurred in DataviewJS:", error);
}
```