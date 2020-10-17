---
title: 'Lync Server 2013: Kapazitäts-und Verfügbarkeitsverwaltung'
description: 'Lync Server 2013: Kapazitäts-und Verfügbarkeitsverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565151"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Der Zweck der Kapazitätsverwaltung und der Verfügbarkeitsverwaltung besteht darin, die Systemleistung zu messen und zu steuern. Es wird empfohlen, dass Sie Verfahren zur Verwaltung von Kapazitätsmanagement und Verfügbarkeit implementieren, damit Sie die Systemleistung messen und steuern können. Sie müssen wissen, ob das System verfügbar ist und ob es die aktuellen und die projizierten Anforderungen verarbeiten kann, indem Sie Basislinien festlegen und das System überwachen, um nach Trends zu suchen.

<div>

## <a name="capacity-management"></a>Kapazitätsverwaltung

Die Kapazitätsverwaltung umfasst die Planung, Dimensionierung und Steuerung der Dienstkapazität, um sicherzustellen, dass die in Ihrer SLA festgelegten mindestleistungs Werte überschritten werden. Die Verwaltung guter Kapazität hilft sicherzustellen, dass Sie IT-Dienste zu vertretbaren Kosten bereitstellen und trotzdem die Leistungsstufen erfüllen können, die in ihren SLAs mit dem Client definiert sind. Diese Kriterien können Folgendes umfassen:

  - **System Antwortzeit**     Dies ist die gemessene Zeit, die das System für typische Aktionen benötigt. Beispiele hierfür sind die Zeit, die für die Verarbeitung von Audio/Video-Datenverkehr durch die Audio/Video-Serverrolle erforderlich ist, die Zeit, die für die Erstellung und Teilnahme an einer Konferenz für einen Client erforderlich ist, oder die Zeit, die für die Aktualisierung von Anwesenheitsinformationen in allen Watcher-Clients benötigt wird.

  - **Speicherkapazität**     Dies ist die Kapazität eines Speichersystems, unabhängig davon, ob es sich um eine Inhaltsdatenbank, ein Sicherungsmedium oder ein lokales Laufwerk handelt. Beispiele hierfür sind die maximale Menge an Speicherplatz, die pro Standort bereitgestellt werden soll, sowie die Zeit, die Sicherungen gespeichert werden sollen, bevor Sie überschrieben werden.

Die Kapazitätsanpassung ist häufig ein Fall, um sicherzustellen, dass genügend physische Ressourcen zur Verfügung stehen, beispielsweise Speicherplatz und Netzwerkbandbreite. In der folgenden Tabelle sind typische Lösungen für kapazitätsbezogene Probleme aufgeführt.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Typische Lösungen für kapazitätsbezogene Probleme

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problem</th>
<th>Mögliche Auflösung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Remote Benutzer mit schlechter Audio-/Videoleistung</p></td>
<td><p>Überprüfen Sie, ob für die WAN-Verbindungen geeignete Bandbreite verfügbar ist und QoS aktiviert und entsprechend konfiguriert ist. Überprüfen Sie die QoE-Daten.</p></td>
</tr>
<tr class="even">
<td><p>Die Gesamtantwort der lync-Umgebung ist langsam.</p></td>
<td><p>Führen Sie Tests aus, um zu überprüfen, ob die vorhandenen Front-End-Server mit der Last umgehen können. Führen Sie einen neuen Front-End-Server ein, wenn dieser erforderlich ist. Überprüfen Sie die SQL-Daten Bank Antwortzeiten, und beheben Sie die Ursachen für die Verzögerungen (beispielsweise verbessern Sie die Datenträger-e/a).</p></td>
</tr>
</tbody>
</table>


Ausführliche Informationen zur Problembehandlung finden Sie im Leitfaden lync Server Netzwerke.

Die Kapazität ist von der Systemkonfiguration betroffen und hängt von physikalischen Ressourcen wie Netzwerkbandbreite ab. Wenn beispielsweise eine lync-Umgebung für eine nächtliche vollständige Sicherung konfiguriert ist, muss darauf geachtet werden, dass die Auswirkungen auf die interaktive Leistung von Endbenutzern minimiert werden.

Bei der Kapazitätsverwaltung handelt es sich um die Beibehaltung der Kapazität eines Systems innerhalb akzeptabler Stufen, und es werden die folgenden Probleme behoben:

  - **Reagieren auf geänderte Anforderungen**     Kapazitätsanforderungen müssen angepasst werden, um Änderungen im System oder in der Organisation zu berücksichtigen. Wenn Ihre Umgebung beispielsweise entscheidet, Enterprise-VoIP zu implementieren, ist die Anzahl und Platzierung von Vermittlungsservern und PSTN-Gateways (Public Switched Telephone Network) sehr wichtig. Wenn Sie SIP-Trunking (Session Initiation Protocol) oder Direct SIP durchführen, wird der Gesamtentwurf erheblich geändert, um die beste Leistung für Enterprise-VoIP bereitzustellen.

  - **Voraussagen für zukünftige Anforderungen**     Einige Kapazitätsanforderungen ändern sich im Laufe der Zeit vorhersagbar. Durch Tracking Trends können Sie Upgrades vorab planen. Beispielsweise muss die verfügbare Bandbreite zwischen verschiedenen lync-Standorten überwacht werden, um einen Basisplan zu erstellen. Mit diesem Basisplan können Sie Vorhersagen, wann Sie diesen Links mehr Bandbreite hinzufügen müssen, da die Anzahl der Benutzer in diesen Remotestandorten mit der Zeit zunimmt.

