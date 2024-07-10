![[LOGIN 1 DESKTOP.png]]
![[LOGIN STUDENT.png]]
# Login
Das Login für [[0001_Designsystem "Portfolioland"|Portfolioland]] ist über Email und Passwort möglich. Der visuellen Ästhetik folgend haben die Eingabeformularelemente abgerundete Kanten und nutzen die vorgegebenen Komponenten aus [[Buttons]] und [[Forms]]. Sollte etwas bei der Eingabe/Absenden nicht korrekt sein, wird dem Benutzer dies durch ein Element aufgezeigt, das ein- und ausfadet.

Dieses Element ist in den [[Farben]] für den Fehlerzustand gehalten und beinhaltet zusätzlich Informationen über den potenziellen Fehler.

![[LOGIN 1 DESKTOP Error.png]]
# Feature 

- [-] Funktion Login
- [-] Funktion Rückmeldung
- [ ] SAML-Integration

TODO: [[SAML-Protokol|SAML]]- Integration.
Das Tool soll nach Möglichkeit einen möglichst barrierearmen Einwahlprozess bieten. Hierzu soll eine Integration der SAML/Shibboleth Authentifizierung der Universität Kassel angestrebt werden. 

# Code 
## Clientseitiger Code (Frontend)

Hier ist ein Beispielcode, der die Implementierung des Designs im Framework [[0002_Tools/Tools/Svelte/Sveltekit]] zeigt, wobei besonders die Verwendung der {#if}-Schleifen zur Darstellung der rückläufigen Formwerte zu beachten ist:
```
<script>

import LoginButton from '$lib/components/Buttons/loginButton.svelte';

import { PUBLIC_TEST_ACCOUNT, PUBLIC_TEST_ACCOUNT_PW } from '$env/static/public';

  

export let form;

let email = PUBLIC_TEST_ACCOUNT;

//TODO: Before release delete value

let password = PUBLIC_TEST_ACCOUNT_PW;

//TODO: Before release delete value

let visible = false;

</script>

  

<div class="loginwrapper">

<form method="POST" action="/login">

<input id="email" name="email" type="text" placeholder="Enter your e-mail" value={form?.email ?? email}/>

<input id="password" name="password" type="password" placeholder="Enter your password" bind:value={password} />

<LoginButton />
  
{#if form?.missing}<p class="error">Please enter USERNAME</p>{/if}
{#if form?.incorrect}<p class="error">Please enter PASSWORD</p>{/if}
{#if form?.invalid}<p class="error">Invalid PASSWORD</p>{/if}

</form>

</div>

  

<style>

.loginwrapper {

width: 100dvw;

width: 100vw;

height: 100%;

display: flex;

justify-content: center;

margin-top: 30vh;

}

  

form {

display: flex;

align-items: center;

justify-content: center;

flex-direction: column;

margin-top: 10px;

}

p {

display: flex;

align-items: center;

justify-content: center;

flex-direction: column;

margin-top: 10px;

margin: 0.5%;

padding: 10px 15px;

width: max-content;

  

border: 1px solid #000000;

border-radius: 200px;

color: #000000;

margin-top: 10px;

}

.error {

margin-top: 5rem;

background-color: rgba(219, 69, 69, 0.821);

color: #ffffff;

transition: 2s all;

opacity: 0.5;

transition: opacity 10s;

box-shadow: 2px 2px 4px #00000041;

}

.error {

-webkit-animation: 4s 0s normal forwards 1 fadeout;

animation: 4s 0s normal forwards 1 fadeout;

}

@keyframes fadeout {

0% {

opacity: 1;

}

66% {

opacity: 0;

}

100% {

opacity: 0;

}

}

  

@-webkit-keyframes fadeout {

0% {

opacity: 1;

}

66% {

opacity: 0;

}

100% {

opacity: 0;

}

}

  

input {

margin: 0.7rem;

padding: 10px 15px;

background: #ffffff;

border: 0.1rem solid #000000;

border-radius: 200px;

color: #000000;

}

input:focus {

opacity: 1;

transition: 0.4s;

box-shadow: 2px 2px 4px #00000041;

}

  

button {

margin: 0.5%;

padding: 10px 15px;

background: #ffffff;

border: 0.1rem solid #000000;

border-radius: 200px;

color: #000000;

margin-top: 10px;

}

button:hover {

background: #94db93;

opacity: 1;

transition: 0.4s;

box-shadow: 2px 2px 4px #00000041;

}

button:focus {

background: #94db93;

opacity: 1;

transition: 0.4s;

box-shadow: 2px 2px 4px #00000041;

}

</style>
```

In diesem Beispiel wird das Formular mit den Eingabefeldern für E-Mail und Passwort dargestellt. Beim Absenden des Formulars wird überprüft, ob beide Felder ausgefüllt sind. Wenn nicht, wird eine Fehlermeldung angezeigt. Beachten Sie die Verwendung der {#if}-Schleife, um die Fehlermeldung nur dann anzuzeigen, wenn ein Fehler auftritt

## Serverseitiger Code
```
import { error, fail, redirect } from '@sveltejs/kit';

export const actions = {

/**

* The default action for the login page.

*

* @async

* @param {Object} context - The context object.

* @param {Request} context.request - The request object.

* @param {Object} context.locals - The locals object.

* @throws {Error} If an error occurs during the action.

* @returns {Promise} A promise that resolves to a redirect or failure response.

*/

default: async ({ request, locals }) => {

const body = Object.fromEntries(await request.formData());

let email = body.email;

  

try {

await locals.pb.collection('users').authWithPassword(body.email, body.password);

  

} catch (err) {

if (!body.email) {

return fail(400, { email, missing: true });

}

  

if (!body.password) {

return fail(400, { email, incorrect: true });

}

  

if (!locals.pb?.authStore?.model?.verified) {

return fail(400, { email, invalid: true });

}

  

console.log('Error: ', err);

throw error(500, 'Something went wrong logging in');

}

  

throw redirect(303, `/profil/${locals.pb.authStore.model.name}`);

},

};
```

