---
title: Übersicht über Webkonferenzen in Lync Server 2013
TOCTitle: Übersicht über Webkonferenzen in Lync Server 2013
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425913(v=OCS.15)
ms:contentKeyID: 49293794
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über Webkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Über die Webkonferenzfunktion können Benutzer während einer Konferenz Dokumente freigeben und gemeinsam verwenden, z. B. PowerPoint-Präsentationen. Zusätzlich können Benutzer den gesamten Desktop oder Teile des Desktops in Echtzeit freigeben. So können die Konferenzteilnehmer gemeinsam Inhalte betrachten, als befänden sie sich am selben Tisch.

## Whiteboard und Anmerkungen

Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Die Whiteboardfunktion verbessert die Zusammenarbeit, indem Besprechungsteilnehmer die Möglichkeit erhalten, Ideen zu diskutieren, ein Brainstorming durchzuführen, Notizen zu machen usw.

## Abstimmungsfunktion

Mit der Abstimmungsfunktion wird die Zusammenarbeit verbessert, da Referenten umgehend die Vorlieben bzw. Meinung der Teilnehmer ermitteln können. Während einer Onlinebesprechung oder -unterhaltung können Referenten mit dieser Funktion anonyme Antworten der Teilnehmer sammeln. Die Ergebnisse werden allen Referenten angezeigt, und die Referenten können entscheiden, ob die Ergebnisse auch für die Teilnehmer sichtbar sein sollen.

## Anwendungs- und Desktopfreigabe

Während einer Konferenz können Sie Ihren gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Andere Teilnehmer der Konferenz können nicht nur die Inhalte sehen, sondern auch die Kontrolle über Ihren Bildschirm anfordern und mit Ihrer Erlaubnis mit den Inhalten interagieren (einschließlich Bildlauf und Bearbeitung).


> [!NOTE]
> Teilnehmer, die bei der Konferenz nur zusehen, können ebenfalls die Kontrolle übernehmen und während der Besprechung Inhalte freigeben.



## PowerPoint-Freigabe

In Lync 2010konnten PowerPoint-Präsentationen auf zwei Arten angezeigt werden. Für Benutzer mit Lync 2010 wurden PowerPoint-Präsentationen im PowerPoint 97-2003-Format mithilfe einer eingebetteten Kopie des PowerPoint Viewer angezeigt. Für Benutzer mit Lync Web App wurden PowerPoint-Präsentationen in dynamische HTML-Dateien konvertiert und mithilfe einer Kombination dieser angepassten DHTML-Dateien mit Silverlight angezeigt. Dieser Ansatz war zwar grundsätzlich effizient, unterlag aber Einschränkungen:

  - Der eingebettete PowerPoint Viewer (mit dem die Anzeigeerfahrung optimal war) ist nur auf der Windows-Plattform verfügbar.

  - Viele mobile Geräte (einschließlich einiger beliebter Handymodelle) unterstützen Silverlight nicht.

  - Der Ansatz mit PowerPoint Viewer bzw. DHTML/Silverlight unterstützt nicht alle Funktionen neuerer Versionen von PowerPoint (z. B. Folienübergänge und eingebettete Videos).

Um diese Probleme zu lösen und die allgemeine Erfahrung der Benutzer als Referent oder Zuhörer bei PowerPoint-Präsentationen zu verbessern, verwendet Lync Server 2013Office Web Apps den Office Web Apps-Server für PowerPoint-Präsentationen. Neben weiteren Vorteilen ermöglicht dieser Ansatz Folgendes:

  - Hochauflösende Displays und bessere Unterstützung von PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.

  - Zusätzliche mobile Geräte zum Zugriff auf diese Präsentationen. Dies liegt daran, dass Lync Server 2013 Standard-DHTML und JavaScript anstelle von angepasstem DHTML und Silverlight verwendet, um PowerPoint-Präsentationen zu übertragen.

  - Benutzer mit entsprechenden Berechtigungen können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Herr Myer beispielsweise seine Bildschirmpräsentation ablaufen lässt, kann Frau Ackerman sich eine beliebige Folie ansehen, ohne Herrn Myers Präsentation zu beeinträchtigen.

