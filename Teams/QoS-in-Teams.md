---
title: Quality of Service in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vorbereiten.
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
ms.openlocfilehash: 5b9c049942808da9b2df97d031ff850949bca211
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713313"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams

Quality of Service (QoS) in Microsoft Teams ermöglicht es Echtzeit-Netzwerkdatenverkehr, der für Netzwerkverzögerungen (z. B. Sprach- oder Videostreams) sensibel ist, vor weniger sensiblem Datenverkehr "zu schneiden" (z. B. beim Herunterladen einer neuen App, bei dem eine zusätzliche Sekunde zum Herunterladen nicht sehr viel ist). QoS verwendet Windows Gruppenrichtlinie-Objekte und portbasierte Access Control Listen, um alle Pakete in Echtzeitdatenströmen zu identifizieren und zu markieren. Dies hilft Ihrem Netzwerk, Audio-, Video- und Bildschirmfreigabestreams einen dedizierten Teil der Netzwerkbandbreite zu geben.

Wenn Sie eine große Gruppe von Benutzern unterstützen, bei denen eines der in diesem Artikel beschriebenen Probleme auftritt, müssen Sie wahrscheinlich QoS implementieren. Ein kleines Unternehmen mit wenigen Benutzern benötigt QoS möglicherweise nicht, aber auch dort sollte es hilfreich sein.

Ohne irgendeine Form von QoS werden möglicherweise die folgenden Qualitätsprobleme in Sprache und Video angezeigt:

- Jitter – Medienpakete, die in unterschiedlichen Raten ankommen, was zu fehlenden Wörtern oder Silben in Anrufen führen kann
- Paketverlust – Verworfene Pakete, die auch zu einer geringeren Sprachqualität und schwer verständlicher Sprache führen können
- Verzögerte Roundtripzeit (RTT) – Medienpakete, die lange brauchen, um ihre Ziele zu erreichen, was zu spürbaren Verzögerungen zwischen zwei Gesprächsparteien führt und dazu führt, dass die Menschen miteinander sprechen

Die am wenigsten komplexe Möglichkeit, diese Probleme zu beheben, besteht darin, die Größe der Datenverbindungen sowohl intern als auch außerhalb des Internets zu erhöhen. Da dies oft kostenintensiv ist, bietet QoS eine Möglichkeit, die vorhandenen Ressourcen effektiver zu verwalten, anstatt Bandbreite hinzuzufügen. Um Qualitätsprobleme zu beheben, empfehlen wir, zuerst QoS zu verwenden und dann nur bei Bedarf Bandbreite hinzuzufügen.

Damit QoS effektiv ist, müssen Sie konsistente QoS-Einstellungen in der gesamten Organisation anwenden. Jeder Teil des Pfads, der Ihre QoS-Prioritäten nicht unterstützt, kann die Qualität von Anrufen, Video und Bildschirmfreigabe beeinträchtigen. Dazu gehört das Anwenden von Einstellungen auf alle Benutzer-PCs oder -Geräte, Netzwerksitches, Router auf das Internet und den Teams-Dienst.

_Abbildung 1. Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365- oder Office 365-Diensten_

![Abbildung der Beziehung zwischen Netzwerken und Diensten.](media/Qos-in-Teams-Image1.png "Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365- oder Office 365-Diensten: lokales Netzwerk und Geräte verbinden sich mit einem Verbindungsnetzwerk, das wiederum eine Verbindung mit Microsoft 365- oder Office 365 Cloud-VoIP- und Audiokonferenzdiensten herstellt.")

## <a name="qos-implementation-checklist"></a>Prüfliste für die QoS-Implementierung

Führen Sie auf hoher Ebene die folgenden Schritte aus, um QoS zu implementieren:

