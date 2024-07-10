# App-Struktur von [[Portfolioland]]

# Terms
Terms zeigt die Nutzungsbestimmungen für [[Portfolioland]] an.
- [x] Terms (Code of Conduct)
- [x] Konditionales Blocken der Nutzung bis akzeptiert.
## Auth
Authentikation ist ein Grundbaustein für die Arbeitsweise von [[Portfolioland]]. Hier wird sichergestellt, dass die User nur Zugang zu ihren eigenen Daten haben und nur diese verändern/bearbeiten können. 
### Frontend
- [x] Login (E-mail, Password)
- [x] Logout
- [x] Register
- [ ] [[SAML-Protokol|SAML]]-Auth (nice to have)
### Profil (Protected Place)
Im Profil von [[0001_Designsystem "Portfolioland"|Portfolioland]] können die authentifizierten User ihr Profil anpassen, Arbeiten erstellen und den Status ihrer Arbeit 

- [ ] Einstellungen
	- [x] Name
	- [x] Pronomen
	- [x] Socials
	- [ ] Klasse

- [ ] Create New Work Entry Modal
	- [x] Title
	- [x]  Description
	- [x] Tag
	- [x] Date
	- [x] First Picture
	- [ ] Template Struktur(Nice to have)
	- [x] Public State
	- [x] Submit
  
- [x] Drag and Drop - Builder
	- [x] Position of Dragger and Delete
	
- [x] Picture
- [x] Headline
- [x] Text
- [ ] embed (nice to have)
	- [ ] Linkchecker
	- [ ] Videoembeds (Youtube, Vimeo,...)
	

- [x] List of Works
	- [x] Public State
	- [x] DeleteButton
	- [ ] Drag n Drop - Sortierung der Einträge

# Öffentlicher Bereich
Der Öffentliche Bereich zeigt die Öffentlich gestellten Arbeiten und Profile an. Des Weiteren bietet der Bereich eine Suchfunktion, sowie eine Landing-Page mit einer Auswahl an Arbeiten.
- [x] Artists Page
	- [x] Profil Page
	- [x] Work Page
- [x] Search
- [x] Frontpage
- [x] Tags
- [ ] Meldebutton und Meldeformular (nice to have)
## Admin-Page (nice to have)
Die Admin-Page soll der Rolle des Admin die Möglichkeit geben einfach auf Meldungen zu reagieren. Sperrungen, ebenso wie Löschungen, benötigen allerdings einer Erklärung.
- [ ] Inbox Meldungen
	- [ ] E-mail-Notification
- [ ] Sperrmöglichkeit mit Begründung warum gesperrt.
	- [ ] User
	- [ ] Content
- [ ] Löschfunktion
	- [ ] Content
	- [ ] Tags

