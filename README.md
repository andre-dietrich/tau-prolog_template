<!--

author:   André Dietrich
email:    andre.dietrich@ovgu.de
version:  1.0.3
language: de
narrator: Deutsch Female
logo:     img/logo.jpg

comment:  Dieses Buch soll in die Programmiersprache PROLOG und in die mit ihr verbundene
          'Logik-programmierung' einführen. Die Idee, 'Logik als eine Programmiersprache'
          zu verwenden, führt zu einer völlig neuen Auffassung vom Programmieren: Das
          Programm ist nicht eine Folge von Handlungsanweisungen, sondern eine Sammlung
          von Fakten und Regeln. Das zu lösende Problem wird als eine Anfrage an diese
          Sammlung formuliert. Im Idealfall führt die logisch korrekte Formulierung der
          Regeln und der Anfrage zur Lösung des Problems.


import: https://raw.githubusercontent.com/liaTemplates/tau-prolog/master/README.md


@stammbaum_db
```prolog @0
maennl(adam).
maennl(alfred).
maennl(anton).
maennl(arthur).
maennl(baldur).
maennl(bernd).
maennl(boris).
maennl(casanova).
maennl(clemens).
maennl(donald).

weibl(adele).
weibl(alwine).
weibl(anna).
weibl(ariadne).
weibl(barbara).
weibl(berta).
weibl(cleopatra).
weibl(cosima).
weibl(daisy).

verheiratet(adam,adele).
verheiratet(adele,adam).
verheiratet(alfred,alwine).
verheiratet(alwine,alfred).
verheiratet(anton,anna).
verheiratet(anna,anton).
verheiratet(arthur,ariadne).
verheiratet(ariadne,arthur).
verheiratet(baldur,barbara).
verheiratet(barbara,baldur).
verheiratet(bernd,berta).
verheiratet(berta,bernd).
verheiratet(clemens,cleopatra).
verheiratet(cleopatra,clemens).

/* elter(X,Y) heißt: Y ist Elternteil von X */

elter(baldur,adam).
elter(baldur,adele).
elter(barbara,alfred).
elter(barbara,alwine).
elter(bernd,anton).
elter(bernd,anna).
elter(berta,arthur).
elter(berta,ariadne).
elter(boris,arthur).
elter(boris,ariadne).
elter(casanova,baldur).
elter(casanova,barbara).
elter(clemens,baldur).
elter(clemens,barbara).
elter(cleopatra,bernd).
elter(cleopatra,berta).
elter(cosima,bernd).
elter(cosima,berta).
elter(donald,clemens).
elter(donald,cleopatra).
elter(daisy,clemens).
elter(daisy,cleopatra).
```
@end

-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://LiaScript.github.io/course/?https://github.com/LiaBooks/Arbeitsbuch-Prolog)

# Arbeitsbuch PROLOG



## Originales Vorwort

Dieses Buch soll in die Programmiersprache PROLOG und in die mit ihr verbundene
'Logik-programmierung' einführen. Die Idee, 'Logik als eine Programmiersprache'
zu verwenden, führt zu einer völlig neuen Auffassung vom Programmieren: Das
Programm ist nicht eine Folge von Handlungsanweisungen, sondern eine Sammlung
von Fakten und Regeln. Das zu lösende Problem wird als eine Anfrage an diese
Sammlung formuliert. Im Idealfall führt die logisch korrekte Formulierung der
Regeln und der Anfrage zur Lösung des Problems.

Dieser Ansatz ist faszinierend, und das allein schon wäre Grund genug, PROLOG
als zweite Programmiersprache für die Schule in Betracht zu ziehen. Hinzu kommen
aber noch andere Vorteile:

* Die Beschäftigung mit einer Sprache, die sich völlig von den
  befehlsorientierten Sprachen wie PASCAL unterscheidet, weitet den Horizont;
  altbekannte Algorithmen erscheinen in einem neuen Licht und neuartige Probleme
  können behandelt werden.
* Die wesentlichen Grundelemente von PROLOG bilden eine kleine, überschaubare
  Menge. (Sie zu beherrschen ist allerdings nicht ganz einfach.)
* Der aktive Umgang mit logischen, deklarativen Programmen fördert (so hoffen
  wir) das logische Denken.

Den letzten Punkt halten wir für entscheidend; daher haben wir uns in diesem
Buch sehr stark auf den logischen Kern der Sprache – auf 'pures' PROLOG –
beschränkt (und nehmen eine etwas spartanische 'Oberfläche' in Kauf). Es geht
uns nicht um die möglichst umfassende Vermittlung der Programmiersprache,
sondern um das Bekanntmachen eines neuen, mächtigen und schönen
Programmierkonzeptes. Zum Vertrautwerden mit diesem neuen Konzept bedarf es
vieler sinnvoller Beispiele und Aufgaben; wir hoffen, hier genügend
bereitgestellt zu haben.

Das Buch besteht im wesentlichen aus zwei Teilen. Der erste Teil gibt eine
Einführung in die Arbeitsweise von PROLOG, das grundlegende Verfahren der
Rekursion und den Datentyp der Liste. Der zweite Teil besteht aus elf
Vertiefungen; diese sind weitgehend unabhängig voneinander und nach steigender
Komplexität geordnet. Für einen Kurs schlagen wir vor, zuerst den ersten Teil
(evtl. ohne Kapitel 7) und dann mindestens eine Vertiefung durchzuarbeiten. Ein
'Schnupperkurs' von wenigen Stunden (vielleicht schon in Sekundarstufe I) könnte
aus Kapitel 1 und 2, dem Anfang von Kapitel 3 und der Vertiefung B, der
Datenbasisprogrammierung, bestehen. Bei Bedarf könnte dies noch mit einigen
Rätseln aus Vertiefung A gewürzt werden.

Wir verwenden PROLOG nach dem sogenannten Edinburgh-Standard, der durch das Buch
von CLOCKSIN und MELLISH definiert wurde und sich inzwischen weitgehend
durchgesetzt hat. In Versionen, die sich nach diesem Standard richten, laufen
die Programme des Buches problemlos. Für einige gängige Versionen sind gezielte
Hinweise im Anhang gegeben. Dort findet man auch Hinweise auf die Bezugsquellen.

Wir bedanken uns bei dem Herausgeber, Herrn StD Dietrich Pohlmann, für
zahlreiche Anregungen und Verbesserungsvorschläge und beim Verlag Ferd. Dümmler
für die freundliche Betreuung. Wir danken weiterhin Ingrid Hafenbrak für die
Illustrationen, Frau Sylvia Platz und Herrn Martin Kammerer für die Hilfe bei
der Gestaltung des Manuskriptes und Herrn Dr. Klaus Scheler für das sorgfältige
Korrekturlesen. Schließlich gilt unser Dank den Mannheimer Schülern und Lehrern
vom Elisabeth Gymnasium und vom Gymnasium Feudenheim, die uns ermöglichten,
unsere Ideen in der Schulpraxis zu erproben.

Es freut uns, dass nach recht kurzer Zeit eine Neuauflage erforderlich wurde.
Dabei wurden nur einige Druckfehler und Unstimmigkeiten berichtigt; die beiden
Auflagen sind also uneingeschränkt nebeneinander im Unterricht einsetzbar.
Heidelberg und Weingarten

Hartmut Göhner, Bernd Hafenbrak

Wir bedanken uns bei den beiden Autoren, die dem Landesinstitut für Schule und
Ausbildung Mecklenburg-Vorpommern (L.I.S.A.) die Texte und Programme zur
Verfügung stellten, damit wir das – leider vergriffene – Arbeitsbuch PROLOG in
den Landesbildungsserver einstellen konnten. Schwerin

Gabriele Lehmann

## Grundlagen

                            --{{0}}--
Einen kleinen Blumenstrauß zu beginn.

![flowers](img/flowers.png)<!-- style="max-width: 100%;" -->

                            --{{1}}--
Dieses Buch ist leider im original nicht im Vierfarbendruck erschienen aber wir
können den Willkommensstrauß auch kurz mit einfachen Worten wie:

                              {{1}}
* Die Rose ist rot.
* Die Tulpe ist gelb.
* Die Nelke ist weiß.
* Das Vergißmeinnicht ist blau.
* Das Veilchen ist blau.
<!-- --{{1}}-- Die Rose ist rot, die Tulpe ist gelb oder das Veilchen ist blau. -->


                            --{{2}}--
Solche **Fakten** (Tatsachen) wie die Zusammensetzung eines Straußes können in
PROLOG wie folgt abgebildet werden:

    {{2}}
