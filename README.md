**Flexbox-Code**
 **Flexbox Demo – README**

Willkommen! 🎉 Dieses kleine Projekt begleitet mein YouTube-Erklärungsvideo zu CSS Flexbox.

Du darfst den Code gerne 1:1 kopieren, verändern und damit experimentieren
Werte anpassen, weitere Elemente hinzufügen, Layouts umbauen, alles erlaubt. Viel Spaß beim Ausprobieren!

---

## Inhalt

* [Ziel](#ziel)
* [Schnellstart](#schnellstart)
* [Der Demo-Code](#der-demo-code)
* [Was du ändern kannst](#was-du-ändern-kannst)
* [Typische Flexbox-Eigenschaften](#typische-flexbox-eigenschaften)
* [Tipps & Stolpersteine](#tipps--stolpersteine)
* [Lizenz / Nutzung](#lizenz--nutzung)

---

## Ziel

Die Demo zeigt, wie *Flexbox* Container (Eltern) und Items (Kinder) anordnet – inkl. `flex-direction`, `justify-content`, `align-items`, `gap`, `wrap`, `flex-grow` u.v.m. Das Setup ist bewusst minimal gehalten, damit du Änderungen schnell siehst.

---

## Schnellstart

1. **Datei anlegen:** Erstelle eine Datei z. B. `index.html`.
2. **Code reinkopieren:** Übernimm den kompletten Inhalt aus dem Abschnitt **Der Demo-Code**.
3. **Öffnen:** Doppelklick auf die Datei oder mit einem Live-Server (VS Code o. ä.) starten.
4. **Experimentieren:** Werte ändern, neue `.child`-DIVs hinzufügen, Media Queries anpassen.

> Tipp: Drücke die Fensterbreite zusammen, um das responsive Verhalten (Media Query + `flex-grow`) zu sehen.

---

## Der Demo-Code

> Vollständig lauffähiges Minimalbeispiel, das du frei verwenden und anpassen kannst.

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flex-Box</title>

    <style>
        body {
            background-color: rgb(0, 0, 22);
        }

        .child {
            background-color: azure;
            font-size: 32px;
            font-weight: bolder;
            width: 120px;
            height: 150px;
            text-align: center;
            align-content: center;
        }

        .parent {
            display: flex;
            gap: 20px;
            flex-direction: row;
            justify-content: space-evenly;
            flex-wrap: wrap;
            /* align-items: flex-end; */
            height:100%;
        }

        @media (max-width:740px) {
            .child {
                flex-grow: 1;
            }

            .parent {
                margin: 16px;
            }
        }
    </style>
</head>

<body style="height: 100vw;">
    <div class="parent">
        <div class="child div1">1</div>
        <div class="child div2">2</div>
        <div class="child div3">3</div>
        <div class="child div4">4</div>
    </div>
</body>

</html>
```

---

## Was du ändern kannst

* **Richtung:** `flex-direction: row | row-reverse | column | column-reverse`
* **Verteilung auf Hauptachse:** `justify-content: flex-start | center | flex-end | space-between | space-around | space-evenly`
* **Ausrichtung auf der Querachse:** `align-items: flex-start | center | flex-end | stretch | baseline`
* **Zeilenumbruch:** `flex-wrap: nowrap | wrap | wrap-reverse`
* **Abstände zwischen Items:** `gap: <Länge>` (z. B. `gap: 20px;`)
* **Wachstum/Schrumpfen einzelner Items:** `flex-grow`, `flex-shrink`, `flex-basis`
* **Individuelle Ausrichtung:** `align-self` für einzelne `.child`-Elemente
* **Responsiv:** Media Queries ändern (z. B. Breakpoints verschieben, `flex-grow`-Werte anpassen)

> Beispiel: Füge weitere Boxen hinzu, indem du einfach mehr `div.child` innerhalb von `.parent` einfügst.

```html
<div class="child">5</div>
<div class="child">6</div>
```

---

## Typische Flexbox-Eigenschaften

**Container (.parent):**

```css
.parent {
  display: flex;
  flex-direction: row;        /* Hauptachse: horizontal (Standard) */
  justify-content: center;    /* Verteilung entlang der Hauptachse */
  align-items: center;        /* Ausrichtung entlang der Querachse */
  gap: 20px;                  /* Abstand zwischen Items */
  flex-wrap: wrap;            /* Umbruch bei Platzmangel */
}
```

**Items (.child):**

```css
.child {
  flex-grow: 0;      /* 0 = wächst nicht automatisch */
  flex-shrink: 1;    /* 1 = darf bei Platzmangel schrumpfen */
  flex-basis: auto;  /* Basisgröße (kann auch px, %, etc. sein) */
  /* align-self: center;  // überschreibt align-items für dieses Item */
}
```

---

## Tipps & Stolpersteine

* **`row` vs. `column`:** Denk daran, dass sich *Haupt-* und *Querachse* je nach `flex-direction` drehen.
* **`space-around` vs. `space-evenly`:** `evenly` verteilt wirklich gleichmäßig – inkl. Außenabstand.
* **`flex-basis` vs. `width`:** In Flexbox hat `flex-basis` Vorrang vor `width`.
* **Viewport-Höhe:** Für volle Höhe ist oft `height: 100vh;` im `<body>`-Style sinnvoll (hier ist `100vw` gesetzt – einfach mal tauschen und den Unterschied testen).
* **`gap`-Support:** Ist in modernen Browsern gut unterstützt; bei sehr alten Versionen Fallbacks prüfen.

---

## Lizenz / Nutzung

**Mach damit, was du möchtest.** Kopieren, verändern, im Video/Unterricht verwenden alles ok.

Viel Spaß beim Bauen! 💪
