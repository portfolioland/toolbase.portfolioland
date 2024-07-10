---
tags:
  - design
  - system
  - designsystem
  - button
---
# Button

![[Button LIGHT MODE.png]]
Buttons sind unverzichtbare Bestandteile des User Interfaces, da sie dem Benutzer klare Interaktionsmöglichkeiten bieten. Anders als Inputfelder, die Daten sammeln, initiieren Buttons unmittelbare Aktionen. Durch ihre visuelle Gestaltung und Beschriftung kommunizieren sie dem Nutzer, welche Funktion sie auslösen. Dadurch ermöglichen sie eine intuitive Navigation und Interaktion innerhalb einer Anwendung oder Webseite. Ob zum Bestätigen einer Auswahl, zum Absenden eines Formulars oder zum Starten einer bestimmten Funktion – Buttons sind das Bindeglied zwischen dem Benutzer und der gewünschten Aktion, und somit ein essenzieller Bestandteil jeder Benutzeroberfläche.

```
<button>Button Lable</button>

<style>

button {
	display: flex;
	justify-content: center;
	align-self: center;
	flex-direction: row;
	align-items: center;
	gap: 0.25rem;
	color: var(--text-light);
	cursor: pointer;
	padding: 0.3rem;
	border: 0.1rem solid var(--text-light)
	border-radius: 20rem;
	
	transition-property: all;
	transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
	transition-duration: 1000ms;
	&:hover {
		outline: 0.2rem solid var(--tertiary);
		transition-property: all;
		transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
		transition-duration: 1000ms;
		}

	&:focus {
		outline: 0.1rem solid var(--tertiary);
	}
}

</style>

```

#[[Atomic Design]]