```prolog
rot(rose).
gelb(tulpe).
weiss(nelke).
blau(vergissmeinnicht).
blau(veilchen).
```

                            --{{2}}--
Die **Prädikate** (Eigenschaften) _rot_, _gelb_, _weiss_ und _blau_ treffen auf
gewisse Konstanten wie zum Beispiel _rose_ zu, dies schreiben wir in der obigen
Form. Sowohl Prädikate als auch Konstanten werden mit kleinem Anfangsbuchstaben
geschrieben, deutsche Sonderzeichen vermeiden wir. Jedes Faktum wird mit einem
Punkt und dem Drücken der RETURN-Taste abgeschlossen.

### PROLOG-Programme

                            --{{0}}--
Die hier genuzte PROLOG-IDE besteht immer aus zwei Teilen, einer Eingabe für das
Programm. Wenn du hier auf Ausführen klickst, so wird dieses Programm geladen.
Da dieses Programm jedoch einen syntaktischen Fehler hat, erhältst du zunächst
eine Fehlermeldung, die auf ein Syntax-Problem hinweist.

                            --{{1}}--
Du kannst den Code auch direkt editieren und den fehlenden Punkt am Ende der
letzten Zeile einfügen. Wenn du dann wieder auf Ausführen klickst, so wird dir
angezeigt, dass deine Datenbasis erfolgreich geladen werden konnte. Und falls du
dir später mal wegen einer Änderung nicht sicher bist, so kannst du auch jede
beliebige Version wieder herstellen, indem du einfach auf die Pfeil-Buttons
neben der aktuellen Versionnummer klickst.

```prolog blumenstrauss.pro
rot(rose).
gelb(tulpe).
weiss(nelke).
blau(vergissmeinnicht).
blau(veilchen)
```
@Tau.program(blumenstrauss.pro)

                            --{{2}}--
Um anfragen an deine Datenbasis zu stellen, benötigst du noch eine zweite
Eingabemöglichkeit:

    {{2-4}}
```prolog
rot(rose).
```
@Tau.query(blumenstrauss.pro)

                            --{{3}}--
Solche Eingaben werden als Fragen aufgefasst. Umgangsprachlich formuliert heißt
das: "Ist die Rose rot?". Als Antwort erscheint `true`.

                            --{{4}}--
Und auf die Frage `gelb(veilchen).` erhalten wir `false`. Versuch weitere
solcher Fragen einzugeben. Du wirst sehen: Kommt die Frage buchstabengetreu als
Faktum in der Datenbasis vor, so antwortet PROLOG mit `true`, andernfalls mit
`false`.

    {{4}}
```prolog
gelb(veilchen).
```
@Tau.query(blumenstrauss.pro)

### Variablen

                            --{{0}}--
Wir können mit Hilfe von Variablen auch etwas anspruchsvoller fragen: "Was ist
blau?". Gibt es mehrere Lösungen, so wird zunächst immer nur eine angeboten. Du
kannst  weitere Lösungen anfordern, indem du wiederholt auf Ausführen klickst.
Gibt es schließlich keine weitere Lösung mehr, so erscheint `false.` mit einem
einem abschließenden Punkt.

```prolog
blau(X).
```
@Tau.query(blumenstrauss.pro)

                            --{{1}}--
Variablen werden mit einem großen Anfangsbuchstaben geschrieben. Dieselbe Frage
können wir auch mit einer anderen (mehr aussagekräftigeren) Variablen stellen.
Beachte wie sich die Ausgabe verändert.

    {{1}}
```prolog
blau(Blume).
```
@Tau.query(blumenstrauss.pro)


### Zweistellige Prädikate

                            --{{0}}--
Dies ist die Urlaubsplanung für die nächsten Ferien, die umgangssprachliche
Formulierung kann ganz einfach in eine PROLOG-Programm übersetzt werden.

**Umgangsprachlich:** Axel fährt nach England, Beate fährt nach Griechenland und
in die Türkei, Clemens, Elmar und Frederike fahren nach Frankreich, Dagmar fährt
nach Italien.

--------------------------------------------------------------------------------

```prolog urlaubsplanung.pro
faehrt_nach(axel,england).
faehrt_nach(beate,griechenland).
faehrt_nach(beate,tuerkei).
faehrt_nach(clemens,frankreich).
faehrt_nach(dagmar,italien).
faehrt_nach(elmar,frankreich).
faehrt_nach(frederike,frankreich).
```
@Tau.program(urlaubsplanung.pro)

                            --{{1}}--
In dieser **Datenbasis** gibt es nur ein Prädikat, das zweistellige Prädikat
`faehrt_nach`. Laden die obige Datenbasis in PROLOG. Die Frage "Wer fährt nach
England?" heißt in PROLOG:

    {{1}}
```prolog Anfrage:
faehrt_nach(X,england).
```
@Tau.query(urlaubsplanung.pro)

                            --{{2}}--
Beantworte die folgenden Fragen, indem du sie in PROLOG übersetzt und vergleiche
deine Anfragen mit den Auflösungen:



1. Fährt Axel nach Griechenland?

       [( )] Ja
       [(X)] Nein
   *************************************
   ```prolog
   faehrt_nach(axel, griechenland).
   ```
   @Tau.query(urlaubsplanung.pro)
   *************************************

2. Wohin fährt Beate?

       [[ ]] england
       [[ ]] frankreich
       [[X]] griechenland
       [[ ]] italien
       [[X]] tuerkei
   *************************************
   ```prolog
   faehrt_nach(beate, X).
   ```
   @Tau.query(urlaubsplanung.pro)
   *************************************

3. Wohin fährt Xaver?

       [[ ]] england
       [[ ]] frankreich
       [[ ]] griechenland
       [[ ]] italien
       [[ ]] tuerkei
   *************************************
   Xaver fährt nirgends hin, er ist nicht in der Datenbasis enthalten.

   ```prolog
   faehrt_nach(xaver, Urlaubsziel).
   ```
   @Tau.query(urlaubsplanung.pro)
   *************************************
4. Wer fährt nach Frankreich?

       [[ ]] Axel
       [[ ]] Beate
       [[X]] Clemens
       [[ ]] Dagmar
       [[X]] Elmar
       [[X]] Frederike
   *************************************
   ```prolog
   faehrt_nach(Wer, frankreich).
   ```
   @Tau.query(urlaubsplanung.pro)
   *************************************
5. Wer fährt wohin?

       [[!]]
   <script>true;</script>
   *************************************
   ```prolog
   faehrt_nach(Person, Ziel).
   ```
   @Tau.query(urlaubsplanung.pro)
   *************************************

### _und_ & _oder_ Operatoren

    {{0-1}}
![breakfast](img/breakfast.png)<!-- style="max-width: 100%" -->

                            --{{0}}--
Die Vorlieben und Abneigungen am Frühstückstisch seien in der folgenden
PROLOG-Datenbasis mit dem Namen 'fruehstueck.pro' festgehalten:

```prolog fruehstueck.pro
mag(papa,muesli).
mag(papa,brot).
mag(mami,kuchen).
mag(mami,brot).
mag(oma,brot).
mag(baby,muesli).
mag(baby,kuchen).
hasst(papa,kuchen).
hasst(mami,muesli).
hasst(oma,muesli).
hasst(oma,kuchen).
hasst(baby,brot).
```
@Tau.program(fruehstueck.pro)

```prolog Anfrage:
mag(papa, brot).
```
@Tau.query(fruehstueck.pro)

                            --{{1}}--
Bis jetzt jetzt soltest du in der Lage sein, vier Arten von Fragen stellen. Du
kannst dich selber testen und PROLOG dazu bringen, diese Fragen zu beantworten.

      {{1-2}}
1. Mag Papa Kuchen?
2. Wer haßt Müsli?
3. Was mag Oma?
4. Wer mag was?



                            --{{2}}--
Für die Frühstücksplanung sind aber auch zusammengesetzte Fragen wichtig die
Prädikate mit _und_ oder _oder_ verknüpft. Das Zeichen in PROLOG für _und_ ist
ein Komma, für _oder_ schreibt man Semikolon.

                            --{{3}}--
Damit ergeben sich folgende PROLOG-Fragen:

    {{2-4}}
* Wer haßt Kuchen _und_ mag Müsli?

      {{3}}
  ***********************************
  ```prolog
  hasst(X,kuchen), mag(X,muesli).
  ```
  @Tau.query(fruehstueck.pro)
  ***********************************
* Wer mag Kuchen _und_ Brot?

      {{3}}
  ***********************************
  ```prolog
  mag(X,brot), mag(X,kuchen).
  ```
  @Tau.query(fruehstueck.pro)
  ***********************************
