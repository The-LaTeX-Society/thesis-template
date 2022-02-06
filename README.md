# Thesis Template

Vorlage für wissenschaftliche Arbeiten – insbesondere Bachelor- und Masterarbeiten – an der Hochschule Furtwangen.

Je nach Kenntnisstand im Bereich LaTeX kann diese Vorlage sehr kompliziert wirken. Durch logische Aufteilung in viele kleine Dateien soll für eine bessere Übersicht über das Projekt gesorgt werden. Auch können sich so Personen mit weniger LaTeX-Erfahrung vorerst auf wenige Dateien beschränken und voreingestellte Formatierungen ignorieren.

[Demo](https://github.com/The-LaTeX-Society/thesis-template/releases/latest/download/Thesis.pdf)

## Dateistruktur

Die nachfolgende Liste führt alle Ordner und Dateien auf, welche vom Ersteller der Thesis bearbeitet werden können / sollen.

- abstract/
  - Abstract_English.tex
  - Abstract_German.tex
- appendix/
  - ...
- content/
  - ...
- images/
  - hfu_logo.eps
  - ...
- acronyms.tex
- appendix.tex
- bibliography.bib
- content.tex
- foreword.tex
- format.tex
- metadata.tex
- style.tex
- Thesis.tex

### Abstract

Das Abstract wird allein durch die zwei Dateien im Ordner abstract/ editiert. In diesen wird jeweils der Text in eckigen Klammern durch den entsprechenden Abstract-Text auf Englisch oder Deutsch ersetzt.

### Anhang

Ein Anhangskapitel wird, wie in den Beispieldateien, im Order appendix/ erstellt. Um dieses Kapitel in den Anhang der Thesis aufzunehmen, muss in der Datei appendix.tex innerhalb der appendices-Umgebung folgender Befehl verwendet werden. (Siehe Beispielanhang.)

```LaTeX
\include{appendix/<Name der Datei>}
```

Soll in einem Anhangskapitel nur je eine Abbildung, Tabelle oder ein Quelltextbeispiel verwendet werden, können dem Kapitel entsprechend folgende Befehle vorangestellt werden. Diese unterdrücken für dieses Kapitel die Nummerierung des entsprechenden Elements. So kann, wenn z. B. nur eine Abbildung verwendet wird, diese als Abbildung A (statt Abbildung A1) betitelt werden.

```LaTeX
\appendixsinglefig % Nur eine Abbildung
\appendixsingletab % Nur eine Tabelle
\appendixsinglelst % Nur ein Quelltextbeispiel

\chapter{...}
```

In der Datei appendix.tex finden sich zusätzlich die Optionen, Abschnitte und Unterabschnitte innerhalb von Anhängen aus dem Inhaltsverzeichnis, sowie Abbildungen, Tabellen und Quelltextbeispiele aus ihren entsprechenden Verzeichnissen zu entfernen. Diese Optionen können separat durch ein- / auskommentieren verwendet oder ignoriert werden.

### Kapitel

Kapitel der Thesis werden je als Datei in dem Ordner content/ angelegt. Eingebunden werden Kapitel über die Datei content.tex mit folgendem Befehl.

```LaTeX
\include{content/<Name der Datei>}
```

### Bilder

Bilder, welche für die Thesis verwendet werden, sollten unter dem Pfad images/ abgelegt werden. Bilder werden unter Verwendung des zu der Datei Thesis.tex relativen Pfades eingebunden.

```LaTeX
\includegraphics{images/example-image.png}
```

Die in der Titelseite verwendete Datei hfu_logo.eps wird nicht mit dieser Vorlage mitgeliefert. Sie kann über das Markenportal der HFU (FELIX: https://marke.hs-furtwangen.de/) bezogen werden und muss im Ordner images/ abgelegt werden.

### Zu bearbeitende Dateien

#### acronyms.tex

Hier können in der Thesis verwendete Akromyne festgelegt werden.

```LaTeX
% Definition
\acro{<Kurzform>}{<Bedeutung des Akronyms>}

% Verwendung
\ac{<Kurzform>}
```

Sollte die gewünschte Kurzform von dem verwendeten Code-Kürzel abweichen, kann man Akronyme auch genauer definieren.

```LaTeX
% Definition
\acro{abc}[ABC]{Alphabet}
\acroplural{abc}[ABCs]{Alphabete}

% Verwendung
\ac{abc}
\acp{abc} % Plural
```

Sollte der Kasus des Akronyms nicht in den ersten Satz passen, kann das Ausschreiben der langen Form des Akronyms blockiert werden und das Wort entsprechend selbst geschrieben werden.

```LaTeX
Alphabeten (\acspl{abc})
```

#### bibliography.bib

Hier werden verwendete Quellen abgelegt. Entsprechender Code kann von den meisten gängigen Portalen direkt übernommen werden. Der verwendete Zitierstil ist APA. Dies kann bei Bedarf in der Datei format.tex angepasst werden. Generell wird Groß- und Kleinschreibung in Titeln und Buchtiteln von diesem Stil entfernt. Da dies in deutschen Arbeiten unüblich ist, kann durch Verwendung doppelter geschweifter Klammern in entsprechenden Feldern ein Eingriff verhindert werden.

```BibTeX
@book{mustermann20,
  author = {Max Mustermann},
  title = {{Ein Buch mit Groß- und Kleinschreibung}},
  year = {2020}
}
```

#### foreword.tex

Sollte ein Vorwort gewünscht sein, kann dieses hier eingefügt werden. Der Text in eckigen Klammern muss hierbei ersetzt werden, während die restlichen Zeilen unberührt bleiben sollten.

Ist ein Vorwort nicht gewünscht, kann es in der Datei Thesis.tex auskommentiert werden.

#### format.tex

Die Datei format.tex bietet eine vorgefertigte Formatierung des Dokuments entsprechend der HFU-Vorgabe. Hier werden alle nicht exklusiv auf den Style bezogenen Pakete eingebunden und konfiguriert. Es sind bereits diverse Einstellungen vorgenommen, die das Gesamtbild der Arbeit verbessern sollen.

Es können bei Bedarf Anpassungen vorgenommen werden, dies ist jedoch in den meisten Fällen nicht nötig.

Am Ende findet sich ein Abschnitt für weitere Pakete, sollten spezifische Pakete benötigt werden. Außerdem können die in diesem Abschnitt eingebundenen Pakete und definierten Befehle gelöscht werden, sollten sie unerwünscht sein.

Kann in Sonderfällen oder zum Einbinden weiterer Pakete bearbeitet werden. So kann z. B. im Paket footmisc ausgestellt werden, dass Fußnotenzählung auf jeder Seite neu beginnt oder der verwendete Zitierstil geändert werden. Hier können auch definierte Abstände (z. B. bei der Nummerierung von Abbildungen, Tabellen oder Fußnoten) geändert werden. Der Nutzen einzelner Pakete und deren Konfiguration ist innerhalb der Datei durch Kommentare genauer erklärt.

(Für die meisten Konfigurationen ist die style.tex Datei zu bevorzugen.)

#### metadata.tex

Hier werden die entsprechenden Metadaten eingefügt, welche über die Vorlage verwendet werden. Sie können auch jederzeit mit ihrem entsprechenden Befehl (bspw. ```\metadataTitle```) im Text verwendet werden.

#### style.tex

Hier können stilistische Änderungen vorgenommen werden, ohne das Backend der Thesis bearbeiten zu müssen. Es stehen unter anderem Optionen zu verschiedenen Hervorhebungen, Schriftarten und der Darstellung von Tabellen und Quelltext zur Verfügung.

Außerdem wird hier die Silbentrennung unbekannter Wörter definiert.

Es ist empfohlen, hier definierte Hervorhebungen (z. B. ```\code{...}```) zu verwenden oder neue zu definieren, anstatt im Text explizite Formatierung (z. B. ```\texttt{...}```) zu verwenden.

#### Thesis.tex

Hier wird die Struktur der Thesis festgelegt. In dieser Datei sollten keine direkten Änderungen vorgenommen werden. Es können jedoch gewisse Dinge wie ein Vorwort, Verzeichnisse, römische Seitenzählung oder ein Anhang durch ein- / auskommentieren eingebunden bzw. entfernt werden.

Dies ist die zu kompilierende Datei.

### Nicht zu bearbeitende Dateien

Die folgenden Dateien müssen nur in Ausnahmefällen bearbeitet werden. Hier werden diverse Formatierungen, Seitenlayouts und Standardtexte festgelegt.

- abstract.tex
- statutory_declaration.tex
- title.tex

#### abstract.tex

Hier werden die Dateien des Abstract-Verzeichnisses eingebunden.

Muss nicht bearbeitet werden.

#### statutory_declaration.tex

Hier ist der HFU-Standardtext der eidesstattlichen Erklärung definiert. Für Namen, Datum und Ort wird sich bei den Metadaten bedient.

Muss nicht bearbeitet werden.

#### title.tex

Hier ist das Layout der Titelseite definiert. Bedient sich zum Befüllen bei den Metadaten. Das Logo der HFU muss, wie bereits oben erwähnt, von dort bezogen werden.

Muss nicht bearbeitet werden.