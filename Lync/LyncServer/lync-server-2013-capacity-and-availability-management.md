---
title: 'Lync Server 2013: Kapazitäts-und Verfügbarkeitsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923dd7a4133da52a68e4d66ee6d5c7c47e7c0421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_

Der Zweck des Kapazitätsmanagements und des Verfügbarkeits Managements besteht in der Messung und Steuerung der Systemleistung. Wir empfehlen, dass Sie die Verwaltungsverfahren für die Kapazitätsverwaltung und die Verfügbarkeit implementieren, damit Sie die Systemleistung messen und steuern können. Sie müssen wissen, ob das System verfügbar ist und ob es die aktuellen und die voraussichtlichen Anforderungen verarbeiten kann, indem Sie Baselines festlegen und das System überwachen, um nach Trends zu suchen.

<div>

## <a name="capacity-management"></a>Kapazitätsverwaltung

Das Kapazitätsmanagement umfasst die Planung, die Größenanpassung und die Steuerung der Servicekapazität, um sicherzustellen, dass die in Ihrer SLA angegebenen Mindestleistungen überschritten werden. Eine gute Kapazitätsverwaltung sorgt dafür, dass Sie IT-Services zu einem vertretbaren Preis bereitstellen und dennoch die in ihren SLAs mit dem Client definierten Leistungsniveaus erfüllen können. Diese Kriterien können Folgendes umfassen:

  - **Systemantwortzeit**   Dies ist die Zeit, die das System für typische Aktionen benötigt. Beispiele sind die Zeit, die erforderlich ist, damit die Audio/Video-Serverrolle Audio/Video-Datenverkehr verarbeitet, die Zeitdauer, die für einen Client zum Erstellen und teilnehmen an einer Konferenz erforderlich ist, oder die Zeit, die für die Aktualisierung von Anwesenheitsinformationen in allen Watcher-Clients benötigt wird.

  - **Speicherkapazität**   hierbei handelt es sich um die Kapazität eines Speichersystems, ob es sich um eine Inhaltsdatenbank, ein Sicherungsmedium oder ein lokales Laufwerk handelt. Beispiele sind die maximale Menge an Speicherplatz, die pro Website bereitgestellt werden soll, und der Zeitpunkt, zu dem Sicherungen gespeichert werden sollen, bevor Sie überschrieben werden.

Das Anpassen der Kapazität ist häufig ein Fall, um sicherzustellen, dass genügend physische Ressourcen wie Speicherplatz und Netzwerkbandbreite verfügbar sind. In der folgenden Tabelle sind typische Lösungen für kapazitätsbezogene Probleme aufgeführt.

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
<td><p>Überprüfen Sie, ob für die WAN-Links geeignete Bandbreite verfügbar ist und ob QoS aktiviert und entsprechend konfiguriert ist. Überprüfen Sie die QoE-Daten.</p></td>
</tr>
<tr class="even">
<td><p>Die Gesamtantwort der lync-Umgebung ist langsam.</p></td>
<td><p>Führen Sie Tests aus, um zu überprüfen, ob die vorhandenen Front-End-Server die Auslastung bewältigen können. Führen Sie bei Bedarf einen neuen Front-End-Server ein. Überprüfen Sie die Antwortzeiten der SQL-Datenbank, und beheben Sie die Ursachen für Verzögerungen (beispielsweise verbessern Sie die Datenträger-e/a).</p></td>
</tr>
</tbody>
</table>


Ausführlichere Informationen zur Problembehandlung sind im lync Server-Netzwerkhandbuch beschrieben.

Die Kapazität wird von der Systemkonfiguration beeinflusst und hängt von physikalischen Ressourcen wie Netzwerkbandbreite ab. Wenn beispielsweise eine lync-Umgebung so konfiguriert ist, dass nächtlich eine vollständige Sicherung durchgeführt wird, müssen Sie sicherstellen, dass die Auswirkungen auf die interaktive Leistung von Endbenutzern minimiert werden.

Capacity Management ist der Prozess, bei dem die Kapazität eines Systems innerhalb akzeptabler Ebenen bleibt und die folgenden Probleme behoben werden:

  - **Die Reaktion auf Änderungen**   an den Anforderungen der Kapazitätsanforderungen muss angepasst werden, um Änderungen am System oder in der Organisation Rechnung zu tragen. Wenn Ihre Umgebung beispielsweise entscheidet, Enterprise-VoIP zu implementieren, ist die Anzahl und Platzierung von Vermittlungsservern und PSTN-Gateways (Public Switched Telephone Network) sehr wichtig. Wenn Sie SIP-Trunking (Session Initiation Protocol) oder Direct SIP ausführen, wird das Gesamtdesign erheblich geändert, um die beste Leistung für Unternehmens-VoIP zu gewährleisten.

  - **Voraussagen zukünftiger Anforderungen**   einige Kapazitätsanforderungen ändern sich im Laufe der Zeit vorhersehbar. Durch Nachverfolgen von Trends können Sie Upgrades im Voraus planen. Beispielsweise muss die verfügbare Bandbreite zwischen verschiedenen lync-Websites überwacht werden, um einen Basisplan zu erstellen. Mit diesem Basisplan können Sie Vorhersagen, wann Sie diesen Links mehr Bandbreite hinzufügen müssen, da sich die Anzahl der Benutzer in diesen Remotestandorten mit der Zeit vergrößert.