* Wer mag Brot _oder_ Kuchen?

      {{3}}
  ***********************************
  ```prolog
  mag(X,brot); mag(X,kuchen).
  ```
  @Tau.query(fruehstueck.pro)
  ***********************************


                            --{{4}}--
Teste jetzt dein Wissen und versuch die folgenden Fragen mit PROLOG zu
beantworten und  vergleiche deine Lösungen mit den Auflösungen.

          {{4}}
1. Wer mag Kuchen und Müsli?

       [[ ]] Mami
       [[X]] Baby
       [[ ]] Papa
       [[ ]] Omi
   **************************
   ```prolog
   mag(X, kuchen), mag(X, muesli).
   ```
   @Tau.query(fruehstueck.pro)
   **************************
2. Was mögen sowohl Papa als auch Mami?

       [[ ]] Kuchen
       [[X]] Brot
       [[ ]] Müsli
   *********************************
   ```prolog
   mag(papa, X), mag(mami, X).
   ```
   @Tau.query(fruehstueck.pro)
   *********************************
3. Wer mag Kuchen und haßt Müsli?

       [[ ]] Baby
       [[X]] Mami
       [[ ]] Papa
       [[ ]] Omi
   **************************
   ```prolog
   mag(X, kuchen), hasst(X, muesli).
   ```
   @Tau.query(fruehstueck.pro)
   **************************

### Aufgaben

