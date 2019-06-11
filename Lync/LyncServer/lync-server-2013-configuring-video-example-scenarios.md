---
title: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Konfigurieren von Video Beispielszenarien für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Lync 2013 fügt neue Videofeatures zur Unterstützung von 1920 x 1080 Full High Definition (HD) Video-und Galerieansicht-Video hinzu. Messungen, die auf Kundendaten basieren, zeigen, dass die typische Videobandbreite im Vergleich zu lync 2010 nur geringfügig zugenommen hat, die maximale Bandbreite des Videostreams jedoch aufgrund der Full-HD-Unterstützung zugenommen hat (Einzelheiten finden Sie im Abschnitt "Nutzung des Media Traffic-Netzwerks" in [ Netzwerkbandbreite-Anforderungen für den Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)) Daher möchten Administratoren möglicherweise die Videobandbreite für bestimmte Benutzer (wie Benutzer in einer Zweigstelle, die eine geringere Netzwerkkapazität aufweisen) einschränken und dabei helfen, die bestmögliche Videoqualität für andere Benutzer (wie Führungskräfte) zu gewährleisten.

Die folgende Tabelle enthält eine Liste der empfohlenen Einstellungen für die Konfiguration von Video für verschiedene Netzwerkkapazitäten. Diese Einstellungen beschränken einige Benutzerszenarien auf das Senden und empfangen von Videos mit höherer Auflösung (siehe Spalte ganz rechts). Die Mindesteinstellungen führen dazu, dass Gallery-Video aufgrund der geringen maximalen Netzwerkbandbreite für den Empfang nicht verfügbar ist.

### <a name="recommended-video-settings"></a>Empfohlene Video Einstellungen

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>Erwartete Videoauflösung für Video in guter Qualität</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Optimal</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Peer-to-Peer: bis zu 1920 x 1080 Videoauflösung</p>
<p>Katalogansicht: bis zu 2 1920 x 1080 Videos oder Videos mit mehreren kleineren Auflösungen</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Peer-to-Peer: bis zu 1280 x 720 Videoauflösung</p>
<p>Galerieansicht: Videos mit bis zu 5 640 x 360 Auflösung</p></td>
</tr>
<tr class="odd">
<td><p>Mittel</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Peer-to-Peer: bis zu 960 x 540 Videoauflösung</p>
<p>Galerieansicht: Videos mit bis zu 5 424 x 240 Auflösung</p></td>
</tr>
<tr class="even">
<td><p>Mindestens</p></td>
<td><p>True</p></td>
<td><p>Falsch</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Peer-to-Peer: bis zu 424 x 240 Videoauflösung</p>
<p>Katalogansicht: nicht verfügbar</p></td>
</tr>
</tbody>
</table>


Sie können die Informationen aus der vorstehenden Tabelle verwenden, um die neuen HD-Video-und-Galerie-Videokonferenz Features für einige Benutzer in Ihrer Organisation bereitzustellen, während Sie anderen Videoauflösungen ermöglichen.

Im folgenden Beispiel werden die neuen Videofeatures mit der höchsten Videoqualität, die nur Führungskräften zur Verfügung stehen, vom Administrator ausgerollt. Für Mitarbeiter in einer Remote-Zweigstelle, die über eine niedrige Netzwerkkapazität verfügt, wird nur die Mindesteinstellung der vorhergehenden Tabelle bereitgestellt. Für alle anderen Mitarbeiter wird die Einstellung "gut" aus der vorhergehenden Tabelle bereitgestellt.

Um die neuen Funktionen für die Führungskräfte bereitzustellen, erstellt der Administrator eine konferenzrichtlinie mit dem Namen ExecutiveVideo. Diese konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 8000 kBit/s eingestellt

  - TotalReceiveVideoBitRateKB ist auf 8000 kBit/s eingestellt

  - AllowMultiview ist auf "true" festgelegt.

  - EnableMultiviewJoin ist auf "true" festgelegt.

Für Mitarbeiter in der Zweigstelle erstellt der Administrator eine konferenzrichtlinie mit dem Namen BranchOfficeVideo. Diese konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 350 KBit/s eingestellt

  - TotalReceiveVideoBitRateKB ist auf 350 KBit/s eingestellt

  - AllowMultiview ist auf "true" festgelegt.

  - EnableMultiviewJoin ist auf "false" festgelegt.

Für alle anderen Mitarbeiter erstellt der Administrator eine konferenzrichtlinie mit dem Namen StandardVideo. Diese konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 2500 Kbit/s eingestellt

  - TotalReceiveVideoBitRateKB ist auf 2500 Kbit/s eingestellt

  - AllowMultiview ist auf "true" festgelegt.

  - EnableMultiviewJoin ist auf "true" festgelegt.

Der Administrator weist Benutzer Konferenzrichtlinien wie folgt zu:

  - Die ExecutiveVideo-konferenzrichtlinie wird den Führungskräften zugewiesen.

  - Die BranchOfficeVideo-konferenzrichtlinie wird allen Mitarbeitern in der Zweigstelle zugewiesen.

  - Die StandardVideo-konferenzrichtlinie wird allen anderen Mitarbeitern zugewiesen.

Diese Konferenzrichtlinien Zuweisungen führen zu der folgenden Benutzeroberfläche:

  - Alle Konferenzen, die von einer beliebigen Benutzer-Galerieansicht unterstützt werden, aber die Mitarbeiter in der Zweigstelle können die Katalogansicht nicht finden.

  - Für zwei-oder Mehrparteienkonferenzen können Führungskräfte 1920 x 1080 Full-HD-Video senden, wenn deren Hardware-und Netzwerkverbindung dies unterstützt, und Sie können 1920 x 1080 Full-HD-Video empfangen, wenn die anderen Teilnehmer dies unterstützen.

  - Mitarbeiter, die keine Führungskräfte sind, erleben niedrigere Auflösungen als die Führungskräfte in ihren zwei-oder Mehrparteienkonferenzen, erhalten aber trotzdem eine gute Auflösung.

  - Mitarbeiter, die in der Zweigstelle sind, erhalten gute Videoqualität bei Anrufen mit zwei Teilnehmern, wenn lync die Standardgröße des Videofensters anzeigt. Wenn das lync-Fenster jedoch auf Vollbild maximiert ist, nimmt die Videoauflösung nicht zu. Bei Konferenzen mit mehreren Teilnehmern werden die Mitarbeiter in der Zweigstelle nur ein aktives Video sehen.

</div>

<span> </span>

</div>

</div>

</div>

