---
title: "An Introduction to CI/CD (German)"
date: 2022-04-16
draft: false
description: "An introduction to CI/CD in german (english article following soon)"
tags: ["de", "ci/cd", "automation", "introduction", "setup"]
author: "UniversumGames"
lang: "de"
---

In diesem Artikel wird das Konzept der häufig verwendeten Abkürzung
\"CI/CD\" vorgestellt. Sie ist häufig in Kombination zu agiler
Softwareentwicklung zu finden, ist aber keine Voraussetzung für diese.
Unter \"CI/CD\" versteht man eine Abwandlung eines Teilbereichs der
Softwareentwicklung durch die Automatisierung von essentiellen Schritten
bei der Verbreitung des fertigen Softwareprojekts. Die Abkürzung besteht
hier aus zwei Teilen: wobei \"CI\" ein fester Bestandteil und
Voraussetzung von \"CD\" ist; sie werden jedoch Vorzugsweise in der
anfänglich gegebenen Kombination genannt.

# Das klassische Modell

In der klassischen Softwareentwicklung, die inzwischen kaum noch
vertreten ist, wird das Wasserfall Modell verwendet bei der das
Softwareprojekt viele verschiedene Phasen durchläuft. Diese Phasen sind
Aufgabentechnisch klar voneinander getrennt und überschneiden sich nur
gering. Die Oberbegriffe dieser Phasen sind in der Regel: Planung,
Entwicklung, Testen und Abgabe.

Bezogen auf das Projekt steht am Anfang die vollständige Planung des
Projektes, hier werden auch bereits alle Feinheiten definiert. Die
detaillierte Planung wird in enger Absprache oder auch Zusammenarbeit
mit dem Kunden erstellt. Dies ist normalerweise das letzte mal, dass der
Kunde auf das Produkt Einfluss nimmt, bis das Projektprodukt am Ende
übergeben wird. Nach der Planung kommt eine lange Entwicklungsphase in
der das Produkt seine Form erhält, es wird sich penibel an den Plan
gehalten, jedoch bekommt weder der Kunde das Produkt zu sehen noch
können größere Änderungen einfach realisiert werden, da weniger in
abtrennbaren Modulen und mehr das gesamte Produkt von vorne nach hinten
abarbeitet wird. Nachdem das Projekt fertig entwickelt worden ist, folgt
eine Testphase bei der Mitarbeiter der \"Quality Assurance\" (QA) das
Softwarepaket auf Fehler überprüfen und diese umständlich, durch die
große zeitliche Trennung, an die Entwickler zurückgeben. Der
beschriebene Kreislauf zwischen QA und den Entwicklern wird so lange
durchgeführt bis keine Fehler mehr gefunden werden können.

Zuletzt, nach der langen Entwicklungsdauer und vielen Testdurchläufen,
bekommt der Kunde einen Einblick in das fertige Projekt. Im Idealfall
hat der Kunde keine Beschwerden mehr vorzuzeigen und das Projekt kann
von der Entwicklungsfirma im Kundensystem installiert werden.

Dieser Prozess, von der Planung bis hin zum vollständig getesteten
Produkt, dauert, im Vergleich zur im nächsten Kapitel besprochenen
Methode, lange, ohne in der Zwischenzeit größere Absprachen mit dem
Kunden zu führen oder einen Ansatz eines vorzeigbaren Produktes auf der
Hand zu haben. In unserer heutigen Zeit, in der alles schnell
fertiggestellt werden muss und einfach auf Änderungswünsche eingegangen
werden können muss, ist diese Art der Softwareentwicklung in den meisten
Fällen ungeeignet.

# Die moderne, agile Variante

Heutzutage wird eine andere Variante der Softwareentwicklung verwendet.
Die agile Softwareentwicklung ist ausgelegt für ändernde
Produktanforderungen im Laufe der Entwicklungsphase. Anstelle von klar
getrennten seriellen Blöcken, der Planung, Entwicklung, Test und
Installation, gehen diese in der agilen Entwicklung ineinander über
beziehungsweise laufen größtenteils parallel ab.

Auch in der agilen Entwicklung können Reste dieser strikten Grenzen, der
seriellen Phasen sowie die Einteilung des Entwicklungsablauf
wiedergefunden werden. Am Anfang, wie auch im Wasserfall Modell, steht
die Planung des Projektes, hier werden jedoch nur wenige Details über
die Umsetzung definiert. In der ersten Planungsphase geht es
hauptsächlich um das Erstellen eines groben Überblicks von dem
gewünschten Produkt. Hier werden meist vor allem besondere
Detailansprüche nicht klar definiert. Diese grobe Planung wird später in
einem vergleichsweise kleinen Entwicklerteam von meist weniger als zehn
Personen verwendet um ein so genanntes \"Minimum viable Product\" (MVP)
zu erstellen, ein Produkt, welches die wichtigsten Funktionen bietet und
dem Kunden ein erstes \"Proof of concept\" bieten kann. Bereits in der
Erstellung dieses MVP werden zahlreiche Unterschritte getätigt um
einfach, schnell und übersichtlich um in dem kleinen Team das Produkt zu
entwickeln. Die Entwickler und Tester treffen sich regelmäßig als
vollständige Gruppe inklusive Leiter, welcher im engen Kontakt mit dem
Kunden steht, um weitere Details und Features zu besprechen, welche bis
zum nächsten Treffen entwickelt werden sollen. Unabhängig von diesen
Großrunden stehen die Entwickler und Tester im ständigen und engen
Kontakt um gegenseitig Hilfestellungen zu bieten, den Code aufeinander
abzustimmen sowie Fehler gemeinsam zu lösen. Diese enge Zusammenarbeit
zwischen Entwicklung, Test sowie Kunde hat einen entscheidenden Vorteil
gegenüber der Wasserfall Methode. Da das Produkt nicht schon am Anfang
vollständig durchgeplant worden ist, kann relativ einfach auf das
Produkt Einfluss genommen und so an geänderte Anforderungen angepasst
werden.

