---
title: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien'
description: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575141"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Konfigurieren von Video Beispielszenarien für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Lync 2013 fügt neue Videofunktionen zur Unterstützung von 1920 x 1080 Full High Definition (HD) Video und Gallery View Video hinzu. Messungen basierend auf Kundendaten zeigen, dass die typische Videobandbreite im Vergleich zu lync 2010 nur geringfügig zugenommen hat, die maximale Bandbreite an Videostreams jedoch aufgrund der vollständigen HD-Unterstützung zugenommen hat (Ausführliche Informationen finden Sie im Abschnitt "Verwendung des Medien Verkehrs Netzwerks" unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Deshalb sollten Administratoren die Videobandbreite für bestimmte Benutzer beschränken (z. B. Benutzer in einer Zweigniederlassung, die über weniger Netzwerkkapazität verfügen) und dadurch die bestmögliche Videoqualität für andere Benutzer (z. B. Führungskräfte) sicherstellen.

Die folgende Tabelle enthält eine Aufstellung der empfohlenen Einstellungen zum Konfigurieren von Video für verschiedene Netzwerkkapazitäten. Mit diesen Einstellungen wird für bestimmte Benutzerszenarien das Senden und Empfangen von Videos mit höherer Auflösung beschränkt (siehe die Spalte ganz rechts). Mit der Mindesteinstellung ist die Katalogansicht aufgrund der niedrigen maximalen Netzwerkbandbreite beim Empfangen nicht verfügbar.

### <a name="recommended-video-settings"></a>Empfohlene Videoeinstellungen

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
<td><p>Peer-zu-Peer: Videoauflösung von bis zu 1920 x 1080</p>
<p>Katalogansicht: Bis zu 2 Videos mit einer Auflösung von 1920 x 1080 oder mehrere Videos mit niedrigerer Auflösung</p></td>
</tr>
<tr class="even">
<td><p>Gut</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Peer-zu-Peer: Videoauflösung von bis zu 1280 x 720</p>
<p>Katalogansicht: Bis zu fünf Videos mit einer Auflösung von 640 x 360</p></td>
</tr>
<tr class="odd">
<td><p>Mittel</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Peer-zu-Peer: Videoauflösung von bis zu 960 x 540</p>
<p>Katalogansicht: Bis zu fünf Videos mit einer Auflösung von 424 x 240</p></td>
</tr>
<tr class="even">
<td><p>Minimum</p></td>
<td><p>Richtig</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Peer-zu-Peer: Videoauflösung von bis zu 424 x 240</p>
<p>Katalogansicht: Nicht verfügbar</p></td>
</tr>
</tbody>
</table>


Mithilfe der Informationen in der vorstehenden Tabelle können Sie die neuen HD-Video- und Katalogansicht-Videokonferenzfeatures für bestimmte Benutzer in Ihrer Organisation und andere Videoauflösungen für andere Benutzer verwenden.

Im folgenden Beispiel führt der Administrator die neuen Videofeatures mit der höchsten Videoqualität nur für Führungskräfte ein. Für Mitarbeiter in einer Remotezweigniederlassung mit niedriger Netzwerkkapazität wird nur die Minimumeinstellung aus der vorstehenden Tabelle bereitgestellt. Für alle anderen Mitarbeiter wird die Einstellung "Gut" aus der vorstehenden Tabelle bereitgestellt.

Für das Rollout der neuen Features für die Führungskräfte erstellt der Administrator die Konferenzrichtlinie ExecutiveVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 8000 KBit/s festgelegt

  - TotalReceiveVideoBitRateKB ist auf 8000 KBit/s festgelegt

  - AllowMultiview ist auf True festgelegt

  - EnableMultiviewJoin ist auf True festgelegt

Für die Mitarbeiter in der Zweigniederlassung erstellt der Administrator die Konferenzrichtlinie BranchOfficeVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 350 KBit/s festgelegt

  - TotalReceiveVideoBitRateKB ist auf 350 KBit/s festgelegt

  - AllowMultiview ist auf True festgelegt

  - EnableMultiviewJoin ist auf False festgelegt

Für alle anderen Mitarbeiter erstellt der Administrator die Konferenzrichtlinie StandardVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:

  - VideoBitRateKB ist auf 2500 KBit/s festgelegt

  - TotalReceiveVideoBitRateKB ist auf 2500 KBit/s festgelegt

  - AllowMultiview ist auf True festgelegt

  - EnableMultiviewJoin ist auf True festgelegt

Der Administrator weist die Konferenzrichtlinie wie folgt den Benutzern zu:

  - Die Konferenzrichtlinie ExecutiveVideo wird den Führungskräften zugewiesen.

  - Die Konferenzrichtlinie BranchOfficeVideo wird allen Mitarbeitern in der Zweigniederlassung zugewiesen.

  - Die Konferenzrichtlinie StandardVideo wird allen anderen Mitarbeitern zugewiesen.

Diese Zuweisungen von Konferenzrichtlinien ergeben für die Benutzer Folgendes:

  - Alle von einem beliebigen Benutzer organisierte Konferenzen unterstützen die Katalogansicht, aber Mitarbeiter in der Zweigniederlassung können die Katalogansicht nicht nutzen.

  - Für Konferenzen mit zwei oder mehreren Teilnehmern können die Führungskräfte Full-HD-Video mit einer Auflösung von 1920 x 1080 senden, falls dies von ihrer Hardware und Netzwerkverbindung unterstützt wird, und sie können Full-HD-Video mit einer Auflösung von 1920 x 1080 empfangen, soweit dies von den Clients der anderen Teilnehmer unterstützt wird.

  - Mitarbeiter, die keine Führungskräfte sind, können bei Konferenzen mit zwei oder mehreren Teilnehmern niedrigere Auflösungen als die Führungskräfte nutzen, erhalten aber immer noch eine gute Auflösung.

  - Mitarbeiter, die sich in der Zweigniederlassung befinden, erhalten bei Anrufen mit zwei Teilnehmern gute Videoqualität, wenn lync die Standardgröße des Videofensters anzeigt. Wenn das lync-Fenster jedoch auf den Vollbildmodus maximiert ist, wird die Videoauflösung nicht erhöht. Bei Konferenzen mit mehreren Teilnehmer wird den Mitarbeitern in der Zweigstelle nur ein aktives Video angezeigt.

</div>

<span> </span>

</div>

</div>

</div>

