# Integrate unity into AIMind

## First step
* Save copies of AIMind in "NarrativeBackendRPI-master\Data Entry\Data Entry\Lost Manuscript II Data Entry\bin\Debug" and "storytelling-infrastructure\Assets\StreamingAssets\xml"
* Quick way to test the validity of AIMind
     * run "Dialogue Data Entry.exe" as admisitrator from "NarrativeBackendRPI-master\Data Entry\Data Entry\Lost Manuscript II Data Entry\bin\Debug"
     * open AIMind in Data Entry and wait until the query windows shows up without any error
	 * then this AIMind is valid for NarrativeBackend

## Second step
* Make a copy of existing unity file from "storytelling-infrastructure\Assets\Scenes" and change its name to new AIMind
* Open the copied unity file and click on "loader" folder on the left
* Change xml_location on the right to new AIMind by change the name after "/xml/" to name of new AIMind
* Change "NarrationManager.cs" file
	 * Double click the block after Script in Narration Manager to open file "NarrationManager.cs"
	 * Find "switch (scene.name)" in "NarrationManager.cs" and copy the code from first "case" to first "break" under "switch (scene.name)"
	 * Paste the copied code under the last "case" and "break" with name changed to new unity file, and also a new pair of numbers in "Narrate(x, y)"
* Open "Build Settings" in "File" and click "Add Open Scenes", then check new AIMind
* If doesn't show the right map
	 * Click on "MapImage" in "MapCanvas" on the left
	 * Change Latitude and Longitude in "Center location" on the right to parameters of center of expetced map
	 * Change parameters in "Zoom", "Latitude Range" and "Longitude Range" if necessary

## Play
* Suggestion: Switch game window dimensions to "Standalone (5888 x 1080)"
* Click on play button on the top
	 * Wait until all Nodes appears in the screen and turned grey
		 * If no Nodes appears because of the wrong map, see the sixth note in Second step
	 * navigation
		 * press enter to minimize map and start narrative
		 * buttons and nodes can be used to navigate narrative data
		 * map will scale and zoom to selected data
	 * debug key bindings
		 * "SHIFT + D + L + 1|2|3" to load "Roman Empire|Analogy|WWII" domains
		 * map
			 * "SHIFT + M + L + N|E|K" to load cached "Terrain|Satelite|SateliteDark" map images
			 * "SHIFT + M + S" to save currently displayed map as "Resources\maps\google_staticmap_lastSaved.png"
		 * "SHIFT + C + S" to capture screenshots
		 * "CTRL + D" show debug gismos
