![[toggles.png]]
```
<script>
  import Toggle from "svelte-toggle";

  let toggled = false;
</script>

<Toggle bind:toggled />

<button on:click={() => (toggled = !toggled)}>
  {toggled ? "Turn off" : "Turn on"}
</button>
```

Svelte Toggle ist eine Component-Library, die es uns ermöglicht einen Toggle Schlater in der Software zu implementieren. Svelte-Togggle lässt sich dabei mit recht CSS frei visuell gestalten.

https://metonym.github.io/svelte-toggle/