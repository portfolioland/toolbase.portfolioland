## User Interface - Drag and Drop
Um auf mobilen Endgeräten, sowie Desktops einen möglichst reibungsloses Bedienen zu ermöglichen, nutzen wir das Prinzip des Drag and Drop. Text-Elemente, wie Überschriften, Paragraphen, aber auch Medien-Elemente, wie Bilder und Bewegtbilder können so per Finger/Zeiger-Bewegung einfach kollagiert werden. 
Hierzu gibt [[Portfolioland]] ein hilfreiches Raster vor, an dem entlang sich die Elemente anreihen lassen. 
Das Interfacedesign versucht für möglichst viele Einstellungen der Plattform, hier beispielhaft erwähnt: die Anordnung der einzelnen Elemente oder die Anzeigereihenfolge der einzelnen Arbeiten, dieses "haptische" Bedienelement einzusetzen.
# [[Svelte-Grid]]
Svelte-Grid ist eine leistungsstarke Bibliothek, die es ermöglicht, Rasterlayouts in [[0001_Entwicklung/0002_Development/0002_Dependencies/Sveltekit|Sveltekit]]-Anwendungen einfach zu erstellen. Es bietet eine Drag-and-Drop-Funktionalität sowie die Möglichkeit, Elemente innerhalb des Rasters zu vergrößern und zu verkleinern. Diese Funktionen machen es ideal für die Erstellung von benutzerdefinierten Dashboards, interaktiven Design-Oberflächen und anderen Anwendungen, die komplexe Layouts erfordern.

## Datenlayout

```js
let data = [
{
	"x": number,
	"y": number,
	"w": number,
	"h": number,
	"id": id,
	"content": content,
	"collectionID": collectionID,
	"type": "pictures||headlines||paragraphs||...",
	"credits": "",
	"altTxt": ""
	}
];
 ```
 