</div>

<div>

## <a name="availability-management"></a>Verfügbarkeitsverwaltung

Verfügbarkeitsverwaltung ist der Prozess, um sicherzustellen, dass jeder IT-Dienst konsistent und kosteneffektiv die Stufe des konsistenten, zuverlässigen Diensts bereitstellt, der vom Kunden benötigt wird. Die Verfügbarkeitsverwaltung befasst sich mit der Minimierung des Dienst Verlusts und mit dem sicherstellen, dass entsprechende Maßnahmen ergriffen werden, wenn der Dienst verloren geht. In einer lync-Umgebung sind Sie möglicherweise besorgt darüber, ob der Enterprise-VoIP-Dienst verfügbar ist, ob Benutzer geplante Konferenzen teilnehmen können usw. Eine SLA definiert eine akzeptable Häufigkeit und Dauer von Ausfällen und ermöglicht für bestimmte Zeiträume, in denen das System für die geplante Wartung nicht verfügbar ist.

Wenn Sie Berichte an ihre Verwaltung über die Verfügbarkeit von Systemen bereitstellen müssen oder wenn Sie finanzielle oder andere Strafen für fehlende Verfügbarkeitsziele haben, müssen Sie die Verfügbarkeitsdaten aufzeichnen. Selbst wenn Sie keine solchen formalen Anforderungen haben, sollten Sie zumindest wissen, wie häufig ein System in einem bestimmten Zeitraum fehlgeschlagen ist. Beispielsweise die Systemverfügbarkeit in den letzten 12 Monaten und die Dauer der Wiederherstellung nach jedem Ausfall. Anhand dieser Informationen können Sie die Effektivität Ihres Teams bei der Reaktion auf einen Systemfehler Messen und verbessern. Es kann Ihnen auch nützliche Informationen geben, wenn es einen Streit gibt.

Im Zusammenhang mit der Verfügbarkeit werden folgende Maßnahmen getroffen:

  - **Verfügbarkeit**     Dies wird normalerweise als die Zeit ausgedrückt, die auf ein System oder einen Dienst zugegriffen werden kann, im Vergleich zu dem Zeitpunkt, zu dem er nicht aktiv ist. Er wird normalerweise als Prozentsatz ausgedrückt. (Möglicherweise werden Verweise auf "drei Neunen" oder "fünf Neunen" angezeigt. Dies bezieht sich auf 99,9 Prozent oder 99,999 Prozent Verfügbarkeit.)

  - **Zuverlässigkeit**     Dies ist ein Maß für die Zeit zwischen den Fehlern eines Systems und wird manchmal als durchschnittliche (mittlere) Zeit zwischen Fehlern (MTBF) ausgedrückt.

  - **Reparaturzeit**     Dies ist die Zeit, die zum Wiederherstellen eines Diensts vorgenommen wurde, nachdem ein Fehler aufgetreten ist, und wird häufig als "Mean" (Bedeutung für den durchschnittlichen) Zeitaufwand für die Reparatur ausgedrückt (MTTR).

Verfügbarkeit, Zuverlässigkeit und Reparaturzeit hängen wie folgt zusammen:

**Verfügbarkeit = (MTBF – MTTR)/MTBF**     Wenn ein Server beispielsweise zwei Mal über einen Zeitraum von sechs Monaten ausfällt und für durchschnittlich 20 Minuten nicht verfügbar ist, beträgt die MTBF drei Monate oder 90 Tage, und die MTTR beträgt 20 Minuten. Daher Verfügbarkeit = (90 Tage – 20 Minuten)/90 Tage = 99,985 Prozent.

Bei der Verfügbarkeitsverwaltung wird sichergestellt, dass die Verfügbarkeit maximiert und innerhalb der in SLAs definierten Parameter aufbewahrt wird. Die Verfügbarkeitsverwaltung umfasst die folgenden Prozesse:

  - **Überwachung**     Untersuchen, wann und für wie lange Dienste nicht verfügbar sind.

  - **Berichterstellung**     Verfügbarkeitszahlen sollten regelmäßig für Management-, Benutzer-und Betriebsteams bereitgestellt werden. Diese Berichte sollten Trends hervorheben und Bereiche erkennen, die gut sind, und Bereiche, die Aufmerksamkeit erfordern. Der Bericht sollte die Einhaltung der in den SLAs festgelegten Ziele zusammenfassen.

  - **Verbesserung**     Wenn die Verfügbarkeit keine Ziele erfüllt, die in den SLAs definiert sind oder wenn sich der Trend auf die reduzierte Verfügbarkeit auswirkt, sollte der Verfügbarkeits Verwaltungsprozess Abhilfemaßnahmen planen. Dazu gehört die Zusammenarbeit mit anderen verantwortlichen Teams, um Ursachen für Ausfällen hervorzuheben und Sanierungsmaßnahmen zu planen, um eine Wiederholung der Ausfälle zu verhindern.

Bei Kapazitäts-und Verfügbarkeits Messungen handelt es sich um sich wiederholende Aufgaben, die für automatisierte Tools und Skripts wie Microsoft System Center Operations Manager (früher Microsoft Operations Manager), die weiter unten in diesem Dokument behandelt werden, ideal geeignet sind.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Überwachen von lync Server 2013 mit System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

