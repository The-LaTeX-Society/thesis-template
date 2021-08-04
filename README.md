# Thesis Template

Vorlage für wissenschaftliche Arbeiten – insbesondere Bachelor- und Masterarbeiten – an der Hochschule Furtwangen.

## Dateistruktur

Die nachfolgende Liste führt alle Ordner und Dateien auf, welche für den Ersteller der Thesis bei der Bearbeitung der Thesis bearbeitet werden können / sollen.

- abstract/
  - Abstract_English.tex
  - Abstract_German.tex
- appendix/
  - ...
- content/
  - ...
- images/
  - ...
- Thesis.tex
- acronyms.tex
- appendix.tex
- bibliography.bib
- content.tex
- foreword.tex
- metadata.tex
- style.tex

### Abstract

Das Abstract wird allein durch die zwei Dateien im Ordner abstract/ editiert. In diesen wird jeweils der Text in eckigen Klammern durch den entsprechenden Abstract-Text auf Englisch oder Deutsch ersetzt.

### Anhang

Ein Anhangskapitel wird wie in den Beispieldateien im Order appendix/ erstellt. Um dieses Kapitel in den Anhang der Thesis aufzunehmen, muss in der Datei appendix.tex innerhalb der appendices-Umgebung folgender Befehl angehängt werden. (Siehe Beispielanhang.)

```LaTeX
\appendixnum
\include{appendix/<Name der Datei>}
```

### Kapitel

Kapitel der Thesis werden je als Datei in dem Ordner content/ angelegt. Eingebunden werden Kapitel über die Datei content.tex mit folgendem Befehl.

```LaTeX
\include{content/<Name der Datei>}
```

### Bilder

Bilder, welche für die Thesis verwendet werden, sollten unter dem Pfad images/ abgelegt werden. Die darin vorhandene Datei hfu_logo.eps wird für die Titelseite benötigt. Bilder werden unter Verwendung des zu der Datei Thesis.tex relativen Pfades eingebunden.

```LaTeX
\includegraphics{images/example-image.png}
```

### Zu bearbeitende Dateien

#### Thesis.tex

Hier wird die Struktur der Thesis festgelegt. In dieser Datei sollten keine direkten Änderungen vorgenommen werden. Es können jedoch gewisse Punkte wie ein Vorwort, Verzeichnisse, römische Seitenzählung oder ein Anhang durch ein- / auskommentieren eingebunden werden. 

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
\acused{abc} Alphabeten (\acp{abc})
```

#### bibliography.bib

Hier werden verwendete Quellen abgelegt. Entsprechender Code kann von den meisten gängigen Portalen direkt übernommen werden.

#### foreword.tex

Sollte ein Vorwort gewünscht sein, kann dieses hier eingefügt werden. Der Text in eckigen Klammern muss hierbei ersetzt werden, während die restlichen Zeilen unberührt bleiben sollten.

#### metadata.tex

Hier werden die entsprechenden Metadaten eingefügt, welche über die Vorlage verwendet werden. Sie können auch jederzeit mit ihrem entsprechenden Befehl (bspw. ```\metadataTitle```) verwendet werden.

#### style.tex

Hier können stilistische Änderungen vorgenommen werden, ohne das Backend der Thesis bearbeiten zu müssen. Es stehen unter anderem Optionen zu verschiedenen Hervorhebungen, Schriftarten und der Darstellung von Quelltext zur Verfügung.

Außerdem wird hier die Silbentrennung unbekannter Wörter definiert.

Es ist empfohlen, hier definierte Hervorhebungen (```\code{...}```) zu verwenden, anstatt z. B. bei jedem Quelltext in der Thesis erneut ```\ttfamily``` zu verwenden.

### Nicht zu bearbeitende Dateien

Die folgenden Dateien müssen nur in Sonderfällen bearbeitet werden. Hier werden diverse Formatierungen, Seitenlayouts und Standardtexte festgelegt.

- abstract.tex
- format.tex
- statutory_declaration.tex
- title.tex