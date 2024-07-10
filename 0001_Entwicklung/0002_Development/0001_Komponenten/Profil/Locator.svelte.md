![[Pasted image 20240704141748.png]]
Die `Locator`-Komponente ist eine komplexe Svelte-Komponente zur Verwaltung und Darstellung von anpassbaren Grid-Elementen. Diese Komponente ist nützlich, um verschiedene Inhalte wie Text, Bilder und Tags in einem Grid-Layout anzuzeigen und zu bearbeiten.

Die `Locator`-Komponente wird in der Applikation zur Darstellung und Bearbeitung der Inhalte genutzt. Sie findet sowohl Anwendung im privaten Bereich `/profil/[artists]`und  im öffentlichem Bereich`/artists/[name]` , als auch in der Darstellung der Arbeiten in `/artists/[name]/[title]`.

Diese Komponente implimentiert das in [[Drag and Drop]] spezifizierte Userinterface. Vorwiegende anwendung findet es in [[Profil (privat)]] oder 


```html
<GridEditor {data} {viewMode} {toggle} {form} />
```

## Props

| Name | Typ | Beschreibung | Standardwert |
| --- | --- | --- | --- |
| `data` | Objekt | Enthält die Daten des Grids, einschließlich der Elemente, die angezeigt und bearbeitet werden sollen. | - |
| `viewMode` | Boolean | Wenn `true`, wird die Komponente im Anzeigemodus dargestellt. Andernfalls ist die Bearbeitung möglich. | `false` |
| `toggle` | Boolean | Steuert den Bearbeitungsmodus des Grids. Wenn `true`, können die Grid-Elemente bearbeitet werden. | `false` |
| `form` | Objekt | Enthält das Formular-Objekt, das zum Speichern und Übermitteln der Daten verwendet wird. | - |

## Funktionen

| Name | Beschreibung | Parameter |
| --- | --- | --- |
| `remove(id)` | Entfernt ein Element mit der angegebenen ID aus dem Grid. | `id` (String): Die ID des zu entfernenden Elements. |
| `addNewItem(type)` | Fügt ein neues Element des angegebenen Typs dem Grid hinzu. | `type` (String): Der Typ des neuen Elements (`paragraphs`, `headlines`, `pictures`). |
| `submit(DOMid)` | Übermittelt das Formular mit der angegebenen ID. | `DOMid` (String): Die ID des zu übermittelnden Formulars. |

## Komponenten

| Komponente            | Beschreibung                                                                          |
| --------------------- | ------------------------------------------------------------------------------------- |
| `Grid` und `GridItem` | Stellt das Grid-Layout dar und ermöglicht das Drag-and-Drop von Elementen.            |
| `Headline`            | Zeigt eine Überschrift an und ermöglicht deren Bearbeitung.                           |
| `Paragraph`           | Zeigt einen Absatz an und ermöglicht dessen Bearbeitung.                              |
| `Pictures`            | Zeigt ein Bild an und ermöglicht dessen Bearbeitung.                                  |
| `DeleteV_2`           | Stellt eine Löschfunktionalität zur Verfügung, um 
## Menu-Komponente

Die Menu-Komponente stellt ein Formular dar, mit dem die Eigenschaften eines Werks bearbeitet werden können. Das Formular wird nur angezeigt, wenn die `toggle`-Variable auf `true` gesetzt ist.

### Funktionen

| Name | Beschreibung | Parameter |
| --- | --- | --- |
| `addNewItem(type)` | Fügt ein neues Element des angegebenen Typs dem Grid hinzu. | `type` (String): Der Typ des neuen Elements (`paragraphs`, `headlines`, `pictures`). |
| `submit(DOMid)` | Übermittelt das Formular mit der angegebenen ID. | `DOMid` (String): Die ID des zu übergebenen Formulars. |



Die Komponente besteht aus einem Formular mit verschiedenen UI-Elementen, die für die Bearbeitung der Eigenschaften des Werks verwendet werden.

- **Formular:**
  Das Formular wird verwendet, um die Eigenschaften des Werks zu ändern. Es wird nur angezeigt, wenn `toggle` auf `true` gesetzt ist.

- **Titel:**
  Der Titel des Werks kann bearbeitet werden. Es wird mit dem `TipTap`-Editor angezeigt.

- **Jahr:**
  Das Jahr des Erstellungsdatums des Werks kann bearbeitet werden. Es wird mit einem `<input>`-Element angezeigt.

- **Tags:**
  Die Tags des Werks können bearbeitet werden. Es wird mit dem `Tags`-Komponenten angezeigt.

- **Menüelemente:**
  Das Menüelement enthält verschiedene Schaltflächen, mit denen neue Absätze, Überschriften oder Bilder hinzugefügt werden können.

- **Submit-Button:**
  Der Submit-Button ermöglicht das Speichern der Änderungen am Werk.

- **TogglePublicState:**
  Die Komponente ermöglicht das Umschalten des öffentlichen Status des Werks.

- **TagDisplay:**
  Die Komponente zeigt die Tags des Werks an.
## Styling

Die Komponente verwendet CSS, um ihre Darstellung anzupassen. Die folgenden Styles werden verwendet:

- **Formular und Hauptcontainer:**
  ```css
  form {
    width: 100%;
  }

  main {
    position: relative;
    width: 100%;
    height: 100vh;
    overflow-y: scroll;
  }

  #menu {
    position: sticky;
    bottom: 0;
    width: 100%;
    background-color: var(--bg-light);
  }
  ```

- **Grid-Elemente:**
  ```css
  .remove {
    cursor: pointer;
    position: absolute;
    right: -1rem;
    top: -2rem;
    user-select: none;
    color: var(--error-color);
    outline-style: solid 1px white;
    background: transparent;
  }

  .menuwrapper {
    outline: var(--button-border);
    padding: 0.5rem;
    display: flex;
    justify-content: center;
    align-content: center;
    align-self: end;
    justify-self: end;
    gap: 1rem;
    width: 100%;
    z-index: 9999;
    border: solid 0.1rem var(--text-light);
  }

  :global(.grid-item) {
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 1;
    border: dashed 1px var(--text-light);
    width: fit-content;
    box-shadow: 2px 5px 16px 0px #0b325e, 5px -3px 0px 13px rgba(0, 0, 0, 0);
  }

  :global(.grid-item-watcher) {
    display: flex;
    justify-content: center;
    align-items: center;
    border: none;
    width: fit-content;
    height: fit-content;
    background: transparent;
  }

  :global(.gridViewer) {
    width: 100%;
    overflow: none;
  }

  :global(.preview) {
    opacity: 0.7;
    background-color: var(--tertiary);
    box-shadow: 0 0 0 1px var(--text-light);
  }
  ```

## Verwendung

Die `GridEditor`-Komponente wird verwendet, um ein anpassbares Grid-Layout darzustellen und zu bearbeiten. Sie ist besonders nützlich für Anwendungen, bei denen Benutzer Inhalte dynamisch hinzufügen, entfernen und anpassen müssen.

```js
<GridEditor {data} {viewMode} {toggle} {form} />
```

