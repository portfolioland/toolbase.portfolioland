![[Pasted image 20240704131531.png]]
Die Komponente `PreviewWork` zeigt ein Preview eines Werks der Kunst an. Sie akzeptiert das `work`-Objekt als Prop, das Informationen über das Werk enthält.

Verwendung findet diese Komponente in der Applikation überall dort, wo ein Werk referenziert werden soll. Z.b. auf `/` , `/tags` oder `/tags/[tag]`

Diese Komponente findet hauptsächlich in [[Frontpage (öffentlich)]] und [[Tags]] anwendung.
## Props

Die Komponente akzeptiert das `work`-Objekt als Prop. Das `work`-Objekt enthält Informationen über das Werk der Kunst, z.B. den Titel, den Künstler, das Jahr der Erstellung, das Bild und die Tags.
### WorkObject

Das `WorkObject` ist ein Objekt, das die folgenden Eigenschaften enthält:

- `title` (string): Der Titel des Werkes.
- `expand` (Object): Ein Objekt, das zusätzliche Informationen über das Werk enthält.
  - `artists` (Object[]): Ein Array von Objekten, die Informationen über die Künstler enthalten.
    - `name` (string): Der Name des Künstlers.
  - `year` (string): Das Jahr, in dem das Werk erstellt wurde.
- `image` (Object): Ein Objekt, das Informationen über das Bild enthält.
  - `id` (string): Die ID des Bildes.
  - `content` (string): Der Inhalt des Bildes.
- `expand.tag` (Object[]): Ein Array von Objekten, die Informationen über die Tags enthalten.
  - `title` (string): Der Titel des Tags.

```JSON
work= {
  "expand": {
    "artists": [
      {
        "name": "BTestProfil"
      }
    ],
    "tag": [
      {
        "title": "Skulptur"
      }
    ]
  },
  "id": "cposrsc8dmugl4z",
  "jahr": 2014,
  "public": true,
  "tag": [
    "n549go32izloduw"
  ],
  "title": "title",
  "image": {
    "id": "ha399hbkfnoz0n3",
    "collectionId": "imagte5o4n6kp1p",
    "content": "test.JPG"
  }
}
```
## Styling
Die Komponente verwendet CSS, um ihre Darstellung anzupassen. Die folgenden Styles werden verwendet:
- `article`: Der Hauptcontainer für das Werk der Kunst. Er hat eine Breite und Höhe von 90% und wird als Flex-Container mit einer Spaltenrichtung und einem Abstand von 0,5rem angezeigt.
- `section`: Ein Flex-Container mit einer Spaltenrichtung und einem Abstand von 0,25rem.
- `a`: Ein Link, ohne Unterstreichung und mit einer hellgrauen Farbe. Beim Hover wird eine Schatteneffekt hinzugefügt.
- `.title`: Der Titel des Werkes wird mit einer Schriftgröße von 1,5rem angezeigt.
- `.name`: Der Name des Künstlers wird angezeigt.
- `.tags`: Ein Flex-Container mit einer Zeilenrichtung und einem Abstand von 0,25rem. Die Tags werden in mehreren Zeilen angeordnet und mit einem Rand oben angezeigt.
- `.jahr`: Das Jahr, in dem das Werk erstellt wurde, wird in einer kursiven Schrift angezeigt.
- `.image`: Ein Container mit einem Überlauf und einem Flex-Container mit dem Zentrierten Inhalt.
- `.image img`: Das Bild wird mit einer Breite und Höhe von 100% und einem Objektanpassungsmodus von "cover" angezeigt.
### Exemplarische semantische Darstellung 

```js
<article>
	<section class="title">
		<a href="/artists/name/title">{title}</a>
	</section>
	<section class="name">

		<a href="/artists/name">{name}</a>
	</section>
	<section class="jahr">{Jahr}</section>
	<section class="image">
		{#if image}
			<a href="/artists/name/title">
				<img/>
			</a>
		{:else}
			<a href="/artists/name/title">
				<img />
			</a>
		{/if}
	</section>
	<section class="tags">
    {#each tags as tag}
		<TagDisplay tag={tag.title} />
    {/each}
	</section>
</article>
```

### CSS
```CSS
	article {
		width: 90%;
		height: 90%;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		padding: 0.5rem;
		border: solid 0.1rem var(--text-light);

		grid-column: span 2;
	}
	section {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
	}
	a {
		text-decoration: none;
		color: var(--text-light);
		&:hover {
			text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
			transition-property: all;
			transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
			transition-duration: 1000ms;
		}
	}
	.title {
		font-size: 1.5rem;
	}
	.tags {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		gap: 0.25rem;
		border-top: solid 0.1rem var(--text-light);

		padding-top: 0.25rem;
	}
	.jahr {
		font-style: italic;
	}

	.image {
		overflow: hidden;
		display: flex;
		justify-content: center;

		& img {
			width: 100%;
			height: 100%;
			object-fit: cover;
		}
	}
```

