## Sass Einführung

### Was ist Sass?

- Syntactically Awesome StyleSheets

- Ein CSS-Präprozessor / eine Erweiterung (fügt CSS mehr Effizienz zu)

- Kann nicht direkt vom Browser gelesen werden.

- Es muss in normales CSS umgewandelt werden.

<br>

### Warum Sass?

Mit Sass können wir Funktionen nutzen, die sonst in normalem CSS nicht verfügbar sind

### Einige Eigenschaften von Sass

<br>

1. Der Unterschied zwischen SASS, SCSS und CSS-Syntax

#### Normalen CSS

```css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```

#### SCSS emöglicht u.a Variabeln unf nesting!

```scss
// SCSS SYNTAX
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

#### SASS

- SASS syntax basiert sich auf "Indentation"
- Man benüzt kein geschweifte Klammern!
- Ein bisschen schwer zu verstehen besonders am Anfang!
- nicht empfohlen für Anfänger!

```scss
// SASS SYNTAX
$font-stack: Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color
```

<br>

2. Variablen

```scss
// Variabeln nennen
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  // Variabeln benützen
  font: 100% $font-stack;
  color: $primary-color;
}
```

3. Verschachtelung

```scss
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

```scss
// SCSS SYNTAX
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li {
    display: inline-block;
  }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

4.  Partials(\_partial.scss-Dateien)
5.  Module

    - Partials haben ein "Underscore" zeichen `_` vor ihre Namen

    Zum beispiel in `_base.scss` datei kann man diese code schreiben

```scss
// _base.scss
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

Und dann in die haupt `style.scss` datei als `Module` importieren (`@import "base";`)

```scss
// styles.scss
@use "base";

.inverse {
  background-color: base.$primary-color;
  color: white;
}
```

- Module hilft uns unser code in Kleine Stückchen zu teilen.
- so wird unser Code besser zu bearbeiten!

6. Mixins

- Mixin erstellt Gruppen von wiederverwendbaren CSS-Deklarationen.
- Es hilft, unsere Sass sehr "DRY-(Don't Repeat Yourself)" zu halten.

```scss
// CSS hat viele Wiederholungen... nicht DRY!
.info {
  background: DarkGray;
  box-shadow: 0 0 1px rgba(169, 169, 169, 0.25);
  color: #fff;
}

.alert {
  // fast gleich wie oben
  background: DarkRed;
  box-shadow: 0 0 1px rgba(139, 0, 0, 0.25);
  color: #fff;
}

.success {
  // fast gleich wie oben
  background: DarkGreen;
  box-shadow: 0 0 1px rgba(0, 100, 0, 0.25);
  color: #fff;
}

// Zu viele Code Wiederholung!!!!
```

aber mit SCSS...

```scss
// mixin erstellen
@mixin theme($theme: DarkGray) {
  background: $theme;
  box-shadow: 0 0 1px rgba($theme, 0.25);
  color: #fff;
}

.info {
  // hier verwenden
  @include theme;
}
.alert {
  // hier modifizeiren
  @include theme($theme: DarkRed);
}
.success {
  // hier modifizeiren
  @include theme($theme: DarkGreen);
}
```

7. Erweitern/Verererbung (Extend/Inheritance)

---

# [Nutze diesem Link zum Sass Docs](https://sass-lang.com/guide)

---

## TIPPS?

- Schreibe wichtigen Dinge auf! (code snippets, Schritte u.s.w)
- Versuch so weit wie möglich in Gruppen zu Arbeiten!
- `"Strg + J" ` Testatur Abkürzung öffnet und schließt VS Code Terminal....
