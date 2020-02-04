---
title: Übersicht über die lync Server 2013-Webkonferenzen
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
ms.openlocfilehash: de63cb5bf2578359d012cda72b07b8fc7f62880d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Übersicht über Webkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Mit Webkonferenzen können Benutzer während ihrer Konferenzen Dokumente wie PowerPoint-Präsentationen Freigeben und daran zusammenarbeiten. Darüber hinaus können Benutzer ihren gesamten Desktop oder einen Teil davon in Echtzeit freigeben, sodass es den Anschein hat, als ob die Personen in der Konferenz um dieselbe Tabelle in der Besprechung versammelt sind.

<div>

## <a name="whiteboard-and-annotations"></a>Whiteboard und Anmerkungen

Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Die Whiteboard-Funktion verbessert die Zusammenarbeit, indem Besprechungsteilnehmer die Möglichkeit erhalten, Ideen zu diskutieren, ein Brainstorming durchzuführen, Notizen zu machen, usw.

</div>

<div>

## <a name="polling"></a>Abruf

Das Polling-Feature verbessert die Zusammenarbeit, indem es Referenten ermöglicht, die Einstellungen der Teilnehmer schnell festzulegen. In Onlinebesprechungen und Unterhaltungen können Referenten mithilfe von Umfragen anonyme Antworten von Teilnehmern sammeln. Alle Referenten können die Ergebnisse sehen und entweder die Ergebnisse ausblenden oder alle Teilnehmer anzeigen.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Anwendungsfreigabe und Desktop Freigabe

Während einer Konferenz können Sie Ihren gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Neben der Anzeige des Inhalts können andere Teilnehmer der Konferenz auch die Steuerung Ihres Bildschirms anfordern und mit der Berechtigung mit dem Inhalt interagieren (einschließlich Scrollen und bearbeiten).

<div>


> [!NOTE]  
> Teilnehmer, die die Konferenz anzeigen, können auch die Freigabe von Inhalten während der Besprechung übernehmen und beginnen.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint-Freigabe

In lync 2010 wurden PowerPoint-Präsentationen auf eine von zwei Arten angezeigt. Für Benutzer, die lync 2010 ausführen, wurden PowerPoint-Präsentationen mit dem PowerPoint 97-2003-Format angezeigt und mit einer eingebetteten Kopie des PowerPoint-Viewers angezeigt. Für Benutzer, die lync Web App ausführen, wurden PowerPoint-Präsentationen in dynamische HTML-Dateien konvertiert und dann mithilfe einer Kombination dieser angepassten DHTML-Dateien und Silverlight angezeigt. Obwohl dies in der Regel effektiv ist, hat dieser Ansatz einige Einschränkungen:

  - Der eingebettete PowerPoint Viewer (der die optimale Anzeigefunktionalität bereitgestellt hat) steht nur auf der Windows-Plattform zur Verfügung.

  - Viele mobile Geräte (darunter einige der beliebtesten Mobiltelefone) unterstützen Silverlight nicht.

  - Der PowerPoint Viewer und der DHTML/Silverlight-Ansatz unterstützen nicht alle Features (wie Folienübergänge und eingebettete Videos), die in den neueren Versionen von PowerPoint zu finden sind.

Zur Behebung dieser Probleme und zur Verbesserung der allgemeinen Benutzerfreundlichkeit von Benutzern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office Web Apps und den Office Web Apps-Server für die Behandlung von PowerPoint-Präsentationen. Dieser neue Ansatz bietet unter anderem folgende Vorteile:

  - Displays mit höherer Auflösung und bessere Unterstützung für PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.

  - Zusätzliche Mobile Geräte, um auf diese Präsentationen zuzugreifen. Das liegt daran, dass lync Server 2013 Standard DHTML und JavaScript zum Übertragen von PowerPoint-Präsentationen anstelle von benutzerdefinierten DHTML-und Silverlight-Anwendungen verwendet.

  - Benutzer mit den entsprechenden Berechtigungen, um unabhängig von der Präsentation in einer PowerPoint-Präsentation zu scrollen. Wenn beispielsweise Ken Myers seine Bildschirmpräsentation vorstellt, kann Pilar Ackerman jede gewünschte Folie sehen, ohne die Präsentation von Ken zu beeinflussen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