Das Prinzip der CI/CD greift direkt in den Ablauf der agilen Entwicklung
ein und ist eine Fortsetzung dieses Prinzips.

# Die Grundzüge von CI/CD

Kurzgesagt bezeichnet die Abkürzung \"CI/CD\" einen automatisierten Weg
um ein Softwareprojekt zu testen, zusammenzustellen und eventuell zu
installieren bzw. auszuliefern.

Die Abkürzung kann in drei Abschnitte unterteilt werden, \"CI\" -
Continous Integration, sowie \"CD\" - Continous delivery/Continous
deployment, wobei es keinen allgemeinen Konsens gibt, was mit \"CD\"
gemeint sein soll.

\"Continous intergration\", der Englische Name der Abkürzung \"CI\",
bezeichnet den Prozess des ständigen automatisierten Testens. Dies setzt
voraus, dass das Entwicklerteam Testfälle aufgesetzt hat und diese
ständig dem Soll-Entwicklungsstand entsprechend aktualisiert. In diesem
Schritt wird das Projekt kompiliert und anhand von vorgefertigten
Testfällen und Testumgebungen automatisch getestet. Bei einem
erfolgreichen Durchlauf aller Tests wird die Software zur manuellen
Verbreitung bzw. Installation bereitgestellt. Hiermit endet der
Aufgabenbereich der CI. Dort wo die Continous Integration mit der
Automatisierung endet geht CD, je nach Definition, ein bis zwei Schritte
weiter.

\"Continous delivery\", der nächste Schritt der CI/CD Kette, erhält beim
erfolgreichen Durchlaufen der Testfälle die Software und führt selbst
weitere Tests durch, welche in einer Umgebung und mit Daten durchgeführt
werden, die der Produktion sehr nahe komme. Beispielsweise werden
Datenbanken mit mehr als nur Platzhaltern gefüllt und andere notwendigen
der Realtität nachahmend aufgesetzte Komponenten werden angebunden. So
sollen so viele Fehler wie möglich erkannt werden, bevor es an den
Kunden als nächste Iteration (kleinere Version/kleineres Update)
abgegeben bzw. auf dessen Server installiert wird. Sind die Tests
erfolgreich, wird die aktualisierte Software auf einen Produktion-Server
geladen und gegebenenfalls nötige Änderungen an Konfigurationen und
ähnlichem werden durchgeführt.

\"Continous deployment\" geht einen Schritt weiter. Hier wird der letzte
menschliche Handgriff, das finale Veröffentlichen und einbinden in die
bestehende Netzwerkstruktur, ebenfalls automatisiert. Identisch zum
Continous delivery werden die intensivieren Tests durchgeführt, das
Produkt wird auf den ersten nicht-kritischen Server installiert und,
hier anders, automatisch nach erfolgreicher Installation in das Netzwerk
eingebunden und nach kritischen Problemen direkt nach der Einbindung
geprüft.

# Der wechsel zu CI/CD

## Notwendige Änderungen

Unabhängig von der jeweiligen Definition von CD greift das Prinzip der
CI/CD in die Entwicklung ein und verändert grundlegend das
Programmierern im Alltag. Betrachtet man beide Aspekte getrennt,
beeinflusst CI die eigentliche Entwicklung währenddessen CD das Arbeiten
der Quality Assurance (QA) und der Operations (Ops) vollständig
verändert und zu weiten Teilen sogar abschafft.

