---
tags:
  - WYSIWYG
  - Richtext-Editor
---

https://tiptap.dev/

TipTap ist ein "Headless-Wrapper" für ProseMirror ein [[WYSIWYG]] RichTextEditor
In Portfolioland kommt TipTap beim Erstellen von Headlines und Paragraphen zum Einsatz. 
TipTap liefert uns HTML-Semantic:
```
<h2> Ich bin der Output für eine Headline2, den TipTap liefert.</h2>
<p> Ich bin der Output für einen Paragraphen, den TipTap liefert.</p>
```

Ein Beispiel wie wir TipTap einsetzten: 

```
<script>

/**

* @typedef {import('svelte').JSX.HTMLAttributes<HTMLElement>} HTMLAttributes

* @typedef {import('@tiptap/core').Editor} Editor

* @typedef {import('@tiptap/starter-kit').StarterKitOptions} StarterKitOptions

* @typedef {import('@tiptap/extension-bubble-menu').BubbleMenuOptions} BubbleMenuOptions

*/

  

import { onMount, onDestroy } from 'svelte';

import { Editor } from '@tiptap/core';

import StarterKit from '@tiptap/starter-kit';

import Paragraph from '@tiptap/starter-kit';

import BubbleMenu from '@tiptap/extension-bubble-menu';

  

/** @type {string} */

export let type = 'headlines';

let element;

let editor;

/** @type {string} */

export let content = '<h1>Write something...</h1>';

/** @type {function(string): void} */

export let updateContent;

export let editable = true;

  

onMount(() => {

editor = new Editor({

element: element,

extensions: [

StarterKit.configure({

heading: {

levels: [1, 2, 3, 4]

},

paragraph: {

HTMLAttributes: {

contenteditable: 'true',

'aria-multiline': 'true'

}

}

}),

BubbleMenu.configure({

element: document.querySelector('.menu')

})

],

  

content: content,

onUpdate: ({ editor }) => {

content = editor.getText();

},

onTransaction: () => {

// force re-render so `editor.isActive` works as expected

editor = editor;

content = editor.getText();

updateContent(content);

}

});

});

  

onDestroy(() => {

if (editor) {

editor.destroy();

}

});

</script>

  
  
  

<div class="editor" bind:this={element} class:headlines={editable} />

  

<style>

div {

width: 100%;

height: 100%;

}

.editor {

font-size: 1.8rem;

color: var(--text-light-100, #0c0c205e);

& :focus {

outline: var(--focus-outline);

}

}

  

.headlines {

font-size: 1.5rem;

font-weight: bold;

color: var(--text-light-100, #0c0c205e);

}

:global(.tiptap) {

width: 100%;

height: 100%;

background-color: var(--white);

&:focus {

outline: 0.1rem solid var(--tertiary, #32b3b3);

}

}

</style>