1. [Stellen Sie sicher, dass Ihr Netzwerk bereit ist](#make-sure-your-network-is-ready).

1. [Wählen Sie eine QoS-Implementierungsmethode](#select-a-qos-implementation-method) aus.

1. [Wählen Sie die anfänglichen Portbereiche für jeden Medientyp](#choose-initial-port-ranges-for-each-media-type) aus.

1. Implementieren von QoS-Einstellungen:
   1. Auf Clients, die ein Gruppenrichtlinie-Objekt (GPO) verwenden, um [Portbereiche und Markierungen von Clientgeräten festzulegen](QoS-in-Teams-clients.md).
   2. Auf Routern (siehe Herstellerdokumentation) oder anderen Netzwerkgeräten. Dies kann portbasierte Access Control Listen (ACLs) oder einfach das Definieren der QoS-Warteschlangen und DSCP-Markierungen oder all diese sein.

      > [!IMPORTANT]
      > Es wird empfohlen, diese QoS-Richtlinien mithilfe der Clientquellports und einer Quell- und Ziel-IP-Adresse von "any" zu implementieren. Dadurch wird sowohl eingehender als auch ausgehender Mediendatenverkehr im internen Netzwerk erfasst.  

   3. [Legen Sie fest, wie Der Mediendatenverkehr für Teams-Besprechungen behandelt werden soll](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. [Überprüfen Sie Ihre QoS-Implementierung](#validate-your-qos-implementation) , indem Sie den Microsoft Teams-Datenverkehr im Netzwerk analysieren.

Beachten Sie bei der Vorbereitung der Implementierung von QoS die folgenden Richtlinien:

- Der kürzeste Weg zu Microsoft 365 ist am besten.
- Das Schließen von Ports führt nur zu einer Qualitätsverschlechterung.
- Jegliche Hindernisse dazwischen, z. B. Proxys, werden nicht empfohlen.
- Beschränken Sie die Anzahl der Hops:
  - Client-zu-Netzwerk-Edge – 3 bis 5 Hops
  - ISP zum Microsoft-Netzwerk-Edge – 3 Hops
  - Microsoft-Netzwerk-Edge bis zum endgültigen Ziel – irrelevant

Informationen zum Konfigurieren von Firewallports finden Sie unter [Office 365 URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Stellen Sie sicher, dass Ihr Netzwerk bereit ist

Wenn Sie eine QoS-Implementierung in Betracht ziehen, sollten Sie bereits Ihre Bandbreitenanforderungen und andere [Netzwerkanforderungen](prepare-network.md) festgelegt haben.
  
Datenverkehrsüberlastung über ein Netzwerk wirkt sich stark auf die Medienqualität aus. Ein Mangel an Bandbreite führt zu leistungseinbußen und einer schlechten Benutzererfahrung. Mit wachsender Einführung und Nutzung von Teams können Sie Mithilfe von Berichterstellung, [Anrufanalyse pro Benutzer](use-call-analytics-to-troubleshoot-poor-call-quality.md) und [Anrufqualitätsdashboard (Call Quality Dashboard, CQD)](turning-on-and-using-call-quality-dashboard.md) Probleme identifizieren und dann Anpassungen mithilfe von QoS und selektiven Bandbreitenerweiterungen vornehmen.

### <a name="vpn-considerations"></a>Überlegungen zu VPN

QoS funktioniert nur wie erwartet, wenn es für alle Verbindungen zwischen Anrufern implementiert wird. Wenn Sie QoS in einem internen Netzwerk verwenden und sich ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur innerhalb Ihres internen, verwalteten Netzwerks priorisieren. Obwohl Remotestandorte eine verwaltete Verbindung empfangen können, indem sie ein virtuelles privates Netzwerk (VPN) implementieren, erhöht ein VPN grundsätzlich den Paketaufwand und verursacht Verzögerungen im Echtzeitdatenverkehr. Es wird empfohlen, echtzeitbasierten Kommunikationsdatenverkehr über ein VPN zu vermeiden.

In einer globalen Organisation mit verwalteten Links, die sich über Kontinente erstrecken, empfehlen wir dringend QoS, da die Bandbreite für diese Links im Vergleich zum LAN begrenzt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in QoS-Warteschlangen

Um QoS bereitzustellen, müssen Netzwerkgeräte eine Möglichkeit zum Klassifizieren von Datenverkehr haben und in der Lage sein, VoIP oder Video von anderem Netzwerkdatenverkehr zu unterscheiden.

Wenn der Netzwerkdatenverkehr in einen Router gelangt, wird der Datenverkehr in eine Warteschlange platziert. Wenn eine QoS-Richtlinie nicht konfiguriert ist, gibt es nur eine Warteschlange, und alle Daten werden als first-in und first-out mit derselben Priorität behandelt. Dies bedeutet, dass der VoIP-Datenverkehr (der sehr empfindlich auf Verzögerungen reagiert) möglicherweise hinter dem Datenverkehr hängen bleibt, wenn eine Verzögerung von ein paar zusätzlichen Millisekunden kein Problem wäre.

Wenn Sie QoS implementieren, definieren Sie mehrere Warteschlangen mithilfe einer von mehreren Funktionen für die Überlastungsverwaltung, z. B. ciscos Prioritätswarteschlangen und [class-based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) und Funktionen zur Vermeidung von Überlastung, z. B. [gewichtete zufällige Früherkennung (WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Abbildung 2. Beispiele für QoS-Warteschlangen_

![Abbildung von QoS-Warteschlangen und Bandbreitenteilung.](media/Qos-in-Teams-Image2.png "Die gesamte verfügbare Bandbreite wird auf mehrere Warteschlangen aufgeteilt – Audio, Video und anderer Datenverkehr – denen unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache Analogie ist, dass QoS virtuelle "Fahrgemeinschaftenspuren" in Ihrem Datennetzwerk erstellt, sodass einige Arten von Daten nie oder selten auf verzögerungen stoßen. Nachdem Sie diese Lanes erstellt haben, können Sie deren relative Größe anpassen und die verfügbare Verbindungsbandbreite viel effektiver verwalten und den Benutzern Ihrer Organisation dennoch Benutzeroberflächen auf Unternehmensniveau bereitstellen.

## <a name="select-a-qos-implementation-method"></a>Auswählen einer QoS-Implementierungsmethode

Sie können QoS über portbasierte Tagging implementieren, indem Sie Access Control Lists (ACLs) auf den Routern Ihres Netzwerks verwenden. Portbasierte Tagging ist die zuverlässigste Methode, da sie in gemischten Windows-, Mac- und Linux-Umgebungen funktioniert und am einfachsten zu implementieren ist. Mobile Clients bieten keinen Mechanismus zum Kennzeichnen von Datenverkehr mithilfe von DSCP-Werten, daher ist diese Methode erforderlich.  

Mithilfe portbasierter Markierungen untersucht der Router Ihres Netzwerks ein eingehendes Paket, und wenn das Paket mit einem bestimmten Port oder Portbereich eingetroffen ist, identifiziert er es als einen bestimmten Medientyp und fügt es in die Warteschlange für diesen Typ ein, und fügt dem IP-Paketheader ein [vordefiniertes DSCP-Zeichen](https://tools.ietf.org/html/rfc2474) hinzu, damit andere Geräte den Datenverkehrstyp erkennen und ihm Priorität in der Warteschlange geben können.

Obwohl die portbasierte Kennzeichnung plattformübergreifend funktioniert, markiert sie nur den Datenverkehr am WAN-Edge (nicht bis zum Clientcomputer) und verursacht Verwaltungsaufwand. Anweisungen zur Implementierung dieser Methode finden Sie in der Dokumentation des Routerherstellers.

### <a name="insert-dscp-markers"></a>Einfügen von DSCP-Markierungen

Sie können QoS auch implementieren, indem Sie ein Gruppenrichtlinie-Objekt (GPO) verwenden, um Clientgeräte anzuweisen, einen DSCP-Marker in IP-Paketheader einzufügen, die ihn als bestimmten Datenverkehrstyp (z. B. VoIP) identifizieren. Router und andere Netzwerkgeräte können so konfiguriert werden, dass sie dies erkennen und den Datenverkehr in einer separaten Warteschlange mit höherer Priorität platzieren.

Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur für Windows-Clients, die einer Domäne beigetreten sind. Jedes Gerät, das kein in die Domäne eingebundener Windows-Client ist, wird nicht für DSCP-Tagging aktiviert. Andere Clients, z. B. solche, auf denen macOS ausgeführt wird, verfügen über hartcodierte Tags und markieren den Datenverkehr immer.

Darüber hinaus stellt die Steuerung der DSCP-Markierung über GPO sicher, dass alle in die Domäne eingebundenen Computer die gleichen Einstellungen erhalten und nur ein Administrator sie verwalten kann. Clients, die GPO verwenden können, werden auf dem ursprünglichen Gerät markiert. Anschließend können konfigurierte Netzwerkgeräte den Echtzeitdatenstrom durch den DSCP-Code erkennen und ihm eine entsprechende Priorität zuweisen.

### <a name="best-practice"></a>Bewährte Methode

Wir empfehlen eine Kombination aus DSCP-Markierungen am Endpunkt und portbasierten ACLs auf Routern, wenn möglich. Die Verwendung eines Gruppenrichtlinienobjekts zur Erfassung der Meisten Clients und die Verwendung portbasierter DSCP-Tags stellt sicher, dass mobile, Mac- und andere Clients weiterhin QoS-Behandlung erhalten (zumindest teilweise).

DSCP-Markierungen können mit Portostempeln abgeglicht werden, die Postangestellten zeigen, wie dringend die Zustellung ist und wie sie für die schnelle Zustellung am besten sortiert werden kann. Nachdem Sie Ihr Netzwerk so konfiguriert haben, dass Echtzeitmedienströmen Priorität eingeräumt wird, sollten verlorene Pakete und verspätete Pakete stark abnehmen.

Sobald alle Geräte im Netzwerk dieselben Klassifizierungen, Markierungen und Prioritäten verwenden, ist es möglich, Verzögerungen, verworfene Pakete und Jitter zu reduzieren oder zu beseitigen, indem Sie die Größe der Portbereiche ändern, die den Warteschlangen zugewiesen sind, die für jeden Datenverkehrstyp verwendet werden. Aus Sicht von Teams ist der wichtigste Konfigurationsschritt die Klassifizierung und Kennzeichnung von Paketen. Damit End-to-End-QoS jedoch erfolgreich ist, müssen Sie auch die Konfiguration der Anwendung sorgfältig an der zugrunde liegenden Netzwerkkonfiguration ausrichten. Sobald QoS vollständig implementiert ist, ist die fortlaufende Verwaltung eine Frage der Anpassung der Portbereiche, die jedem Datenverkehrstyp zugewiesen sind, basierend auf den Anforderungen Ihrer Organisation und der tatsächlichen Nutzung.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Auswählen der anfänglichen Portbereiche für jeden Medientyp

Der DSCP-Wert teilt einem entsprechend konfigurierten Netzwerk mit, welche Priorität einem Paket oder Stream zugewiesen werden soll, ob die DSCP-Markierung von Clients oder dem Netzwerk selbst basierend auf ACL-Einstellungen zugewiesen wird. Jede Medienworkload erhält einen eigenen eindeutigen DSCP-Wert (andere Dienste ermöglichen Workloads möglicherweise die Freigabe einer DSCP-Markierung, Teams nicht) und einen definierten und separaten Portbereich, der für jeden Medientyp verwendet wird. Andere Umgebungen verfügen möglicherweise über eine vorhandene QoS-Strategie, mit der Sie die Priorität von Netzwerkworkloads ermitteln können.

Die relative Größe der Portbereiche für verschiedene Echtzeitstreaming-Workloads legt den Anteil der gesamten verfügbaren Bandbreite fest, die für diese Workload reserviert ist. Um zu unserer früheren Post analog zurückzukehren: Ein Brief mit einem "Air Mail"-Stempel kann innerhalb einer Stunde zum nächstgelegenen Flughafen gebracht werden, während ein kleines Paket mit der Kennzeichnung "Massensendung" einen Tag warten kann, bevor es auf einer Reihe von Lastwagen über Land geht.

_Empfohlene anfängliche Portbereiche_

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Beachten Sie Folgendes, wenn Sie diese Einstellungen verwenden:

- Wenn Sie planen, ExpressRoute in Zukunft zu implementieren und QoS noch nicht implementiert haben, empfehlen wir, dass Sie die Anleitung befolgen, damit DSCP-Werte von Absender zu Empfänger identisch sind.

- Alle Clients, einschließlich mobiler Clients und Teams-Geräte, verwenden diese Portbereiche und sind von jeder von Ihnen implementierten DSCP-Richtlinie betroffen, die diese Quellportbereiche verwendet. Die einzigen Clients, die weiterhin dynamische Ports verwenden, sind die browserbasierten Clients (Clients, mit denen Teilnehmer über ihre Browser an Besprechungen teilnehmen können).

- Obwohl der Mac-Client dieselben Portbereiche verwendet, verwendet er auch hartcodierte Werte für Audio (EF) und Video- und Anwendungs-/Bildschirmfreigabe (AF41). Diese Werte können nicht konfiguriert werden.

- Wenn Sie die Portbereiche später anpassen müssen, um die Benutzerfreundlichkeit zu verbessern, können sich die Portbereiche nicht überlappen und sollten nebeneinander liegen.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie zuvor Skype for Business Online bereitgestellt haben, einschließlich QoS-Tagging und Portbereiche, und jetzt bereitstellen. Teams respektiert die vorhandene Konfiguration und verwendet die gleichen Portbereiche und Tags wie der Skype for Business Client. In den meisten Fällen ist keine zusätzliche Konfiguration erforderlich.

> [!NOTE]
> Wenn Sie QoS-Tags für Anwendungsnamen über Gruppenrichtlinie verwenden, müssen Sie Teams.exe als Anwendungsnamen hinzufügen.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementieren von QoS in Teams unter Windows mithilfe von PowerShell

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

In Teams sollten QoS-Quellports, die von den verschiedenen Workloads verwendet werden, aktiv verwaltet und bei Bedarf angepasst werden. In Bezug auf die Tabelle in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't konfigurierbar. Nachdem Sie diese Einstellungen implementiert haben, stellen Sie möglicherweise fest, dass für einen bestimmten Medientyp mehr oder weniger Ports erforderlich sind. [Die Anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) und [das Anrufqualitätsdashboard (Call Quality Dashboard, CQD)](turning-on-and-using-call-quality-dashboard.md) pro Benutzer sollten verwendet werden, um eine Entscheidung zur Anpassung von Portbereichen zu treffen, nachdem Teams implementiert wurde, und in regelmäßigen Abständen, wenn sich die Anforderungen ändern.

> [!NOTE]
> Wenn Sie QoS bereits basierend auf Quellportbereichen und DSCP-Markierungen für Skype for Business Online konfiguriert haben, gilt die gleiche Konfiguration für Teams, und es sind keine weiteren Client- oder Netzwerkänderungen an der Zuordnung erforderlich, obwohl Sie [möglicherweise die in Teams verwendeten Bereiche so festlegen](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) müssen, dass sie den Für Skype for Business Online konfigurierten Anforderungen entsprechen.

Wenn Sie zuvor Skype for Business Server lokal bereitgestellt haben, müssen Sie ihre QoS-Richtlinien möglicherweise erneut überprüfen. Passen Sie die Richtlinien an die von Ihnen überprüften Portbereichseinstellungen an, um eine qualitativ hochwertige Benutzererfahrung für Teams bereitzustellen.

## <a name="validate-your-qos-implementation"></a>Überprüfen der QoS-Implementierung

Damit QoS effektiv ist, muss der vom Gruppenrichtlinienobjekt festgelegte DSCP-Wert an beiden Enden eines Aufrufs vorhanden sein. Wenn Sie den vom Teams-Client generierten Datenverkehr analysieren, können Sie überprüfen, ob der DSCP-Wert nicht geändert oder entfernt wird, wenn sich der Datenverkehr der Teams-Workload durch das Netzwerk bewegt.

Vorzugsweise erfassen Sie den Datenverkehr am Netzwerkausgangspunkt. Sie können die Portspiegelung auf einem Switch oder Router verwenden, um dies zu unterstützen.

## <a name="implement-qos-for-other-devices"></a>Implementieren von QoS für andere Geräte

Lesen Sie diese Themen, um Informationen zur Implementierung von QoS für Intune, Surface, iOS, Android und Mac zu finden.

- [QoS für Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS für Surface Hub](/surface-hub/surface-hub-qos)

- [QoS für iOS, Android und Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Verwandte Themen

- [Video: Netzwerkplanung](https://aka.ms/teams-networking)

- [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

- [Implementieren von QoS im Teams-Client](QoS-in-Teams-clients.md)