[test](#aufgabe)


                            --{{0}}--
Die folgenden beiden Abschnitte sollen dazu dienen, das bereits gelernte zu
wiederholen und zu festigen, bevor wir lernen wie man komplexere Sachverhalte
durch die Nutzung von Regeln abbildet.

#### Blumenstrauß #2

Stellen Sie die Gegebenheiten des Willkommensstraußes von Aufgabe 1 mit Hilfe
eines zweistelligen Prädikates farbe dar.

```prolog blumenstrauss2.pro
rot(rose).
gelb(tulpe).
weiss(nelke).
blau(vergissmeinnicht).
blau(veilchen).
```
@Tau.program(blumenstrauss2.pro)

```prolog Anfrage:

```
@Tau.query(blumenstrauss2.pro)

Welchen Vorteil hat diese zweistellige Darstellung?

    [[!]]
**************************************

**Vorteil:** Man kann auch Fragen stellen wie: "_Welche Farbe hat die Rose?_"

```prolog
blume(rot, rose).
blume(gelb, tulpe).
blume(weiss, nelke).
...

?- blume(rot, X).
```

**************************************

#### Beziehungen

                            --{{0}}--
Übersetz die folgenden Sätze in eine PROLOG-Datenbasis.


    {{0-1}}
![cats](img/cats.png)

* Peter liebt Susi.
* Hans liebt Susi und Sabine.
* Sabine liebt Peter und haßt Hans.
* Susi liebt Peter und Felix.
* Susi haßt Sabine.
* Peter haßt Felix.
* Felix liebt sich selbst.

```prolog @Tau(beziehungen.pro,% und hier deine fragen)
% gib hier die Beziehungen ein
```


                            --{{1}}--
Versuch die folgenden Anfragen selbst zu lösen, bevor du sie mit den Auflösungen
vergleichst:



    {{1}}
* Wen liebt Sabine?

      [[!]]
  *************************
  ```prolog
  liebt(sabine, X).
  ```
  *************************
* Wer liebt Sabine?

      [[!]]
  *************************
  ```prolog
  liebt(X, sabine).
  ```
  *************************
* Wer liebt wen?

      [[!]]
  *************************
  ```prolog
  liebt(Wer, Wen).
  ```
  *************************
* Wer liebt jemanden, der ihn auch liebt?

      [[!]]
  *************************
  ```prolog
  liebt(X, Y), liebt(Y, X).
  ```
  *************************
* Wessen Liebe wird mit Haß vergolten?

      [[!]]
  *************************
  ```prolog
  liebt(X, Y), hasst(Y, X).
  ```
  *************************


#### Stammbaum

                            --{{0}}--
Der folgende Stammbaum von Donald und Daisy läßt eine gewisse Systematik bei der
Namensgebung erkennen, die den Überblick erleichtert:

<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: 600px;" -->
``````````
♂ Adam ━━━━━┓
            ┣━━━━ ♂ Baldur ━━━━━┓
♀ Adele ━━━━┛                   ┣━━━━ ♂ Casanova
♂ Alfred ━━━┓                   ┣━━━━ ♂ Clemens ━━━━┓
            ┣━━━━ ♀ Barbara ━━━━┛                   ┃
♀ Alwine ━━━┛                                       ┣━━━━ ♂ Donald
♂ Anton ━━━━┓                                       ┣━━━━ ♀ Daisy
            ┣━━━━ ♀ Berta ━━━━━━┓                   ┃
♀ Anna ━━━━━┛                   ┣━━━━ ♀ Cleopatra ━━┛
♂ Arthur ━━━┓                   ┣━━━━ ♀ Cosima
            ┣━━━━ ♂ Bernd ━━━━━━┛
            ┣━━━━ ♂ Boris
♀ Adriane ━━┛
``````````


                            --{{1}}--
Es gibt verschiedene Möglichkeiten, die Informationen dieses Stammbaumes in
einer Datenbasis festzuhalten. Wir wählen dazu die Prädikate _maennl_, _weibl_,
_verheiratet_ und _elter_. Die Datenbasis wird schon recht groß. In Ihrer Datei
erscheint sie einspaltig, da jedes Faktum mit Punkt und RETURN abgeschlossen
wird.

                              {{1}}
*******************************************************************************
```prolog stammbaum.pro
maennl(adam).
maennl(alfred).
maennl(anton).
maennl(arthur).
maennl(baldur).
maennl(bernd).
maennl(boris).
maennl(casanova).
maennl(clemens).
maennl(donald).

weibl(adele).
weibl(alwine).
weibl(anna).
weibl(ariadne).
weibl(barbara).
weibl(berta).
weibl(cleopatra).
weibl(cosima).
weibl(daisy).

verheiratet(adam,adele).
verheiratet(adele,adam).
verheiratet(alfred,alwine).
verheiratet(alwine,alfred).
verheiratet(anton,anna).
verheiratet(anna,anton).
verheiratet(arthur,ariadne).
verheiratet(ariadne,arthur).
verheiratet(baldur,barbara).
verheiratet(barbara,baldur).
verheiratet(bernd,berta).
verheiratet(berta,bernd).
verheiratet(clemens,cleopatra).
verheiratet(cleopatra,clemens).

/* elter(X,Y) heißt: Y ist Elternteil von X */

elter(baldur,adam).
elter(baldur,adele).
elter(barbara,alfred).
elter(barbara,alwine).
elter(bernd,anton).
elter(bernd,anna).
elter(berta,arthur).
elter(berta,ariadne).
elter(boris,arthur).
elter(boris,ariadne).
elter(casanova,baldur).
elter(casanova,barbara).
elter(clemens,baldur).
elter(clemens,barbara).
elter(cleopatra,bernd).
elter(cleopatra,berta).
elter(cosima,bernd).
elter(cosima,berta).
elter(donald,clemens).
elter(donald,cleopatra).
elter(daisy,clemens).
elter(daisy,cleopatra).
```
@Tau.program(stammbaum.pro)

```prolog Anfrage:
% Anfragen hier eingeben.
```
@Tau.query(stammbaum.pro)
*******************************************************************************

                            --{{2}}--
Beachte, wie sich die Symmetrie des Prädikats `verheiratet` in der Datenbasis
ausdrückt. Das Prädikat `elter` bedarf einer Erläuterung. Hierzu wurde ein
noch einen Kommentar eingefügt:

                             {{2-3}}
**Kommentar:** `/* elter(X,Y) heißt: Y ist Elternteil von X */ `

                            --{{2}}--
Alles was zwischen den Kommentarzeichen `/*` und `*/` steht, wird von PROLOG
ignoriert. Für den Benutzer ist im obigen Fall ein solcher Kommentar notwendig,
da die Reihenfolge von X und Y von uns willkürlich (in Anlehnung an
Gepflogenheiten der Mathematiker) festgelegt wurde.

                            --{{3}}--
Lade das Programm und versuche die folgenden Fragen zu stellen und zu
beantworten. Nutze bei deinen Anfragen `X` als freie Variable!

                             {{3-4}}
*******************************************************************************
* Wer sind die Eltern von Daisy?

      [[elter(daisy, X).]]
      @Tau.check(stammbaum.pro,`setof(X, @input, [clemens, cleopatra])`)

* Mit wem ist Baldur verheiratet?

      [[verheiratet(baldur, X).]]
      @Tau.check(stammbaum.pro,`setof(X, @input, [barbara])`)


* Wie heißen die Kinder von Arthur?

      [[elter(X, arthur).]]
      @Tau.check(stammbaum.pro,`setof(X, @input, [barbara])`)

*******************************************************************************

                            --{{4}}--
Wenn wir nun die Mutter von Cosima suchen, müssen wir eine zusammengesetzte
Frage stellen: _Welchen weiblichen Elternteil hat Cosima?_. In PROLOG lautet das
wie folgt. Beide Fragen sind logisch gleichwertig und erzielen dieselbe Antwort.
Auf Unterschiede bei der Abarbeitung der beiden Anfragen wollen wir erst in
Kapitel 3 eingehen.

                             {{4-5}}
********************************************************************************
Wer ist die Mutter von Cosima?

```prolog
elter(cosima,X), weibl(X).
```
@Tau.query(stammbaum.pro)

oder ...

```prolog
weibl(X), elter(cosima,X).
```
@Tau.query(stammbaum.pro)
****************************************************************************


                              {{5}}
Versuche selbst als kleine Fingerübung auf jeweils zwei verschiedene Arten nach
dem Vater von Daisy, nach den Söhnen von Barbara und nach den Töchtern von
Anton!

                            --{{6}}--
Suchen wir die Großeltern von Donald, dann erreichen wir dies durch die folgende
Anfrage. In Worten: "Gesucht sind _E_ und _G_, so dass _E_ Elternteil von Donald
und _G_ Elternteil von _E_ ist.

    {{6-7}}
```prolog
elter(donald,E), elter(E,G).
```
@Tau.query(stammbaum.pro)

                            --{{7}}--
Versuche selbst die folgenden Fragen zu lösen!

<!-- --{{7}}-- Und suche die Großmütter von Clemens, die Urgroßeltern von Daisy,
die Schwiegermutter von Bernd! -->

    {{7-8}}
* Wer ist die Großmütter von Clemens?

      [[!]]
  *******************************
  ```prolog
  weibl(Oma), elter(E, Oma), elter(clemens, E).
  ```
  @Tau.query(stammbaum.pro)
  *******************************
* Wer sind die Urgroßeltern von Daisy?

      [[!]]
  *******************************
  ```prolog
  elter(G, E), elter(E, G), elter(daisy, E).
  ```
  @Tau.query(stammbaum.pro)
  *******************************
* Wie heißt die Schwiegermutter von Bernd?

      [[!]]
  *******************************
  ```prolog
  verheiratet(bernd, F), elter(F, S), weibl(S).
  ```
  @Tau.query(stammbaum.pro)
  *******************************

                            --{{8}}--
Eine besondere Schwierigkeit tritt auf, wenn wir den Bruder von Clemens suchen.
Der Bruder ist das Kind der beiden Eltern von Clemens, das ergibt die folgende
Anfrage. Da sich diese Frage sich nicht mehr in einer Zeile unterbringen läßt,
können wir auch mehrere Zeilen für eine Anfrage nutzen. Erst durch den Punkt
wird die Anfrage abgeschlossen.


    {{8-9}}
```prolog
elter(clemens, V), maennl(V), elter(clemens, M), weibl(M),
elter(X, V), elter(X, M), maennl(X).
```
@Tau.query(stammbaum.pro)

                            --{{9}}--
Diese Anfrage nach den Brüdern von Clemens ist jedoch noch fehlerhaft. Außer der
richtigen Lösung Casanova erscheint auch Clemens selbst als Antwort. Wir
benötigen hier ein Prädikat für die Ungleichheit, dies wird in PROLOG
geschrieben als `\=`. Unsere Frage nach dem Bruder von Clemens lautet damit wie
folgt:

    {{9}}
```prolog
elter(clemens, V), maennl(V), elter(clemens, M), weibl(M),
elter(X, V), elter(X, M), maennl(X), X \= clemens.
```
@Tau.query(stammbaum.pro)

                           --{{10}}--
Versuch diese Anfrage selbst verändern um auch nach den Schwestern
von Cosima zu suchen.



## Regeln

                            --{{0}}--
Im vorigen Beispiel waren einige Grundbegriffe wie Elternteil, männlich,
weiblich durch die Datenbasis erklärt, andere Begriffe wie Vater,
Schwiegermutter oder Bruder mussten wir bei Anfragen in diese Grundbegriffe
übersetzen. Dieses umständliche Verfahren können wir vereinfachen, indem wir zu
den Fakten unserer Datenbasis noch **Regeln** hinzufügen. Im Beispiel wären das
die Regeln

```prolog +regeln.pro
mutter(X,Y) :- elter(X,Y), weibl(Y).

vater(X,Y) :-  elter(X,Y), maennl(Y).

kind(X,Y) :-   elter(Y,X).

schwiegermutter(X,Y) :- verheiratet(X,Z), mutter(Z,Y).

bruder(X,Y) :- vater(X,V), mutter(X,M),
               vater(Y,V), mutter(Y,M), maennl(Y), Y\=X.

maennl(adam).
maennl(alfred).
maennl(anton).
maennl(arthur).
maennl(baldur).
maennl(bernd).
maennl(boris).
maennl(casanova).
maennl(clemens).
maennl(donald).

weibl(adele).
weibl(alwine).
weibl(anna).
weibl(ariadne).
weibl(barbara).
weibl(berta).
weibl(cleopatra).
weibl(cosima).
weibl(daisy).

verheiratet(adam,adele).
verheiratet(adele,adam).
verheiratet(alfred,alwine).
verheiratet(alwine,alfred).
verheiratet(anton,anna).
verheiratet(anna,anton).
verheiratet(arthur,ariadne).
verheiratet(ariadne,arthur).
verheiratet(baldur,barbara).
verheiratet(barbara,baldur).
verheiratet(bernd,berta).
verheiratet(berta,bernd).
verheiratet(clemens,cleopatra).
verheiratet(cleopatra,clemens).

/* elter(X,Y) heißt: Y ist Elternteil von X */

elter(baldur,adam).
elter(baldur,adele).
elter(barbara,alfred).
elter(barbara,alwine).
elter(bernd,anton).
elter(bernd,anna).
elter(berta,arthur).
elter(berta,ariadne).
elter(boris,arthur).
elter(boris,ariadne).
elter(casanova,baldur).
elter(casanova,barbara).
elter(clemens,baldur).
elter(clemens,barbara).
elter(cleopatra,bernd).
elter(cleopatra,berta).
elter(cosima,bernd).
elter(cosima,berta).
elter(donald,clemens).
elter(donald,cleopatra).
elter(daisy,clemens).
elter(daisy,cleopatra).
```
@Tau.program(stammbaum+regeln.pro,@input)

```prolog
mutter(X,Y).
```
@Tau.query(stammbaum+regeln.pro)


{{1-5}} **Neues Zeichen:** `:-` ==> falls

                            --{{1}}--
Dabei wird das Zeichen `:-` gelesen als 'falls' oder 'wenn'.  Der Regelteil vor
dem Zeichen `:-` heißt **Kopf der Regel**, der Rest heißt **Rumpf der Regel**.

                            --{{1}}--
Umgangssprachlich lesen wir die Regel für mutter als:
_Y ist Mutter von X, wenn Y Elternteil von X ist und Y weiblich ist._

                            --{{1}}--
Die Regel für schwiegermutter heißt:
_Y ist Schwiegermutter von X, falls eine Person Z mit X verheiratet ist und Y Mutter von Z ist._

                            --{{2}}--
Manche Prädikate werden durch mehrere Regeln beschrieben:

                             {{2-3}}
*******************************************************************************
```prolog
schwager(X,Y) :- verheiratet(X,Z), bruder(Z,Y).
schwager(X,Y) :- schwester(X,Z),   verheiratet(Z,Y).
```

**In Worten:** Y ist Schwager von X, falls X mit einer Person Z verheiratet ist
und Y Bruder von Z ist oder falls X eine Schwester Z hat, die mit Y
verheiratet ist.

*******************************************************************************

                            --{{3}}--
Sowohl Fakten als auch Regeln bezeichnen wir als **Klauseln**. Die Gesamtheit
aller Klauseln bildet ein PROLOG-**Programm**. Dieses wird mit Hilfe des Editors
als Datei angelegt. Mit _consult_ wird das Programm geladen.

                            --{{4}}--
Lies die Regel für das Prädikat `bruder` umgangssprachlich. Ergänze die das
Programm `stammbaum2.pro` um Regeln für die folgenden Verwandtschaftsbeziehungen
und schreibe vor jedes Prädikat einen Kommentar zur Erläuterung:

    {{4-5}}
1. Sohn

      [[!]]
   ************************
   ```prolog
   /* sohn(X, Y) heißt: Y ist Kind von X und Y ist männlich */
   sohn(X, Y) :- kind(X, Y), maennl(Y).
   ```
   ************************
2. Tochter

      [[!]]
   ************************
   ```prolog
   /* tochter(X,Y) heißt: Y ist Kind von X und Y ist weiblich */
   tochter(X, Y) :- kind(X, Y), weibl(Y).
   ```
   ************************
3. Schwester

       [[!]]
   ************************
   ```prolog
   /* schwester(X,Y) heißt: Y ist die Schwester von X, wenn beide den gleichen
   Vater und die gleiche Mutter haben und Y ist weiblich und X und Y nicht die
   gleiche Person sind. */
   schwester(X,Y) :- vater(X,V), mutter(X,M),
                     vater(Y,V), mutter(Y,M), weibl(Y), Y\=X.
   ```
   ************************
4. Großeltern
5. Füge Kommentare ein, w. z. B. `/* vater(X,Y) heißt: Y ist Vater von X */`


                            --{{5}}--
Lade dein Programm und frage mit Hilfe der neuen Prädikate nach den Großeltern
von Donald, dem Bruder von Clemens usw. Überprüfen Sie, ob PROLOG die Antworten
gibt, die du aufgrund des Stammbaums erwartest.

                              {{5}}
******************************************************
**Frage nach:**

* Großeltern von Donald,
* dem Bruder von Clemens
* usw.
******************************************************

### Geltungsbereiche

                            --{{0}}--
Bis jetzt haben wir Regeln verwendet, um neue Prädikate mit Hilfe der schon
bekannten zu definieren. Man kann Regeln auch dazu benutzen, den Geltungsbereich
von schon bekannten Prädikaten zu erweitern; zum Beispiel haben wir in der Datei
`fruehstueck.pro` die Prädikate mag und hasst vorliegen, die Vorlieben und
Abneigungen beim Frühstück beschreiben. Nun sei bekannt, dass der Opa dieser
Familie alles mag, was Oma haßt. Diese Regel lautet dann in PROLOG:

```prolog
mag(opa,X):- hasst(oma,X).
```

2) Nehmen Sie diese Regel in das PROLOG-Programm auf. Welche Antworten erwarten Sie
bei den Fragen

