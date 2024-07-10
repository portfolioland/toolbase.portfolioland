Toggle-Schalter sind ein weiteres bedeutendes Element im User Interface. Sie bieten dem Nutzer die Möglichkeit, zwischen verschiedenen Zuständen ([[States]]) oder Optionen zu wechseln. Im Gegensatz zu Buttons, die eine einmalige Aktion auslösen, ermöglichen Toggle-Schalter eine dauerhafte oder vorübergehende Aktivierung oder Deaktivierung von Funktionen oder Einstellungen.

Ihr charakteristisches Design, oft in Form eines Schalters mit zwei Positionen, vermittelt dem Benutzer auf einen Blick den aktuellen Zustand und die verfügbaren Optionen. Durch einen einfachen Klick oder Touch können Benutzer den Schalter umlegen und somit den gewünschten Zustand wählen.

Toggle-Schalter werden im [[0001_Designsystem "Portfolioland"|Portfolioland]], unter anderem, im "privaten" Bereich für die Einstellungen von öffentlich und privat genutzt.

![[toggles.png]]
# Code
## Exportierte Werte
### `label`

- Typ: String
- Standardwert: `'test'`
- Beschreibung: Die Beschriftung oder der Text, der in einem UI-Element angezeigt wird.

### `toggled`

- Typ: Boolean
- Standardwert: `false`
- Beschreibung: Der Zustand des Schalters oder der Checkbox. `true`, wenn der Schalter aktiviert ist, `false`, wenn er deaktiviert ist.

### `labelProps`

- Typ: Objekt
- Standardwert: `{}`
- Beschreibung: Ein Objekt, das zusätzliche Eigenschaften oder Konfigurationen für die Beschriftung enthält. Kann für die Anpassung von Stilen oder anderen Optionen verwendet werden.

### `switchColor`

- Typ: String (CSS-Farbwert)
- Standardwert: `'var(--white)'`
- Beschreibung: Die Farbe des Schalters im Standardzustand (deaktiviert).

### `toggledColor`

- Typ: String (CSS-Farbwert)
- Standardwert: `'var(--tertiary)'`
- Beschreibung: Die Farbe des Schalters im aktivierten Zustand.

### `togglePrivate`

- Typ: String (CSS-Farbwert)
- Standardwert: `'var(--secondary)'`
- Beschreibung: Die Farbe des privaten Bereichs des Schalters. Dieser Bereich kann z. B. verwendet werden, um den privaten Modus in einer Anwendung zu kennzeichnen.
### `untoggledColor`

- Typ: String (CSS-Farbwert)
- Standardwert: `'var(--bg-bright)'`
- Beschreibung: Die Farbe des Schalters im Standardzustand (deaktiviert). Wird verwendet, wenn der `switchColor` nicht angegeben ist.
### `disabled`

- Typ: Boolean
- Standardwert: `false`
- Beschreibung: Gibt an, ob das UI-Element deaktiviert ist oder nicht.
### `hideLabel`

- Typ: Boolean
- Standardwert: `true`
- Beschreibung: Gibt an, ob die Beschriftung des UI-Elements ausgeblendet werden soll oder nicht.
### `dispatcherON`
- Typ: Boolean
- Standardwert: `true`
- Beschreibung: Ein Schalter, der angibt, ob ein Dispatcher aktiviert ist oder nicht. Ein Dispatcher kann verwendet werden, um Ereignisse oder Aktionen zu steuern.


```
<script>

import { ToggleCore } from 'svelte-toggle';

export let label = 'test';
export let toggled = false;
export let labelProps = {};
export let switchColor = 'var(--white)';
export let toggledColor = 'var(--tertiary)';
export let togglePrivate = 'var(--secondary';
export let untoggledColor = 'var(--bg-bright)';
export let disabled = false;
export let hideLabel = true;
export let dispatcherON = true;

import { createEventDispatcher } from 'svelte'
const dispatch = createEventDispatcher();

$: dispatch('toggle', toggled);

</script>

  

{#if dispatcherON}

<ToggleCore bind:toggled let:label={labelProps} let:button>

<!-- svelte-ignore a11y-label-has-associated-control -->

<label {...labelProps} class:hideLabel>{label}</label>

<button

{...$$restProps}

{...button}

style:color={toggled ? switchColor : togglePrivate}

style:background-color={untoggledColor}

{disabled}

on:click

on:click={() => (toggled = !toggled)}

on:focus

on:blur

/>

</ToggleCore>

{:else}

<ToggleCore bind:toggled let:label={labelProps} let:button>

<!-- svelte-ignore a11y-label-has-associated-control -->

<div style="gap: 0.5rem">

<label {...labelProps} class:hideLabel>{label}</label>

<button

{...$$restProps}

{...button}

style:color={switchColor}

style:background-color={toggled ? toggledColor : untoggledColor}

{disabled}

on:click|preventDefault={() => (toggled = !toggled)}

on:focus

on:blur

on:keypress|preventDefault

/>

</div>

</ToggleCore>

{/if}

  

<style>


.hideLabel {

position: absolute;

height: 1px;

width: 1px;

overflow: hidden;

clip: rect(1px 1px 1px 1px);

clip: rect(1px, 1px, 1px, 1px);

white-space: nowrap;

}

  

button {

position: relative;

padding: 0 0.25rem;

border: 0;

border-radius: 1rem;

height: 1.35rem;

width: 2.5rem;

font: inherit;

color: inherit;

line-height: inherit;

border: var(--button-border, 0.1rem solid var(--text-light, #0c0c20));

//background-color: var(--button-background, var(--bg-bright, #fff));

transition: background-color 0.2s ease-out;

}

  

button:not([disabled]) {

cursor: pointer;

}

  

button[disabled] {

cursor: not-allowed;

opacity: 0.6;

}

  

button:before {

position: absolute;

content: '';

top: 0;

bottom: 0;

left: 0.125rem;

margin: auto;

height: 1rem;

width: 1rem;

text-align: center;

border-radius: 50%;

background-color: currentColor;

transition: transform 150ms ease-out;

outline: var(--button-border, 0.1rem solid var(--text-light, #0c0c20));

}

  

button[aria-checked='true']:before {

transform: translateX(1.1rem);

}

  

button.small {

height: 1rem;

width: 1.75rem;

}

  

button.small:before {

height: 0.75rem;

width: 0.75rem;

}

  

button.small[aria-checked='true']:before {

transform: translateX(0.75rem);

}

  

div {

display: flex;

align-items: center;

}

  

span {

margin-left: 0.5rem;

}

</style>

```

## Dependencies
Svelte-Toggle ist ein Svelte-Component das Accessibility-features von Haus aus mitbringt.
### Install
```
# yarn
yarn add -D svelte-toggle

# npm
npm i -D svelte-toggle

# pnpm
pnpm i -D svelte-toggle
```


https://github.com/metonym/svelte-toggle

#[[Atomic Design]]