Die Nutzung einer CI/CD Toolchain erfordert eine spezielle
Vorgehensweise in der Programmierung an vielen kleinen Stellen. Die
Grundbedingung für das Aufsetzen der Toolchain ist das verwenden einer
Versionskontrolle wie Git, bei der die Entwickler regelmäßig, teilweise
mehrmals täglich, ihre Änderungen auf einen gemeinsamen Server committen
(Anglizismus für eng. \"(to) commit\"), sodass auch für kleine
Änderungen die CI das Projekt überprüfen kann und die Zusammenarbeit im
Team gefördert wird. Desweiteren werden, um die Tests durchzuführen,
Testfälle benötigt, die das gesamte Projekt abdecken und abtesten
sollten. Bei Änderungen an der Funktionsweise der Software ist es
selbstverständlich nötig die Testfälle dem gewünschten Ergebnis
anzupassen. Diese Testfälle müssen jedoch nicht unbedingt existieren,
gerade bei kleinen Projekten, die vielleicht in der Freizeit erstellt
werden, reicht vielleicht das erfolgreiche Kompilieren als einziger
Testfall aus um schnellstmöglich an ein MVP zu kommen. Mit dem Umstellen
des Committen und dem Erstellen von Testfällen sind die Grundbedingen
geschaffen um ein CI anbinden zu können.

Für CD übernehmen die Entwickler Teile der QA und Ops und werden zu so
genannten DevOps, kurz für Developer und Operations. Sie passen die
Toolchain der CI/CD ständig dem derzeitigen Entwicklungsstand an, sodass
das das Aufgabengebiet der QA, das Testen des Systems, zu großen Teilen
durch die automatisierten Tests wegfällt und das der Operations, das
Installieren der neuen Systeme, vollständig durch die Continous
development abgenommen wird. Dafür sind gute Kenntnisse der gesamten
Systemstruktur, deren Betriebssysteme und die Zusammenarbeit der
einzelnen Komponenten von den DevOps essenziell.

## Vorteile von CI/CD

Das implementieren einer CI/CD Toolchain hat viele Vorteile,
insbesondere der klassischen Entwicklung gegenüber. Richtig
implementiert kann solch eine Toolchain Unmengen an Geld sparen. Durch
das Einführen von Testfällen, die das gesamte System abdecken und das
automatisierte Installieren eines Systems können viele Stunden
eingespart werden, da nicht mehr zahlreiche Mitarbeiter das Projekt
durchtesten müssen und keine stundenlangen Nachtschichten für die
Installation mehr bezahlt werden müssen. Stattdessen können diese
Aufgaben automatisiert oder mittels eines einfachen Knopfdrucks
durchgeführt werden. Die Arbeitsweise von CI/CD fördert mehr
Kollaboration zwischen den Entwicklern und den restlichen
Teammitgliedern, welches zu mehr Freude und wieder zu mehr Produktivität
führen kann. Zuletzt kann das aufsetzen von Continous Delivery und
automatische Installieren der neuen Version bei jedem Commit den Kontakt
zu den Benutzern fördern und schneller Feedback eingesammelt werden.

## Risiken und Probleme

Jedoch kann CI/CD auch ein paar Nachteile und Probleme mit sich führen.
Es ist nicht immer trivial und einfach eine CI/CD Toolchain aufzusetzten
und erst recht in ein bereits existierendes größeres Projekt
einzubinden. Auch wenn die Toolchain viel Zeit einsparen kann müssen,
gerade wenn das Projekt größere Ausmaße hat oder annimmt, zwischendurch
einige Zeit investiert werden um die Toolchain aufzusetzten und in Stand
zu halten. Das Umstellen der Kollaboration zwischen den Entwicklern und
im Team kann schief laufen, wenn keiner im Team bereits Erfahrung
sammeln konnte noch enger verknüpft im Team zu arbeiten und anständige
Commits zu schreiben, kann der gesamte Prozess sehr anstrengend sein und
sogar länger Dauern als die vorherig verwendete Methode. Zuletzt, je
nach Kundenstruktur und Projekt, bietet es sich in manch einem Fall
nicht an eine CI/CD Pipeline vollständig zu implementieren, da entweder
die Berechtigungen des Kunden oder das eingesetzte Gebiet zu groß ist
umd den Überblick behalten zu können und alle Eventualitäten einplanen
zu können.

## Daraus folgende \"Best Practices\"

Glücklicherweise gibt es für die meisten dieser Probleme bereits gut
Ansätze um diese Probleme zu verhindern, so genannte \"Best Practices\"
die die Zusammenarbeit mit der CI/CD so einfach wie möglich gestalten.
Wenn sich mit dem Grad des Einflussbereichs auseinandergesetzt wurde und
klar ist, inwieweit eine CI/CD Toolchain sinnvoll und inwieweit sie
einsetzbar ist, kommt es nun auf den Entwicklungsstand des derzeitigen
Projektes an. Falls das Projekt bereits einen größeren Umfang erreicht
haben sollte und schon weit fortgeschritten ist, kann ein Umstieg auf
eine CI/CD Toolchain nicht mehr sinnvoll sein, falls doch sollte die
Toolchain schrittweise aufgesetzt und erprobt werden. So sollte das Team
beispielsweise den Umgang mit der Verflochtenen Arbeitsweise der agilen
Entwicklung verinnerlicht haben. Steht das Projekt noch am Anfang und
dem Team ist die Entwicklung mit CI/CD nicht unbekannt, kann die
Toolchain auch zu Anfang schon aufgesetzt werden und mit dem Projekt
gemeinsam wachsen.

Wie auch schon zuvor angedeutet ist es sinnvoll, um eine derartige
Toolchain verwenden zu können, die Mitarbeiter des Teams angemessen zu
schulen, um sich in der agilen Entwicklung, im Team und der CI/CD
einfach bewegen zu können und Hand in Hand miteinander arbeiten zu
können.