?- mag(opa,X).
?- mag(X,kuchen).
?- mag(opa,muesli).
?- hasst(opa,X).

### Aufgaben

#### Urlaub #2

Zur Gruppe aus der Datei urlaub.pro stößt Romeo. Er fährt überall hin, wo Beate
hinfährt. Wie lautet diese Regel in PROLOG? Ergänzen Sie die Datei urlaub.pro.

#### Nibelungen

Der Nibelungen Not:

1. Siegfried liebt Krimhild und mag Gunther.
2. Krimhild liebt Siegfried und haßt Brunhild.
3. Gunther liebt Brunhild und mag Krimhild und Hagen.
4. Brunhild haßt Siegfried, Gunther und Krimhild.
5. Hagen haßt Siegfried und alle, die Siegfried lieben.
6. Brunhild mag alle, die Siegfried hassen.
7. Alberich haßt alle, mit Ausnahme von sich selbst.

                            --{{0}}--
Schreibe die obigen Aussagen als PROLOG-Programm in eine Datei `nibelungen.pro`.

@Tau(nibelungen.pro,%program,%fragen)

                            --{{1}}--
Stelle die folgenden Fragen:

    {{1-2}}
1. Wer haßt Siegfried?
2. Wen mag Brunhild?
3. Wer haßt wen?
4. Wer liebt wen?


                              {{2}}
*******************************************************************************
Definieren ein Prädikat _ideales\_paar_, das auf _(X,Y)_ zutrifft, falls _X_
von _Y_ und _Y_ von _X_ geliebt wird.

   [[!]]
************************
```prolog
/* schwester(X,Y) heißt: Y ist die Schwester von X, wenn beide den gleichen
Vater und die gleiche Mutter haben und Y ist weiblich und X und Y nicht die
gleiche Person sind. */
schwester(X,Y) :- vater(X,V), mutter(X,M),
                  vater(Y,V), mutter(Y,M), weibl(Y), Y\=X.
```
@Tau.query(nibelungen.pro)
************************

*******************************************************************************

#### Grammtiken

                            --{{0}}--
Regeln kennen wir auch aus der Grammatik. An einem sehr einfachen Beispiel
wollen wir einen Zusammenhang mit PROLOG aufzeigen.

* Der Hund bellt.
* Der Hase flieht.
* Der Fuchs flieht.
* Der Jäger schießt.


                            --{{1}}--
Diese Sätze sind alle nach demselben Schema gebildet, das wir als PROLOG-Regel
schreiben können:

                              {{1}}
```prolog
artikel(der).

nomen(hund).
nomen(hase).
nomen(fuchs).
nomen(jaeger).

verb(bellt).
verb(flieht).
verb(schiesst).

satz(X,Y,Z):- artikel(X), nomen(Y), verb(Z).
```
@Tau.program(grammatik.pro)

                            --{{1}}--
Damit haben wir eine kleine Sprache definiert, die über einen sehr begrenzten
Wortschatz und über eine einzige grammatikalische Regel verfügt und natürlich
nur einen ganz engen Bereich unserer Umgangssprache abdeckt.

                            --{{2}}--
Verwenden Sie das Prädikat satz, um zu überprüfen, ob drei Worte einen Satz
unserer Sprache bilden. Beispiele:


                             {{2-3}}
********************************************************************************
```prolog
satz(der,jaeger,bellt).
```
@Tau.query(grammatik.pro)


```prolog
satz(flieht,der,hund).
```
@Tau.query(grammatik.pro)
********************************************************************************


                            --{{3}}--
Verwende das Prädikat _satz_ auch, um alle möglichen Sätze dieser Sprache zu
erzeugen (Wieviele verschiedene Sätze erwartest du):

                              {{3}}
```prolog
satz(A,B,C).
```
@Tau.query(grammatik.pro)



#### Aufgabe

In einer Gaststätte gibt es

* __Vorspeisen:__    Tomatensuppe, Lauchsuppe, Fleischbrühe mit Backerbsen.
* __Hauptgerichte:__ Sauerbraten mit Spätzle, Leberkäse mit Kartoffeln,
                     Hackbraten mit Reis.
* __Nachspeisen:__   Eis, Obstsalat, Bienenstich.


Ein Menü besteht aus Vorspeise, Hauptgericht und Nachspeise.

Schreiben Sie ein Programm, das ein dreistelliges Prädikat menue enthält. Dieses
Prädikat soll Menüvorschläge überprüfen und erzeugen können.

#### 4-Farbenproblem

                            --{{0}}--
Das dargestellte Rechteck besteht aus 4 Gebieten, die mit den drei Farben _rot_,
_gelb_ und _blau_ so eingefärbt werden sollen, dass keine gleichfarbigen Gebiete
längs einer Linie aneinandergrenzen.


<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: 315px;" -->
``````````
 ┏━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━┓
 ┃             ┃                   ┃
 ┃      1      ┃         2         ┃
 ┃             ┃                   ┃
 ┣━━━━━━━━━━━━━┻━━━━━┳━━━━━━━━━━━━━┫
 ┃                   ┃             ┃
 ┃         4         ┃      3      ┃
 ┃                   ┃             ┃
 ┗━━━━━━━━━━━━━━━━━━━┻━━━━━━━━━━━━━┛
``````````

                            --{{1}}--
Wir lassen ein Programm nach den Lösungen suchen. Die Farbe des Gebietes 1
bezeichnen wir mit der Variablen `F1`, und so weiter. Dabei bedeutet
`einfaerbung(F1, F2, F3, F4)`, dass die Farben `F1`, `F2`, `F3`, `F4` eine
erlaubte Einfärbung des Rechtecks liefern.

    {{1}}
```prolog vier_farben.pro
farbe(rot).
farbe(gelb).
farbe(blau).

einfaerbung(F1, F2, F3, F4) :-
  farbe(F1), farbe(F2), farbe(F3), farbe(F4),
  F1\==F2, F1\==F4, F2\==F3, F2\==F4, F3\==F4.

% todo: einfaerbung2
```
@Tau.program(vier_farben.pro)

                            --{{2}}--
Wir bekommen also die Lösungen durch die folgende Anfrage:

    {{2}}
