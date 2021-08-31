---
title: Quality of Service in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in einem Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f87dfea2eb847a8bf6ae4c6aa95b099d93b0c1e0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732934"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams

Quality of Service (QoS) in Microsoft Teams ermöglicht Echtzeit-Netzwerkdatenverkehr, der auf Netzwerkverzögerungen (z. B. Sprach- oder Videostreams) zu einem weniger sensiblen Datenverkehr "eingeschnitten" wird (z. B. beim Herunterladen einer neuen App, bei dem eine zusätzliche Sekunde zum Herunterladen keine große Menge ist). QoS verwendet Windows Gruppenrichtlinienobjekte und portbasierte Zugriffssteuerungslisten, um alle Pakete in Echtzeitdatenströmen zu identifizieren und zu markieren. Dies hilft Ihrem Netzwerk dabei, Audio-, Video- und Bildschirmfreigabe-Streams einen dedizierten Teil der Netzwerkbandbreite zu verleihen.

Wenn Sie eine große Gruppe von Benutzern unterstützen, bei denen eines der in diesem Artikel beschriebenen Probleme auftritt, müssen Sie wahrscheinlich QoS implementieren. Ein kleines Unternehmen mit wenigen Benutzern benötigt möglicherweise QoS nicht, aber auch dort sollte es hilfreich sein.

Ohne eine Form von QoS werden möglicherweise die folgenden Qualitätsprobleme in Sprache und Video angezeigt:

- Jitter – Die Empfangen von Medienpaketen mit unterschiedlichen Paketraten kann zu fehlenden Wörtern oder Silben in Anrufen führen.
- Paketverlust – Verworfene Pakete, was auch zu einer geringeren Sprachqualität und schwer verständlichen Spracherkennung führen kann
- Verzögerte Roundtripzeit (ROUND-Trip Time, RTT) – Die Medienpakete dauern lange bis zum Erreichen ihres Ziels, was zu deutlichen Verzögerungen zwischen zwei Gesprächs beteiligten Parteien führt und dazu führt, dass miteinander gesprochen wird.

Die am wenigsten komplexe Möglichkeit, diese Probleme zu beheben, besteht im Vergrößern der Größe der Datenverbindungen, sowohl intern als auch aus dem Internet. Da dies häufig unerschwinglich ist, bietet QoS eine Möglichkeit, Ihre verfügbaren Ressourcen effektiver zu verwalten, statt die Bandbreite zu addieren. Um Probleme mit der Qualität zu beheben, empfiehlt es sich, zuerst QoS zu verwenden und dann bei Bedarf nur Bandbreite hinzuzufügen.

Damit QoS wirksam wird, müssen Sie in der gesamten Organisation konsistente QoS-Einstellungen anwenden. Jeder Teil des Pfads, der Ihre QoS-Prioritäten nicht unterstützt, kann die Qualität von Anrufen, Videos und Bildschirmfreigaben beeinträchtigen. Dies umfasst das Anwenden von Einstellungen auf alle Benutzer-PCs oder -geräte, Netzwerkschalter, Router zum Internet und Teams Dienst.

_Abbildung 1. Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365 oder Office 365 Diensten_

![Abbildung der Beziehung zwischen Netzwerken und Diensten.](media/Qos-in-Teams-Image1.png "Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365- oder Office 365-Diensten: Lokales Netzwerk und Geräte verbinden sich mit einem verbundenen Netzwerk, das wiederum eine Verbindung mit Microsoft 365- oder Office 365-Cloud-Sprach- und Audiokonferenzdiensten herstellt.")

## <a name="qos-implementation-checklist"></a>Prüfliste für die QoS-Implementierung

Gehen Sie auf einer hohen Ebene wie folgt vor, um QoS zu implementieren:

1. [Stellen Sie sicher, dass Das Netzwerk bereit ist.](#make-sure-your-network-is-ready)

1. [Wählen Sie eine QoS-Implementierungsmethode aus.](#select-a-qos-implementation-method)

1. [Wählen Sie die anfänglichen Portbereiche für jeden Medientyp aus.](#choose-initial-port-ranges-for-each-media-type)

1. Implementieren Sie QoS-Einstellungen:
   1. Auf Clients, die ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) zum Festlegen von Portbereichen und Kennzeichnungen für [Clientgeräte verwenden.](QoS-in-Teams-clients.md)
   2. Auf Routern (siehe Dokumentation des Herstellers) oder anderen Netzwerkgeräten. Dies kann portbasierte Zugriffssteuerungslisten (Access Control Lists, ACLs) oder einfach nur das Definieren der QoS-Warteschlangen und DSCP-Markierungen oder alle diese umfassen.

      > [!IMPORTANT]
      > Wir empfehlen, diese QoS-Richtlinien über die Clientquellenports und die IP-Quell- und Zieladresse "any" zu implementieren. Dadurch wird sowohl der eingehende als auch der ausgehende Medienverkehr im internen Netzwerk abfangen.  

   3. [Legen Sie die Verarbeitung des Mediendatenverkehrs für Besprechungen Teams vor.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Überprüfen Sie Ihre QoS-Implementierung,](#validate-your-qos-implementation) indem Sie Teams Datenverkehr im Netzwerk analysieren.

Beachten Sie bei der Vorbereitung der Implementierung von QoS die folgenden Richtlinien:

- Der kürzeste Weg zu Microsoft 365 ist am besten.
- Das Schließen von Ports führt nur zu einer Qualitätsbeeinträchtigung.
- Hindernisse dazwischen, z. B. Proxys, werden nicht empfohlen.
- Beschränken Sie die Anzahl der Hops:
  - Client-zu-Netzwerk-Edge – 3 bis 5 Hops
  - IsP zum Microsoft-Netzwerk-Edge – 3 Hops
  - Microsoft-Netzwerk-Edge bis zum endgültigen Ziel – irrelevant

Informationen zum Konfigurieren der Firewallports finden Sie unter konfigurieren [Office 365 URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Stellen Sie sicher, dass Ihr Netzwerk bereit ist

Wenn Sie eine QoS-Implementierung in Erwägung ziehen, sollten Sie ihre Bandbreitenanforderungen und andere [Netzwerkanforderungen bereits festgelegt haben.](prepare-network.md)
  
Verkehrsüberlastung in einem Netzwerk hat großen Einfluss auf die Medienqualität. Fehlende Bandbreite führt zu Leistungseinbußen und einer schlechten Benutzererfahrung. Da Teams und Nutzung wächst, verwenden [](use-call-analytics-to-troubleshoot-poor-call-quality.md)Sie Berichterstellung, Anrufanalyse pro Benutzer und Anrufqualitätsdashboard [(Call Quality Dashboard, CQD),](turning-on-and-using-call-quality-dashboard.md) um Probleme zu erkennen und dann Anpassungen mithilfe von QoS und selektiver Bandbreitenzustellung vornimmt.

### <a name="vpn-considerations"></a>Überlegungen zu VPN

QoS funktioniert nur wie erwartet, wenn es für alle Verknüpfungen zwischen Anrufern implementiert wird. Wenn Sie QoS in einem internen Netzwerk verwenden und sich ein Benutzer von einem Remotestandort aus meldet, können Sie nur innerhalb Ihres internen, verwalteten Netzwerks Prioritäten setzen. Obwohl Remotestandorte eine verwaltete Verbindung empfangen können, indem sie ein VPN (Virtuelles privates Netzwerk) implementieren, erhöht ein VPN grundsätzlich den Paketaufwand und sorgt für Verzögerungen beim Echtzeitdatenverkehr. Wir empfehlen, die Ausführung von Echtzeit-Kommunikationsverkehr über ein VPN zu vermeiden.

In einer globalen Organisation mit verwalteten Links, die sich über Kontinente erstreckt, wird QoS dringend empfohlen, da die Bandbreite für diese Links im Vergleich zum LAN beschränkt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in QoS-Warteschlangen

Zur Bereitstellung von QoS müssen Netzwerkgeräte über eine Möglichkeit zum Klassifizieren von Datenverkehr verfügen und in der Lage sein, Sprache oder Video von anderem Netzwerkdatenverkehr zu unterscheiden.

Wenn der Netzwerkdatenverkehr einen Router einbetritt, wird der Datenverkehr in eine Warteschlange gesetzt. Wenn eine QoS-Richtlinie nicht konfiguriert ist, gibt es nur eine Warteschlange, und alle Daten werden als First-In, First-Out mit derselben Priorität behandelt. Dies bedeutet, dass der Sprachdatenverkehr (der sehr anfällig für Verzögerungen ist) hinter dem Datenverkehr zurückbleiben kann, bei dem eine Verzögerung von ein paar zusätzlichen Millisekunden kein Problem wäre.

Wenn Sie QoS implementieren, definieren Sie mehrere Warteschlangen mithilfe eines von mehreren Features für das Überlastungsmanagement, z. B. die Prioritätswarteschlange von Cisco und [class-based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) und Die Vermeidung von Überlastung, z. B. gewichtete zufällige Früherkennung [(WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Abbildung 2. Beispiele für QoS-Warteschlangen_

![Abbildung von QoS-Warteschlangen und Bandbreitenteilung](media/Qos-in-Teams-Image2.png "Die gesamte verfügbare Bandbreite wird auf mehrere Warteschlangen – Audio, Video und anderen Datenverkehr – aufgeteilt, denen unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache Analogie ist, dass QoS virtuelle "Fahrgemeinschaften" in Ihrem Datennetzwerk erstellt, sodass es bei einigen Datentypen nie oder nur selten zu Verzögerungen kommt. Nachdem Sie diese Verantwortlichen erstellt haben, können Sie deren relative Größe anpassen und die verfügbare Verbindungsbandbreite viel effektiver verwalten, während Sie gleichzeitig den Benutzern Ihrer Organisation benutzerdefinierte Benutzererfahrungen auf Unternehmensqualität bieten.

## <a name="select-a-qos-implementation-method"></a>Auswählen einer QoS-Implementierungsmethode

Sie können QoS über portbasiertes Tagging implementieren, indem Sie Zugriffssteuerungslisten (ACLs) auf den Routern Ihres Netzwerks verwenden. Portbasiertes Tagging ist die zuverlässigste Methode, da sie in Mixed Windows-, Mac- und Linux-Umgebungen funktioniert und am einfachsten zu implementieren ist. Mobile Clients stellen keinen Mechanismus zum Markieren des Datenverkehrs mithilfe von DSCP-Werten zur Verfügung, daher ist diese Methode erforderlich.  

Mit portbasiertem Tagging untersucht der Router Ihres Netzwerks ein eingehendes Paket. Wenn das Paket über einen bestimmten Port oder Portsbereich eingetroffen ist, identifiziert es es als einen bestimmten Medientyp und legt es in der Warteschlange für diesen Typ ab, und fügt dem IP-Paketheader ein vordefiniertes [DSCP-Zeichen](https://tools.ietf.org/html/rfc2474) hinzu, damit andere Geräte seinen Datenverkehrstyp erkennen und ihm Priorität in der Warteschlange geben können.

Obwohl portbasiertes Tagging plattformübergreifend funktioniert, wird der Datenverkehr am WAN-Edge (nicht bis zum Clientcomputer) markiert und ein Verwaltungsaufwand verursacht. Anweisungen zur Implementierung dieser Methode finden Sie in der vom Routerhersteller bereitgestellten Dokumentation.

### <a name="insert-dscp-markers"></a>Einfügen von DSCP-Markierungen

Sie können QoS auch implementieren, indem Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) verwenden, um Clientgeräte an den Client weiter zu führen, um eine DSCP-Markierung in IP-Paketheader einlegen, die sie als bestimmte Art von Datenverkehr (z. B. Sprache) identifiziert. Router und andere Netzwerkgeräte können so konfiguriert werden, dass sie dies erkennen und den Datenverkehr in einer separaten Warteschlange mit höherer Priorität abwarten.

Dieses Szenario ist zwar vollständig gültig, es funktioniert aber nur bei Domänen-in-Windows Clients. Jedes Gerät, das kein Domänen-Mitglied des Windows-Client ist, wird nicht für DSCP-Tags aktiviert. Andere Clients, z. B. solche mit macOS, verfügen über hart codierte Tags und markieren den Datenverkehr immer.

Auf der Plusseite wird durch Steuern der DSCP-Markierung über Gruppenrichtlinienobjekt sichergestellt, dass alle in die Domäne eingetretenen Computer dieselben Einstellungen erhalten und nur von einem Administrator verwaltet werden können. Clients, die Gruppenrichtlinienobjekt verwenden können, werden auf dem Ursprungsgerät markiert, und dann können konfigurierte Netzwerkgeräte den Echtzeitdatenstrom anhand des DSCP-Codes erkennen und ihm eine entsprechende Priorität geben.

### <a name="best-practice"></a>Bewährte Methode

Wir empfehlen nach Möglichkeit eine Kombination von DSCP-Markierungen am Endpunkt und portbasierten ACLs auf Routern. Durch die Verwendung eines Gruppenrichtlinienobjekts zum Abfangen der Mehrzahl der Clients und durch die Verwendung portbasierter DSCP-Tags wird sichergestellt, dass mobile, Mac- und andere Clients QoS-Behandlungen (zumindest teilweise) erhalten.

DSCP-Markierungen können mit Portostempeln versehen werden, die den Postmitarbeitern zeigen, wie dringend die Lieferung ist und wie sie für eine schnelle Zustellung am besten sortiert werden können. Nachdem Sie Ihr Netzwerk so konfiguriert haben, dass Echtzeitmedienströme Priorität erhalten, sollten verlorene Pakete und verspätete Pakete deutlich abgenommen werden.

Sobald alle Geräte im Netzwerk die gleichen Klassifizierungen, Markierungen und Prioritäten verwenden, ist es möglich, Verzögerungen, verworfene Pakete und Jitter zu reduzieren oder zu beseitigen, indem die Größe der Portbereiche geändert wird, die den Warteschlangen für die einzelnen Datenverkehrstypen zugewiesen sind. Aus Teams Sicht ist der wichtigste Konfigurationsschritt die Klassifizierung und Markierung von Paketen. Damit End-to-End-QoS erfolgreich ist, müssen Sie jedoch auch die Konfiguration der Anwendung sorgfältig an der zugrunde liegenden Netzwerkkonfiguration ausrichten. Sobald QoS vollständig implementiert wurde, ist eine ständige Verwaltung eine Frage der Anpassung der Portbereiche, die den einzelnen Datenverkehrstypen zugewiesen sind, basierend auf den Anforderungen ihrer Organisation und der tatsächlichen Nutzung.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Auswählen der anfänglichen Portierungsbereiche für jeden Medientyp

Der DSCP-Wert teilt einem entsprechend konfigurierten Netzwerk mit, welche Priorität einem Paket oder Stream zugewiesen werden soll, ob die DSCP-Markierung von Clients oder basierend auf ACL-Einstellungen dem Netzwerk selbst zugewiesen wird. Jede Medienarbeitsauslastung erhält ihren eigenen eindeutigen DSCP-Wert (andere Dienste ermöglichen workloads möglicherweise das Freigeben einer DSCP-Markierung, Teams nicht) und einen definierten und separaten Portbereich, der für jeden Medientyp verwendet wird. In anderen Umgebungen ist möglicherweise eine QoS-Strategie vorhanden, die Ihnen hilft, die Priorität von Netzwerkarbeitslasten zu bestimmen.

Die relative Größe der Portbereiche für verschiedene Echtzeitstreamingarbeitslasten legt den Anteil der gesamten verfügbaren Bandbreite fest, die dieser Arbeitsauslastung gewidmet ist. Zur früheren analogen Postanschrift: Ein Brief mit dem Stempel "Air Mail" wird möglicherweise innerhalb einer Stunde zum nächstgelegenen Flughafen genommen, während ein kleines Paket mit der Kennzeichnung "Massensendungen" einen Tag warten kann, bevor er auf dem Landweg auf einer Reihe von Trucks landet.

_Empfohlene anfängliche Portierungsbereiche_

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Beachten Sie die folgenden Punkte, wenn Sie diese Einstellungen verwenden:

- Wenn Sie planen, ExpressRoute in Zukunft zu implementieren, QoS aber noch nicht implementiert haben, empfehlen wir, die Anleitungen zu befolgen, damit die DSCP-Werte von Absender zu Empfänger identisch sind.

- Alle Clients, einschließlich mobiler Clients und Teams-Geräte, verwenden diese Portbereiche und sind von allen DSCP-Richtlinien betroffen, die Sie implementieren, die diese Quellportbereiche verwenden. Die einzigen Clients, die weiterhin dynamische Ports verwenden, sind die browserbasierten Clients (Clients, mit deren Hilfe Teilnehmer über ihren Browser an Besprechungen teilnehmen können).

- Obwohl der Mac-Client dieselben Portbereiche verwendet, verwendet er auch hart codierte Werte für Audio (EF) und Video (AF41). Diese Werte können nicht konfiguriert werden.

- Wenn Sie die Portbereiche später anpassen müssen, um die Benutzerfreundlichkeit zu verbessern, können sich die Portbereiche nicht überlappen und sollten aneinander angrenzen.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie zuvor in Skype for Business Online bereitgestellt haben, einschließlich QoS-Tags und Portbereichen, und werden jetzt bereitgestellt. Teams, Teams die vorhandene Konfiguration respektiert und die gleichen Portbereiche und Tags wie der Skype for Business verwendet. In den meisten Fällen ist keine zusätzliche Konfiguration erforderlich.

> [!NOTE]
> Wenn Sie das QoS-Tagging für Anwendungsnamen über eine Gruppenrichtlinie verwenden, müssen Sie Teams.exe als Anwendungsnamen hinzufügen.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementieren von QoS in Teams auf Windows mithilfe von PowerShell

**Festlegen von QoS für Audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Festlegen von QoS für Video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Festlegen von QoS für die Freigabe**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Verwalten von Quellports im Teams Admin Center

In Teams sollten die von den verschiedenen Workloads verwendeten QoS-Quellports aktiv verwaltet und bei Bedarf angepasst werden. Verweisen auf die Tabelle in Auswählen der anfänglichen [Portbereiche](#choose-initial-port-ranges-for-each-media-type)für jeden Medientyp sind die Portbereiche anpassbar, aber die DSCP-Markierungen können nicht konfiguriert werden. Nachdem Sie diese Einstellungen implementiert haben, werden möglicherweise mehr oder weniger Ports für einen bestimmten Medientyp benötigt. [Die](use-call-analytics-to-troubleshoot-poor-call-quality.md) Anrufanalyse pro Benutzer und das Anrufqualitätsdashboard [(Call Quality Dashboard, CQD)](turning-on-and-using-call-quality-dashboard.md) sollten dazu verwendet werden, die Portbereiche nach der Implementierung von Teams anzupassen, und dies regelmäßig, wenn sich die Anforderungen ändern.

> [!NOTE]
> Wenn Sie QoS bereits basierend auf Quellportbereichen und DSCP-Markierungen für Skype for Business Online konfiguriert haben, gilt die gleiche Konfiguration für Teams, und an der Zuordnung sind keine weiteren Client- oder Netzwerkänderungen erforderlich. Möglicherweise müssen Sie jedoch die [in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) verwendeten Bereiche entsprechend der Konfiguration für Skype for Business Online festlegen.

Wenn Sie zuvor QoS-Richtlinien Skype for Business Server bereitgestellt haben, müssen Sie Ihre QoS-Richtlinien möglicherweise erneut überprüfen. Passen Sie die Richtlinien so an, dass sie den Portbereichseinstellungen entsprechen, die Sie überprüft haben, um die Benutzerfreundlichkeit Ihrer Teams.

## <a name="validate-your-qos-implementation"></a>Überprüfen der QoS-Implementierung

Damit QoS wirksam wird, muss der vom Gruppenrichtlinienobjekt festgelegte DSCP-Wert an beiden Enden eines Aufrufs vorhanden sein. Durch Analysieren des vom Teams-Client generierten Datenverkehrs können Sie überprüfen, ob der DSCP-Wert nicht geändert oder entfernt wurde, wenn der Teams-Workloaddatenverkehr durch das Netzwerk bewegt wird.

Vorzugsweise erfassen Sie den Datenverkehr am Netzwerkpunkt. Sie können die Portspiegelung auf einem Switch oder Router verwenden, um dies zu unterstützen.

## <a name="implement-qos-for-other-devices"></a>Implementieren von QoS für andere Geräte

Lesen Sie diese Themen, um Informationen zur Implementierung von QoS für Intune, Surface, iOS, Android und Mac zu erhalten.

- [QoS für Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS für Surface Hub](/surface-hub/surface-hub-qos)

- [QoS für iOS, Android und Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Verwandte Themen

- [Video: Netzwerkplanung](https://aka.ms/teams-networking)

- [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

- [Implementieren von QoS im Teams Client](QoS-in-Teams-clients.md)