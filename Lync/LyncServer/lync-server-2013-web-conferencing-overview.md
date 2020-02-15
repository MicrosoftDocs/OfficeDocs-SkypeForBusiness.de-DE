---
title: Übersicht über lync Server 2013-Webkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253141be23396ccce12a52123d907b3523a30b03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Übersicht über Webkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Über die Webkonferenzfunktion können Benutzer während einer Konferenz Dokumente freigeben und gemeinsam verwenden, z. B. PowerPoint-Präsentationen. Zusätzlich können Benutzer den gesamten Desktop oder Teile des Desktops in Echtzeit freigeben. So können die Konferenzteilnehmer gemeinsam Inhalte betrachten, als befänden sie sich am selben Tisch.

<div>

## <a name="whiteboard-and-annotations"></a>Whiteboard und Anmerkungen

Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Die Whiteboardfunktion verbessert die Zusammenarbeit, indem Besprechungsteilnehmer die Möglichkeit erhalten, Ideen zu diskutieren, ein Brainstorming durchzuführen, Notizen zu machen usw.

</div>

<div>

## <a name="polling"></a>Abrufen

Mit der Abstimmungsfunktion wird die Zusammenarbeit verbessert, da Referenten umgehend die Vorlieben bzw. Meinung der Teilnehmer ermitteln können. Während einer Onlinebesprechung oder -unterhaltung können Referenten mit dieser Funktion anonyme Antworten der Teilnehmer sammeln. Die Ergebnisse werden allen Referenten angezeigt, und die Referenten können entscheiden, ob die Ergebnisse auch für die Teilnehmer sichtbar sein sollen.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Anwendungs- und Desktopfreigabe

Während einer Konferenz können Sie den gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Andere Teilnehmer der Konferenz können nicht nur die Inhalte sehen, sondern auch die Kontrolle über Ihren Bildschirm anfordern und mit Ihrer Erlaubnis mit den Inhalten interagieren (einschließlich Bildlauf und Bearbeitung).

<div>


> [!NOTE]  
> Teilnehmer, die bei der Konferenz nur zusehen, können ebenfalls die Kontrolle übernehmen und während der Besprechung Inhalte freigeben.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint-Freigabe

In lync 2010 PowerPoint-Präsentationen wurden auf eine von zwei Arten angezeigt. Für Benutzer, die lync 2010 durchführen, wurden PowerPoint-Präsentationen im PowerPoint 97-2003-Format angezeigt und mit einer eingebetteten Kopie des PowerPoint-Viewers angezeigt. Für Benutzer, die lync Web App durchführen, wurden PowerPoint-Präsentationen in dynamische HTML-Dateien konvertiert und dann mit einer Kombination dieser angepassten DHTML-Dateien und Silverlight angezeigt. Obwohl dieser Ansatz generell effizient ist, gibt es einige Einschränkungen:

  - Der eingebettete PowerPoint Viewer (der das optimale Anzeigeerlebnis bereitgestellt hat) ist nur auf der Windows-Plattform verfügbar.

  - Viele mobile Geräte (darunter einige der beliebtesten Mobiltelefone) unterstützen Silverlight nicht.

  - Der PowerPoint Viewer und der DHTML/Silverlight-Ansatz unterstützen nicht alle Features (solche Folienübergänge und eingebettete Videos), die in den neueren Versionen von PowerPoint gefunden werden.

Um diese Probleme zu beheben und die Gesamterfahrung von Benutzern zu verbessern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office-Webanwendungen und den Office-webapps-Server zur Behandlung von PowerPoint-Präsentationen. Neben weiteren Vorteilen ermöglicht dieser Ansatz Folgendes:

  - Hochauflösende Displays und bessere Unterstützung von PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.

  - Zusätzliche mobile Geräte zum Zugriff auf diese Präsentationen. Der Grund ist, dass Lync Server 2013 anstatt angepasster DHTML-Dateien und Silverlight Standard-DHTML und JavaScript zum Übertragen von PowerPoint-Präsentationen verwendet.

  - Benutzer mit entsprechenden Berechtigungen können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Herr Myer beispielsweise seine Bildschirmpräsentation ablaufen lässt, kann Frau Ackerman sich eine beliebige Folie ansehen, ohne Herrn Myers Präsentation zu beeinträchtigen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