```prolog Anfrage:
einfaerbung(F1, F2, F3, F4).
```
@Tau.query(vier_farben.pro)


                              {{3}}
***********************************************************************

Versuche nun selbst eine Regel `einfaerbung2(F1, F2, F3, F4, F5)` für das das
folgende Rechteck, bestehend aus 5 Gebieten, zu definieren. Nutze wieder nur
drei Farben und achte darauf, dass keine gleichfarbigen Gebiete
aneinandergrenzen?


<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: 315px;" -->
``````````
 ┏━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━┓
 ┃                ┃                ┃
 ┃     1     ┏━━━━┻━━━━┓     2     ┃
 ┃           ┃         ┃           ┃
 ┣━━━━━━━━━━━┫    3    ┣━━━━━━━━━━━┫
 ┃           ┃         ┃           ┃
 ┃     5     ┗━━━━┳━━━━┛     4     ┃
 ┃                ┃                ┃
 ┗━━━━━━━━━━━━━━━━┻━━━━━━━━━━━━━━━━┛
``````````

Überprüfe deine Regel.

    [[!]]
```prolog @Tau.check(vier_farben.pro)

setof([A,B,C,D,E], einfaerbung2(A,B,C,D,E),
     [[blau, gelb, rot, blau, gelb],
      [blau, rot, gelb, blau, rot],
      [gelb, blau, rot, gelb, blau],
      [gelb, rot, blau, gelb, rot],
      [rot, blau, gelb, rot, blau],
      [rot, gelb, blau, rot, gelb]]).
```
****************************************
Der Körper der Regel `einfaerbung2` müßte in etwa wie folgt aussehen:

```prolog
% einfaerbung2(F1,F2,F3,F4,F5) :-
   farbe(F1), farbe(F2), farbe(F3), farbe(F4), farbe(F5),
   F1\==F2, F1\==F3, F1\==F5,
   F2\==F3, F2\==F4,
   F3\==F4, F3\==F5,
   F4\==F5.
```
@Tau.query(vier_farben.pro)
****************************************

*******************************************************************************

## So arbeitet Prolog

                            --{{0}}--
Der junge Prinz sucht die schöne Tänzerin der vergangenen Nacht. Auf der Flucht
hat sie ihren goldenen Schuh verloren. Mit diesem besucht er nun die Töchter des
Landes, um nachzuschauen, bei welcher der Fuß in den Schuh passt.

![cinderella](img/cinderella.png)

                            --{{1}}--
Die Suche wäre weniger mühsam, wenn die Daten der Untertanen schon auf dem
Computer verfügbar wären. Es sei etwa auf dem königlichen Hofcomputer eine
PROLOG-Datenbasis abgelegt:


    {{1}}
```prolog aschenputtel.pro
schuhgroesse(adelheid,34).
schuhgroesse(agnes,28).
schuhgroesse(aschenputtel,26).
schuhgroesse(brunhilde,44).
schuhgroesse(kunigunde,28).
schuhgroesse(walburga,38).
```
@Tau.program(aschenputtel.pro)


    {{2-6}}
```prolog
schuhgroesse(aschenputtel,26).
```
@Tau.query(aschenputtel.pro)

                            --{{3}}--
Bei der der obigen Abfrage vergleicht PROLOG vergleicht diese der Reihe nach mit
den Fakten der Datenbasis in `aschenputtel.pro`. Beim dritten Faktum erreicht es
eine Deckung, die Anfrage und dieses Faktum matchen (sprich: mätschen, vom
englischen to match, zusammenpassen).

                            --{{4}}--
PROLOG arbeitet hier also genau wie unser Prinz. Die Anfrage (der Schuh) wird
mit einem Faktum (einem Fuß) verglichen. Passen beide nicht zusammen, so geht
PROLOG zum nächsten Faktum; passen sie, wird das dem Benutzer mit `true`
mitgeteilt. Wurde die ganze Datenbasis durchlaufen, ohne dass ein zur Frage
passendes Faktum gefunden wurde, so gibt PROLOG die Meldung `false` aus.

                            --{{5}}--
Es ist einleuchtend, dass diese schematische Suche von einer Maschine verrichtet
werden kann; und du hast auch schon oft beobachtet, dass PROLOG diese Fertigkeit
fehlerfrei beherrscht. Als Modell können wir uns vorstellen, dass die Maschine
eine Schablone mit der Anfrage über die Datenbasis zieht, bis eine Deckung
erreicht ist.

{{5-6}} **Schablone ==>** `schuhgroesse(aschenputtel,26).`


                            --{{6}}--
Nehmen wir an, der Prinz mit dem Schuh in der Hand stelle die folgende Anfrage.

    {{6-10}}
```prolog
schuhgroesse(X, 26).
```
@Tau.query(aschenputtel.pro)


                            --{{7}}--
Wieder macht sich PROLOG ans Suchen, ob zu dieser Anfrage ein Faktum passt.
Hierbei befolgt es den Grundsatz:

{{7-8}} **Eine Variable kann mit jeder Konstanten matchen.**

                            --{{8}}--
Die Anfrage matcht mit dem dritten Faktum der Datenbasis, dabei matcht `X` mit
`aschenputtel`. Das Ergebnis der erfolgreichen Suche wird wie unten dargestellt
zurückgegeben. Das heißt, die Anfrage ist erfüllbar, wenn die Variable `X` an
die Konstante `aschenputtel` gebunden wird.

    {{8-10}}
```prolog
X = aschenputtel ;
```

                            --{{9}}--
Verlangen wir vom System weitere Antworten auf die Frage, so löst PROLOG die
Variable `X` von der Konstanten `aschenputtel` und setzt die Suche fort. Da es
in der Datenbasis keine weitere Möglichkeit des Matchens findet, gibt es die
Antwort `false` aus.

                            --{{10}}--
Betrachten wir die Abarbeitung einer Frage, die mehrere Antworten zuläßt:

    {{10}}
```prolog
schuhgroesse(X, 28).
```
@Tau.query(aschenputtel.pro)

                            --{{11}}--
PROLOG vergleicht Faktum für Faktum mit der Frage und kann beim zweiten Faktum
matchen, indem es `X` mit `agnes` belegt. Die Antwort lautet also:

    {{11}}
```prolog
X = agnes ;
```

                            --{{11}}--
Fordern wir PROLOG auf, weiter zu suchen, so wird `X` wieder von `agnes` gelöst
und die Frage mit dem dritten, vierten und fünften Faktum verglichen. Erst beim
fünften ist wieder das Matchen möglich:

    {{12}}
```prolog
X = kunigunde ;
```

                            --{{12}}--
Lassen wir nochmals weitersuchen, so wird `X` wieder von `kunigunde` gelöst und
die Frage mit dem sechsten Faktum verglichen. Dort ist Matchen nicht möglich,
und damit ist die Datenbasis erschöpft, also erhalten wir die Antwort `false`.


### Logging der Teilschritte mit _write_

                            --{{0}}--
