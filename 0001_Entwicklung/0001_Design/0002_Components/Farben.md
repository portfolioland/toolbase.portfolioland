![[Farben.png]]
# Bedeutung des Farbcodes 
Im Designsystem spielen Farben eine entscheidende Rolle, da sie verschiedene Aufgaben erfüllen. Die Hauptfarbe, die durch den Hex-Code #A32EFF repräsentiert wird, dient als öffentliche Farbe und wird vor allem für die Repräsentation des "öffentlichen Status" in  Elemente verwendet. Die sekundäre Farbe, definiert als #FFA92C, fungiert als private Farbe und findet bei Elementen Einsatz, die den Status "Privat" repräsentieren . 
Die elementare Funktion der Farbgebung besteht darin, die Zustände der Seite zu unterscheiden. Hier kommt die tertiäre Farbe ins Spiel, die durch den Code #BFFDF dargestellt wird und als Akzentfarbe fungiert. Sie zeigt dem Benutzer an, welche Elemente momentan im Focus sind.
Die neutrale Farbe, codiert als #0C0C20, wird hingegen hauptsächlich für den Text verwendet, um eine gute Lesbarkeit zu gewährleisten. 
Für Fehlermeldungen steht die Farbe mit dem Code #E31C3D bereit, um diese deutlich hervorzuheben. Insgesamt tragen diese Farbcodes maßgeblich zur visuellen Kohärenz und Benutzerfreundlichkeit des Designs bei.
![[States]]
# Codeeinbettung
Der folgende Codeblock präsentiert die Vorlagen in der app.css-Datei für die verschiedenen Farben. Diese können dann im Code mithilfe von var(--example) verwendet werden. Beachten Sie jedoch, dass die app.css-Datei über einen Style-Link eingebunden sein muss.

```
// app.css
:root{
--accent-color-dark: rgba(75, 223, 255, 0.4);

//Background-Colors:

--bg-bright: rgb(241, 240, 240);
--bg-dark: rgb(0 0 0);
--bg-light: rgb(241, 240, 240);


--grey: #ccc;
//Text-Colors
--text-light: #0c0c20;
--text-light-100: #0c0c20b1;

--white: #FFF;
--primary: #A32EFF;
--secondary: #FFA92C;
--tertiary: #4bffdf;
}
```



#[[Atomic Design]]