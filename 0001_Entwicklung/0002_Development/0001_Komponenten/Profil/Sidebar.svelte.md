![[Frame 37.png]]

# Sidebar-Komponente

Dies ist eine Svelte-Komponente, die als Seitenleiste für das Profil eines Benutzers dient. Sie zeigt den Namen des Benutzers, das Profilbild und eine Liste seiner Werke an. Die Seitenleiste kann geöffnet oder geschlossen sein, und der Benutzer kann neue Werke aus dem Profil hinzufügen. Die Komponente enthält außerdem eine Umschaltfläche, um die Sichtbarkeit öffentlicher Werke zu aktivieren oder zu deaktivieren. Die Komponente verwendet die Svelte-Toggle-Bibliothek, um die Umschaltfläche zu implementieren.

## Props

| Name | Typ | Standardwert | Beschreibung |
| --- | --- | --- | --- |
| `open` | boolean | `false` | Legt fest, ob die Seitenleiste geöffnet oder geschlossen ist. |
| `data` | Objekt | | Enthält die Daten des Benutzers, einschließlich seines Namens, Profilbilds und Werken. |
| `form` | Objekt | | Enthält die Daten des Benutzerformulars. |
| `addWork` | boolean | `false` | Legt fest, ob die Schaltfläche "Neues Werk hinzufügen" sichtbar ist. |
| `toggle` | boolean | `false` | Legt fest, ob der Bearbeitungsmodus aktiviert ist. |
| `editWork` | boolean | `false` | Legt fest, ob der Bearbeitungsmodus aktiviert ist. |
| `bearbeiten` | boolean | `false` | Legt fest, ob der Benutzer gerade sein Profil bearbeitet. |
## Funktionalität

- Die Komponente hört auf Fenstergrößenänderungen und legt die `open`-Eigenschaft basierend auf der Fensterbreite fest.
- Die Komponente enthält eine Schaltfläche, die sowohl das Bearbeiten des "Locators", als auch das Hinzufügen neuer Werke und die Veränderung von persönlicher Daten ermöglicht.
- Die Komponente zeigt den Namen des Benutzers an.
- Die Komponente enthält eine Schaltfläche, um neue Werke zum Profil hinzuzufügen.
- Die Komponente enthält eine Umschaltfläche für jedes Werk, um die Sichtbarkeit öffentlicher Werke zu aktivieren oder zu deaktivieren.
- ~~Die Komponente hört auf Zieh- und ablegende Ereignisse und aktualisiert die Reihenfolge der Werke.~~
- Die Komponente enthält ein Modal für das Hinzufügen neuer Werke zum Profil.
- Die Komponente enthält eine Abmelde-Schaltfläche.


## Style

Die Komponente verwendet CSS, um die Seitenleiste und ihre Elemente zu formatieren. Die Komponente verwendet Medienabfragen, um das Layout für kleinere Bildschirme anzupassen. Die Komponente enthält Übergänge für das Öffnen und Schließen der Seitenleiste.