Damit verlassen wir das schlichte Aschenputtel und wenden uns einem
reichhaltigeren Beispiel zu, dem Stammbaum von Donald und Daisy aus
[Kapitel 1](#11). Dort hattest du in einer Aufgabe nach dem Vater von Daisy
gesucht:

@stammbaum_db(stammbaum2.pro)
@Tau.program(stammbaum2.pro)


```prolog Anfrage
elter(daisy, X), maennl(X).
```
@Tau.query(stammbaum2.pro)


                            --{{1}}--
Das Ziel von PROLOG ist es, die zwei Forderungen an `X` zu erfüllen. Dies macht
es, indem es nacheinander zwei Teilziele anstrebt. Zunächst versucht es, das
erste Teilziel `elter(daisy, X)` zu erreichen und findet auch nach etlichen
Vergleichen eine Möglichkeit zu matchen mit `X = clemens`. Die Variable `X` ist
damit instantiiert (belegt) mit `clemens`. Das zweite Teilziel lautet damit
`maennl(clemens)`, diese Forderung kann beim Durchsuchen der Datenbasis
bestätigt werden. Erst wenn beide Teilziele erreicht sind, wird die Antwort
ausgegeben:


    {{1}}
```prolog
X = clemens;
false.
```

                            --{{2}}--
Fragen wir nochmals nach dem Vater von Daisy, dann versucht PROLOG in dieser
Anfrage das erste Teilziel `maennl(X)` zu erreichen, und dies gelingt auch
sofort mit `X = adam`. Mit dieser Instantiierung von `X` wird das zweite
Teilziel angegangen, also `elter(daisy, adam)`. Diese Ergebnisse können leicht
mit dem originalen [Stammbaum](#11) verglichen werden; PROLOG muss Faktum für
Faktum mit der Frage vergleichen und geht die ganze Datenbasis durch, bis es zum
gleichen Ergebnis kommt. Die Instantiierung von `X` mit `adam` führt also nicht
zum Ziel und wird deshalb rückgängig gemacht. PROLOG gibt die Variable `X`
wieder frei und versucht `maennl(X)` mit einem anderen Faktum zu matchen. Schon
beim nächsten Faktum ist dies möglich und ergibt `X = alfred`. Aber auch damit
scheitert es am zweiten Teilziel, und so probiert PROLOG nacheinander `adam`,
`alfred`, `anton` usw. aus, bis es schließlich mit `X = clemens` beide
Teilforderungen erfüllen kann.


    {{2}}
```prolog
maennl(X), elter(daisy,X).

% 1: maennl(X)
%    1: X = adam
%    2: eltern(daisy, adam) = false
% 2: maennl(X)
%    1: X = alfred
%    2: eltern(daisy, alfred) = false
% .: ...
%
% 9: maennl(X)
%    1: X = clemens
%    2: eltern(daisy, clemens) = true
```
@Tau.query(stammbaum2.pro)

Die folgende Anfragen ist vom deklarativen (beschreibenden) Standpunkt aus
gleichwertig zu der gerade besprochenen; sie sind aber verschieden, wenn man sie
unter prozeduralen Gesichtspunkten betrachtet, das heißt, ihre Abarbeitung
verfolgt. Fragen an das System können vom prozeduralen Standpunkt aus als
Anweisungen gesehen werden. Die untere Anfrage  können wir deklarativ übersetzen
mit _"Wer ist Elternteil von Daisy und männlich?"_ oder prozedural mit
_"Suche ein Elternteil X von Daisy, suche solange, bis du ein männliches X mit dieser Eigenschaft findest"_.


```prolog
elter(daisy,X), maennl(X).
```

Mit einer Anfrage geben wir PROLOG ein Ziel für eine Suche. Dieses Ziel besteht
meist aus mehreren Teilzielen, die PROLOG nacheinander anstrebt. Ein Teilziel
ist erreicht, wenn PROLOG geeignete Variablenbelegungen gefunden hat, welche die
Forderung des Teilziels erfüllen. Man sagt dann kurz (und sprachlich unsauber):
_"Das Teilziel ist erfüllt"._

1. Es werde die Frage nach der Mutter von Daisy gestellt:

   ```prolog
   elter(daisy,X), weibl(X).
   ```
       [[!]]
   ***************************************************

    jjj

   ***************************************************



Beschreiben Sie das Vorgehen von PROLOG, insbesondere, mit welchen Konstanten X
instantiiert wird. Begründen Sie, warum die Anfrage

?- weibl(X), elter(daisy,X).

vom prozeduralen Standpunkt aus ungünstiger ist. Es gibt eine Möglichkeit,
PROLOG bei seiner Arbeit Protokoll führen zu lassen, und zwar mit Hilfe des
Prädikats write. Dieses Prädikat ist vom deklarativen Standpunkt nicht
beschreibbar; man kann höchstens die Eigenschaft festhalten, dass es immer wahr
ist. Es hat aber den 'Seiteneffekt', dass write(X) die jeweilige Belegung der
Variablen X auf den Bildschirm bringt. Durch Einfügen dieses Prädikats können
wir also Zwischenergebnisse sichtbar machen.

Leider bringt die hier genutzte Prolog-Implementierung keine `write` Funktion
mit sich aber mit einem kleinen Trick, können wir eine ähnlich Funktionalität
ganz einfach nachbauen. Du musst dazu nur, den unten stehenden Code im Anfang
von `stambaum2.pro` einfügen:

```prolog
:-use_module(library(js)).

write(X) :- apply(alert, [X], X).
```

2) Überprüfen Sie Ihre Überlegungen von Aufgabe 1 durch Einfügen von write(X) in die obigen Abfragen:
?- elter(daisy,X), write(X), nl, weibl(X).
?- weibl(X), write(X), nl, elter(daisy,X).

(Das Prädikat nl bedeutet 'new line' und bewirkt einen Zeilenvorschub.) In
Kapitel 2 haben wir mit Regeln gearbeitet. Auch sie wollen wir noch kurz
prozedural betrachten. Zur Datenbasis des Stammbaums wurde z. B. die Regel
hinzugefügt

vater(X,Y):- elter(X,Y), maennl(Y).

Die deklarative Lesart dieser Regel kennen wir schon: "Y ist Vater von X, falls
Y Elternteil von X und männlich ist." Prozedural gesehen ist diese Regel eine
Anweisung für den Computer, wie er bei der Suche nach dem Vater vorzugehen hat:
"Ist der Vater Y von X gesucht, so suche zunächst ein Elternteil Y und versuche
auch noch die Bedingung zu erfüllen, dass dieses männlich ist." Also wird z. B.
die Anfrage

?- vater(daisy,V).

intern ersetzt durch die Frage

?- elter(daisy,V), maennl(V).

Die Abarbeitung dieser Frage haben wir schon oben betrachtet. Manche Prädikate
werden durch mehrere Regeln festgelegt; z. B. brauchen wir für den Begriff

'Schwager' zwei Regeln:

`/* schwager(X,Y) heißt: Y ist Schwager von X */`

schwager(X,Y):- verheiratet(X,Z), bruder(Z,Y).
schwager(X,Y):- schwester(X,Z), verheiratet(Z,Y).
Es werde jetzt die Frage gestellt

?- schwager(cosima,S).

Nach der ersten Regel versucht PROLOG zunächst die Teilziele
verheiratet(cosima,Z) und bruder(Z,S) zu erfüllen. Dies gelingt nicht. Deshalb
wird diese Regel verlassen und der Schwager von Cosima wird nach der zweiten
Regel gesucht. Dazu versucht PROLOG die beiden Teilziele schwester(cosima,Z) und
verheiratet(Z,S) zu erfüllen, was schließlich auch gelingt.

Wie Sie gesehen haben, verfügt PROLOG bei der Suche nach Lösungen über einen
recht leistungsfähigen Grundalgorithmus. Entscheidungen, die in eine Sackgasse
führen, werden wieder rückgängig gemacht und es wird die nächste Möglichkeit
ausprobiert. Ein solches Vorgehen wird von den Informatikern Backtracking
(Rücksetzen) genannt. Dieses Backtracking wollen wir zum Schluß noch am letzten
Beispiel des vorigen Kapitels erläutern.

### Vier-Farben-Problem

Es ging dort um die Einfärbung eines
Gebietes mit drei Farben und wir hatten folgen- des Programm angegeben:

einfaerbung(F1,F2,F3,F4):-
farbe(F1), farbe(F2), farbe(F3), farbe(F4),
F1\=F2, F1\=F4, F2\=F3, F2\=F4, F3\=F4.
Wir fragen jetzt nach der Lösung des Problems
?- einfaerbung(F1,F2,F3,F4).

PROLOG will diese Anfrage mit Hilfe der Regel lösen. Dazu versucht es
nacheinander die Teilziele auf der rechten Seite zu erfüllen. Die ersten
Teilziele farbe(F1), farbe(F2), farbe(F3), farbe(F4) sind schnell erfüllbar,
indem alle Variablen F1 bis F4 mit rot belegt werden: F1=rot, F2=rot, F3=rot,
F4=rot. Damit sind alle Variablen, die in der obigen Regel vorkommen, belegt; es
ist eine vollständige Belegung der Variablenmenge erzeugt. Die nächsten
Teilziele F1\=F2, F1\=F4,... überprüfen nun, ob diese Variablenbelegungen das
Einfärbeproblem lösen. Schon die erste Überprüfung F1\=F2 scheitert, damit setzt
das Backtracking ein. Als erstes wird die letzte Entscheidung (F4=rot)
rückgängig gemacht; F4 wird wieder freigegeben und versuchsweise mit gelb bzw.
blau belegt. Da dies auch nicht zum Ziel führt, wird dann die vorletzte
Entscheidung (F3=rot) aufgehoben; die Variable F3 ist nun frei und es werden die
Belegungen probiert


F3=gelb,F3=gelb,F3=gelb,F3=blau,F3=blau,F3=blau,F4=rot
F4=gelb
F4=blau
F4=rot
F4=gelb
F4=blau


Sicher haben Sie schon bemerkt, dass diese Versuche für die Erfüllung des
Teilziels F1\=F2 alle zwecklos sind; PROLOG kommt durch braves Ausprobieren zum
selben Schluß und hebt nun auch die drittletzte Entscheidung (F2=rot) auf. Es
versucht die nächste Möglichkeit F2=gelb, F3=rot, F4=rot, und damit sind die
ersten fünf Teilziele der rechten Seite erfüllt. PROLOG wendet sich nun dem
sechsten Teilziel zu: F1\=F4. Mit der derzeitigen Variablenbelegung ist dieses
Teilziel nicht erfüllt, also beginnt wieder das Bachtracking. Die letzte
Entscheidung F4=rot wird aufgehoben und die nächste Möglichkeit, die die
Datenbasis anbietet, wird versucht: F4=gelb. Wir haben jetzt also die Belegung
F1=rot, F2=gelb, F3=rot, F4=gelb, die die ersten sechs Teilziele erfüllt. Diese
Belegung erfüllt allerdings noch nicht die beiden letzten Teilziele F2\=F4 und
F3\=F4. Durch nochmaliges Backtracking landen wir aber schließlich bei der
Belegung F1=rot, F2=gelb, F3=rot, F4=blau, die sämtliche Bedingungen erfüllt.

Wir veranschaulichen uns das Backtracking in einem Diagramm (siehe nächste
Seite). Es sind 4 Entscheidungen zu treffen, die Belegungen der Variablen F1,
F2, F3, F4. Bei jeder Entscheidung gibt es 3 Möglichkeiten, damit gibt es
insgesamt 34=81 Möglichkeiten, die in einem Baum (der hier von links nach rechts
wächst) dargestellt werden können. Hier ist nur ein Teil des Baumes gezeichnet.

Wir durchlaufen den Entscheidungsbaum von links nach rechts, die Entscheidung
für rot wird symbolisiert durch einen Weg nach schräg oben, gelb entspricht
waagrecht nach rechts, blau wird dargestellt durch schräg nach unten. Nach vier
Entscheidungen landet man ganz rechts bei einer Belegung der vier Variablen. Der
Rücknahme einer Entscheidung entspricht das Zurückgehen nach links bis zum
vorigen Knoten, wo dann eine neue Entscheidung getroffen werden kann. Wir waren
zunächst beim Endpunkt 'rrrr' angelangt, durch Überprüfen, Zurückgehen und
nochmaliges Versuchen kamen wir zu den Zuständen 'rrrg' und 'rrrb'; da diese
auch nicht die Bedingungen erfüllten, mussten wir noch eine Entscheidungsebene
zurückgehen usw. So können Sie im Baumdiagramm die Entscheidungen und das
Backtracking verfolgen, die uns schließlich zum Zustand 'rgrb' geführt haben.
Sie sehen, dass PROLOG zwölf Belegungen der vier Variablen ausprobieren musste,
bis es fündig wurde.


<!-- style="display: block; margin-left: auto; margin-right: auto; max-width: 350px;" -->
``````````
  .         .         .         ┏━━━ rrrr
  .         .         ┏━━━ r ━━━╋━━━ rrrg
  .         .         ┃         ┗━━━ rrrb
  .         .         ┃         .
  .         .         ┃         ┏━━━ rrgr
  .         ┏━━━ r ━━━╋━━━ g ━━━╋━━━ rrgg
  .         ┃         ┃         ┗━━━ rrgb
  .         ┃         ┃         .
  .         ┃         ┃         ┏━━━ rrbr
  .━━━ r ━━━┫         ┗━━━ b ━━━╋━━━ rrbg
  .         ┃         .         ┗━━━ rrbb
  .         ┃         .         .
  .         ┃         .         ┏━━━ rgrr
  .         ┗━━━ g ━━━━━━ r ━━━━╋━━━ rgrg
  .         .         .         ┗━━━ rgrb
  .         .         .         .
 F.1       F.2       F.3       F.4
``````````


Das Programm arbeitet nach dem Prinzip 'Erzeuge und Überprüfe' (generate and
test). Die ersten vier Teilziele farbe(F1), ...., farbe(F4) erzeugen die
Belegung sämtlicher Variablen, diese Belegungen werden durch die folgenden
Teilziele F1\=F2, ..., F3\=F4 überprüft.

3) Der Benutzer erfragt bei obigem Programm weitere Lösungen. Ergänzen Sie das
obige Baumdiagramm und verfolgen Sie das Backtracking bis zur nächsten Lösung.