</div>

<div>

## <a name="availability-management"></a>Verfügbarkeitsverwaltung

Bei der Verfügbarkeitsverwaltung wird sichergestellt, dass jeder IT-Dienst konsistent und kostengünstig den konsistenten, zuverlässigen Service bereitstellt, der vom Kunden benötigt wird. Die Verfügbarkeitsverwaltung befasst sich mit dem Minimieren des Service Verlusts und mit der Sicherstellung, dass entsprechende Maßnahmen ergriffen werden, wenn der Dienst verloren geht. In einer lync-Umgebung sind Sie möglicherweise besorgt darüber, ob der Enterprise-VoIP-Dienst verfügbar ist, ob Benutzer an geplanten Konferenzen teilnehmen können usw. Eine SLA definiert eine akzeptable Häufigkeit und Dauer von Ausfällen und ermöglicht bestimmte Zeiträume, wenn das System für geplante Wartungsarbeiten nicht verfügbar ist.

Wenn Sie Ihrem Managementberichte zur Verfügbarkeit von Systemen bereitstellen müssen oder wenn Sie finanzielle oder andere Strafen mit fehlenden Verfügbarkeitszielen verbunden haben, müssen Sie Verfügbarkeitsdaten aufzeichnen. Auch wenn Sie keine derartigen formalen Anforderungen haben, empfiehlt es sich, zumindest zu wissen, wie häufig ein System in einem bestimmten Zeitraum fehlgeschlagen ist. Beispielsweise die Systemverfügbarkeit in den letzten 12 Monaten und die Dauer der Wiederherstellung nach jedem Fehler. Diese Informationen werden Ihnen helfen, die Effektivität Ihres Teams bei der Reaktion auf einen Systemfehler zu messen und zu verbessern. Es kann Ihnen auch nützliche Informationen geben, wenn es eine Unstimmigkeit gibt.

Im Zusammenhang mit der Verfügbarkeit sind folgende Maßnahmen zu finden:

  - **Verfügbarkeit**   Dies wird in der Regel als die Zeit ausgedrückt, zu der auf ein System oder einen Dienst zugegriffen werden kann, verglichen mit dem Zeitpunkt, zu dem er abläuft. Sie wird in der Regel als Prozentsatz ausgedrückt. (Möglicherweise werden Verweise auf "drei Neunen" oder "fünf Neunen" angezeigt. Diese beziehen sich auf die Verfügbarkeit von 99,9 Prozent oder 99,999 Prozent.)

  - **Zuverlässigkeit**   Dies ist ein Maß für die Zeit zwischen Fehlern eines Systems und wird manchmal als Mittelwert (oder Mittelwert) Zeit zwischen Fehlern (MTBF) ausgedrückt.

  - **Zeit zum Reparieren**   Dies ist die Zeit, die für die Wiederherstellung eines Diensts nach einem Fehler aufgetreten ist, und wird häufig als Mittelwert (Mittelwert) für die Reparaturzeit ausgedrückt (MTTR).

Verfügbarkeit, Zuverlässigkeit und Reparaturzeit hängen wie folgt zusammen:

**Verfügbarkeit = (MTBF-MTTR)/MTBF**   Wenn beispielsweise ein Server zwei Mal über einen Zeitraum von sechs Monaten nicht verfügbar ist und für durchschnittlich 20 Minuten nicht zur Verfügung steht, beträgt die MTBF drei Monate oder 90 Tage, und die MTTR beträgt 20 Minuten. Daher Verfügbarkeit = (90 Tage – 20 Minuten)/90 Tage = 99,985 Prozent.

Bei der Verfügbarkeitsverwaltung wird sichergestellt, dass die Verfügbarkeit maximiert und innerhalb der in SLAs definierten Parameter beibehalten wird. Die Verfügbarkeitsverwaltung umfasst die folgenden Prozesse:

  - **Überwachung**     der Untersuchung, wann und wie lange Dienste nicht verfügbar sind.

  - ****   Informationen zur Verfügbarkeit von Berichten sollten regelmäßig für Verwaltungs-, Benutzer-und Betriebsteams bereitgestellt werden. Diese Berichte sollten Trends hervorheben und Bereiche ermitteln, die gut funktionieren, und Bereiche, die berücksichtigt werden müssen. Der Bericht sollte die Einhaltung der in den SLAs festgelegten Ziele zusammenfassen.

  - **Verbesserung**   wenn die Verfügbarkeit nicht den in den SLAs definierten Zielen entspricht oder der Trend zu einer reduzierten Verfügbarkeit führt, sollte der Verfügbarkeits Verwaltungsprozess Sanierungsschritte planen. Dazu gehören die Zusammenarbeit mit anderen zuständigen Teams, um Ursachen für Ausfälle hervorzuheben und Sanierungsmaßnahmen zu planen, um eine Wiederholung der Ausfälle zu vermeiden.

Kapazitäts-und Verfügbarkeits Messungen sind sich wiederholende Aufgaben, die ideal für automatisierte Tools und Skripts wie Microsoft System Center Operations Manager (vormals Microsoft Operations Manager) geeignet sind, die später in diesem Dokument erläutert werden.

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

