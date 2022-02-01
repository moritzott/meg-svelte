# MEG - Mail-Entwurfs-Generator

Dies hier is die *Svelte*-Version des MEGs (Mail-Entwurfs-Genertor).

## Beschreibung

Manchmal muss man Mails über das Smartphone schreiben.
Gegenüber einem PC hat dabei man den Nachteil, dass man sich öfter
vertippt und das Schreiben auf dem kleinen Touchscreen
unangenehm ist.
Der *MEG* ist ein Mail-Entwurfs-Generator, der 
gewöhnliche Begrüßungs- und Schlussfloskeln setzt, Absendername und Empfänger aufnimmt und die
Mail entsprechend mit Abständen automatisiert formatiert.
Man schreibt auf diese Weise hübschere und korrektere Mails
in schnellerer Geschwindigkeit. Man muss sich auch weniger
Gedanken um Schreibfehler machen.

## Demo
* Live-Demo: [MEG](https://moritzott.github.io/meg-svelte/)

## Zusatzinfo
Standardmäßig werden die komplilierten Dateien bei Svelte in
den *public*-Ordner geschrieben. GitHub Pages schaut jedoch entweder
im Wurzelverzeichnis (root) oder im Ordner /docs nach den Dateien. Damit die Webvorschau
funktioniert, wurde für dieses Repositorium der public-Ordner in den 
/doc-Ordner kopiert (die kompilierten Dateien sind also sowohl im
*public*-Ordner für Svelte wie im *docs*-Ordner für GitHub pages).
Kurz: Das Verzeichnis /docs existiert nur für GitHub Pages! Für
die Svelte-Anwendung spielt es keine Rolle.

## Weitere Eckdaten
* Mobile-First-Ansatz: Auf dem Handy passieren beim
Schreiben einer Mail die meisten Tippfehler.
Deswegen sollte die Anwendung auf mobile Nutzung 
mit einem Smartphone
ausgerichtet sein.

## Aktuelle Version
* 2.0.0

## (Zukünftige) Versionen und gesteckte Ziele


* 2.1.0
	* Erweiterung der Empfänger und Begrüßung
		* Vereine (*des* Ruderverein**s**), Ämter (*des*
		Finanzamt**es**)
		
* 2.2.0
	* optional: Vorauswahl an Texten

## Weitere Ideen
* Absendeadresse als Signatur unten einfügen?
* Speichern der Absendeadresse u. ähnlicher Angaben und vorausfüllen?
* separate Betreffzeile?
* Formatierung einer Nachricht als HTML-Nachricht?