4) Ergänzen Sie das Programm durch vier write-Befehle für die Variablen F1 bis
F4, die nach den ersten vier Teilzielen gesetzt werden. Damit lassen Sie die
Belegung der Variablen protokollieren. Vergleichen Sie mit dem Baumdiagramm.

5) Machen Sie das obige Programm schneller, indem Sie die Reihenfolge der
Teilziele verändern. Das Überprüfen sollte nicht erst am Schluß, sondern so bald
wie möglich geschehen.

Wenn Sie PROLOG bei seiner Suche zuschauen wollen, können Sie das im Trace-Modus
tun (siehe Anhang). Das Schöne bei PROLOG ist aber, dass sich der Programmierer
um die Organisation der Suche nicht kümmern muss. Für viele Probleme reicht
daher eine deklarative Beschreibung des Problems aus, die vielleicht durch eine
grobe Vorstellung des Suchvorgangs abgerundet wird. Keinesfalls ist es nötig,
sich bei jeder Anfrage Gedanken darüber zu machen, welche Instantiierungen und
Vergleiche bei der Bearbeitung vorgenommen werden.



## Rekursion

![recursion](img/recursion.png)

Hier sehen Sie ein Bild von Donald, dessen Stammbaum uns schon in den Kapiteln 1
und 2 beschäftigt hat. Donald hat sich vor dem Bild seines Vaters (Clemens)
fotografieren lassen. Als dieses Bild von Clemens vor etwa 25 Jahren aufgenommen
wurde, hat sich Clemens vor das Bild seines Vaters (Baldur) gestellt, der sich
vor 50 Jahren vor dem Bild seines Vaters (Adam) aufgestellt hatte. Auf diese
Weise ist in einem Bild eine ganze Galerie von Vorfahren eingefangen.

Um den Begriff 'Vorfahr' geht es in diesem Abschnitt. Schon einem kleinen Kind
können wir diesen Begriff schnell erklären:

Vorfahren sind die Eltern, Großeltern, Urgroßeltern, Ururgroßeltern,
Urururgroßeltern usw.

Wir erklären PROLOG zunächst diese Begriffe:

```prolog Großeltern
      grosselter(X,Y):- elter(X,Z), elter(Z,Y).
    urgrosselter(X,Y):- elter(X,Z), grosselter(Z,Y).
  ururgrosselter(X,Y):- elter(X,Z), urgrosselter(Z,Y).
urururgrosselter(X,Y):- elter(X,Z), ururgrosselter(Z,Y).
```

Schwierig ist nur die Verallgemeinerung, der Begriff 'Vorfahr', da PROLOG im
Gegensatz zu uns mit dem 'usw.' nichts anzufangen weiß. Dieses 'usw.' dient uns
dazu, die unendlich vielen Möglichkeiten einzufangen. In PROLOG benötigen wir
hierfür die Rekursion. Die rekursive Definition von 'Vorfahr' lautet:

vorfahr(X,Y):- elter(X,Y).
vorfahr(X,Y):- elter(X,Z), vorfahr(Z,Y).

Das heißt: Vorfahren von X sind die Eltern von X und die Vorfahren der Eltern
von X. Der Begriff 'Vorfahr' wird also teilweise durch sich selbst erklärt. Dass
dies trotzdem keine unsinnige, in sich kreisende Definition ist, sieht man am
besten, wenn man sie prozedural betrachtet.

Dann sind die obigen Regeln eine Anweisung an PROLOG:

* Wenn du einen Vorfahr von X suchen sollst, so suche zunächst die Eltern von X.
* Wenn du noch weiter nach Vorfahren suchen sollst, so suche ein Elternteil Z
  und von diesem einen Vorfahr.

Dieses Vorgehen wollen wir für eine spezielle Anfrage nachvollziehen. Es sei
gefragt:


## Listen

## Arithmetik

## NOT und CUT

``````````
                          ┏━━━━━┓
                          ┃  7  ┃
                          ┣━━━━━┫
                          ┃  6  ┃
  ┏━━━━━┓                 ┣━━━━━┫
  ┃  2  ┃                 ┃  5  ┃
  ┣━━━━━┫     ┏━━━━━┓     ┣━━━━━┫
  ┃  1  ┃     ┃  3  ┃     ┃  4  ┃
 ━┻━━━━━┻━━━━━┻━━━━━┻━━━━━┻━━━━━┻━
     a           b           c
``````````



# Vertiefung

# Anhang
