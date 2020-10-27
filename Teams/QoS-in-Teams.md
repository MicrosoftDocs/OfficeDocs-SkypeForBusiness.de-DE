---
title: Quality of Service in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Hier erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vorbereiten.
localization_priority: Normal
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
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766578"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams

Quality of Service (QoS) in Microsoft Teams ermöglicht Netzwerkdatenverkehr in Echtzeit, der auf Netzwerkverzögerungen (beispielsweise sprach-oder Videostreams) sensibel ist, um vor dem Verkehr, der weniger sensibel ist (wie beim Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum Herunterladen nicht sehr viel ist), "Cut in der Zeile" zu erfolgen. QoS verwendet Windows-Gruppenrichtlinienobjekte und Port basierte Zugriffssteuerungslisten, um alle Pakete in Echtzeit-Streams zu identifizieren und zu kennzeichnen. Auf diese Weise kann Ihr Netzwerk sprach-, Video-und Bildschirmfreigabe Datenströmen einen dedizierten Teil der Netzwerkbandbreite verleihen.

Wenn Sie eine große Gruppe von Benutzern unterstützen, bei denen Probleme auftreten, die in diesem Artikel beschrieben werden, müssen Sie wahrscheinlich QoS implementieren. Ein kleines Unternehmen mit wenigen Benutzern benötigt möglicherweise keine QoS, aber auch dort sollte es hilfreich sein.

Ohne eine Art von QoS sehen Sie möglicherweise die folgenden Qualitätsprobleme in Sprache und Video:

- Jitter – Medienpakete, die zu unterschiedlichen Tarifen ankommen, was zu fehlenden Wörtern oder Silben bei Anrufen führen kann
- Paketverlust – Pakete sind gesunken, was auch zu einer niedrigeren Sprachqualität und einer schwer verständlichen Sprache führen kann
- Verzögerte Roundtrip-Zeit (Round-Trip Time, RTT) – Medienpakete dauern lange, bis Sie Ihre Ziele erreicht haben, was zu spürbaren Verzögerungen zwischen zwei Gesprächspartnern führt und dazu führt, dass Personen sich über einander unterhalten.

Die am wenigsten komplexe Möglichkeit, diese Probleme zu beheben, besteht darin, die Größe der Datenverbindungen sowohl intern als auch über das Internet zu erhöhen. Da dies oft kostengünstig ist, bietet QoS eine Möglichkeit, die Ressourcen effektiver zu verwalten, anstatt eine Bandbreite hinzuzufügen. Um Qualitätsprobleme zu beheben, empfehlen wir, zunächst QoS zu verwenden und dann die Bandbreite nur bei Bedarf hinzuzufügen.

Damit QoS effektiv ist, müssen Sie in Ihrer Organisation konsistente QoS-Einstellungen anwenden. Jeder Teil des Pfads, der Ihre QoS-Prioritäten nicht unterstützt, kann die Qualität von anrufen, Video und Bildschirmübertragung beeinträchtigen. Dies umfasst das Anwenden von Einstellungen auf alle Benutzer-PCs oder-Geräte, Netzwerk-Switches, Router zum Internet und den Teams-Service.

_Abbildung 1 Die Beziehung zwischen den Netzwerken einer Organisation und den Microsoft 365-oder Office 365-Diensten_

![Abbildung der Beziehung zwischen Netzwerken und Diensten](media/Qos-in-Teams-Image1.png "Die Beziehung zwischen den Netzwerken einer Organisation und den Microsoft 365-oder Office 365-Diensten: lokales Netzwerk und Geräte stellen eine Verbindung mit einem Interconnect-Netzwerk her, das wiederum mit Microsoft 365-oder Office 365-Cloud-sprach-und-Konferenzdiensten verbunden ist.")

## <a name="qos-implementation-checklist"></a>Checkliste für QoS-Implementierung

Führen Sie auf einem hohen Niveau die folgenden Schritte aus, um QoS zu implementieren:

1. [Sicherstellen, dass Ihr Netzwerk bereit ist](#make-sure-your-network-is-ready)

1. [Auswählen einer QoS-Implementierungsmethode](#select-a-qos-implementation-method)

1. [Auswählen von anfänglichen Portbereichen für die einzelnen Medientypen](#choose-initial-port-ranges-for-each-media-type)

1. Implementieren von QoS-Einstellungen:
   1. Auf Clients, die ein Gruppenrichtlinienobjekt (GPO) verwenden, um [Clientgeräte-Portbereiche und-Markierungen einzurichten](QoS-in-Teams-clients.md)
   2. Auf Routern (siehe Herstellerdokumentation) oder auf anderen Netzwerkgeräten. Dies kann portbasierte Zugriffssteuerungslisten (ACLs) oder einfach die Definition von QoS-Warteschlangen und DSCP-Markierungen oder all diesen umfassen.

      > [!IMPORTANT]
      > Es wird empfohlen, diese QoS-Richtlinien mithilfe der Clientports und einer Quell-und Ziel-IP-Adresse von "Any" zu implementieren. Dadurch wird sowohl ein-und ausgehenden Mediendatenverkehr im internen Netzwerk abgefangen.  

   3. [Bestimmen, wie Mediendatenverkehr für Teams-Besprechungen gehandhabt werden soll](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. Über [prüfen Sie Ihre QoS-Implementierung](#validate-your-qos-implementation) , indem Sie den Datenverkehr des Teams im Netzwerk analysieren.

Beachten Sie beim Vorbereiten der Implementierung von QoS die folgenden Richtlinien:

- Der kürzeste Weg zu Microsoft 365 ist am besten
- Das Schließen von Ports führt nur zur Verschlechterung der Qualität
- Keine Hindernisse dazwischen, wie etwa Proxies, werden nicht empfohlen
- Beschränken Sie die Anzahl der Hops:
  - Client-zu-Netzwerk-Edge – 3 bis 5 Hops
  - ISP zu Microsoft Network Edge – 3 Hops
  - Microsoft-Netzwerk-Edge bis zum endgültigen Zielort – irrelevant

Informationen zum Konfigurieren von Firewall-Ports finden Sie unter [Office 365-URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Sicherstellen, dass Ihr Netzwerk bereit ist

Wenn Sie eine QoS-Implementierung in Betracht ziehen, sollten Sie bereits ihre Bandbreitenanforderungen und andere [Netzwerkanforderungen](prepare-network.md)festgelegt haben.
  
Verkehrsüberlastung in einem Netzwerk beeinträchtigt die Medienqualität erheblich. Mangelnde Bandbreite führt zu Leistungseinbußen und einer schlechten Benutzererfahrung. Wenn die Akzeptanz und Nutzung von Teams wächst, verwenden Sie Berichterstellung, [pro-Benutzer-anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md)und Dashboard für die [Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md) , um Probleme zu erkennen und Anpassungen mithilfe von QoS und selektiver Bandbreiten Erweiterungen vorzunehmen.

### <a name="vpn-considerations"></a>VPN-Überlegungen

QoS funktioniert nur erwartungsgemäß, wenn Sie für alle Verknüpfungen zwischen Anrufern implementiert werden. Wenn Sie QoS in einem internen Netzwerk verwenden und sich ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur in Ihrem internen, verwalteten Netzwerk priorisiert werden. Obwohl Remotestandorte eine verwaltete Verbindung erhalten können, indem Sie ein VPN (virtuelles privates Netzwerk) implementieren, fügt ein VPN inhärent einen Paket Overhead hinzu und verursacht Verzögerungen im Echtzeitverkehr. Wir empfehlen, dass Sie den Echt Zeit Kommunikationsverkehr über ein VPN vermeiden.

In einer globalen Organisation mit verwalteten Links, die sich über Kontinente erstrecken, empfehlen wir QoS, da die Bandbreite für diese Links im Vergleich zum LAN begrenzt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in QoS-Warteschlangen

Für die Bereitstellung von QoS müssen Netzwerkgeräte eine Möglichkeit zum Klassifizieren des Datenverkehrs und zur Unterscheidung von Sprach-oder Videodaten von anderem Netzwerkdatenverkehr aufweisen.

Wenn Netzwerkdatenverkehr in einen Router eintritt, wird der Datenverkehr in eine Warteschlange gestellt. Wenn eine QoS-Richtlinie nicht konfiguriert ist, gibt es nur eine Warteschlange, und alle Daten werden als First-in-First-Out mit der gleichen Priorität behandelt. Das bedeutet, dass der VoIP-Datenverkehr (der sehr anfällig für Verzögerungen ist) möglicherweise hinter dem Datenverkehr hängen bleibt, in dem eine Verzögerung von einigen zusätzlichen Millisekunden kein Problem darstellt.

Wenn Sie QoS implementieren, definieren Sie mehrere Warteschlangen mit einer von mehreren Funktionen zur Engpass Verwaltung, wie beispielsweise die Priorität Queuing von Cisco und die [Klasse-based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) und Engpass Vermeidungs Features, wie etwa die [gewichtete zufällige Früherkennung (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Abbildung 2. Beispiele für QoS-Warteschlangen_

![Illustration von QoS-Warteschlangen und Bandbreiten Teilung](media/Qos-in-Teams-Image2.png "Die gesamte verfügbare Bandbreite ist auf mehrere Warteschlangen – Audio, Video und anderer Datenverkehr – aufgeteilt, denen unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache Analogie ist, dass QoS virtuelle "Fahrgemeinschaften-Lanes" in Ihrem Datennetzwerk erstellt, sodass einige Datentypen nie oder nur selten einer Verzögerung begegnen. Nachdem Sie diese Spuren erstellt haben, können Sie Ihre relative Größe anpassen und die von Ihnen genutzte Verbindungsbandbreite effektiver verwalten, während Sie dennoch unternehmensspezifische Erfahrungen für die Benutzer Ihrer Organisation bereitstellen.

## <a name="select-a-qos-implementation-method"></a>Auswählen einer QoS-Implementierungsmethode

Sie können QoS mithilfe von Port basiertem Tagging implementieren, indem Sie die Zugriffssteuerungslisten (ACLs) auf den Routern Ihres Netzwerks verwenden. Die Port basierte Kennzeichnung ist die zuverlässigste Methode, da Sie in gemischten Windows-, Mac-und Linux-Umgebungen funktioniert und am einfachsten zu implementieren ist. Mobile Clients bieten keinen Mechanismus zum Kennzeichnen von Datenverkehr mithilfe von DSCP-Werten, sodass diese Methode erforderlich ist.  

Bei Verwendung von Port basiertem Tagging untersucht der Router Ihres Netzwerks ein eingehendes Paket, und wenn das Paket mit einem bestimmten Port oder Portbereich eingetroffen ist, wird es als bestimmter Medientyp identifiziert und in die Warteschlange für diesen Typ eingefügt, wodurch dem IP-Paketheader eine vordefinierte [DSCP](https://tools.ietf.org/html/rfc2474) -Markierung hinzugefügt wird, damit andere Geräte den Datenverkehrstyp erkennen und ihm Priorität

Obwohl die Portierungs basierte Kennzeichnung plattformübergreifend funktioniert, kennzeichnet Sie nur den Datenverkehr am WAN-Edge (nicht bis zum Clientcomputer) und führt zu Verwaltungsaufwand. Anweisungen zur Implementierung dieser Methode finden Sie in der vom Router-Hersteller bereitgestellten Dokumentation.

### <a name="insert-dscp-markers"></a>Einfügen von DSCP-Markierungen

Sie können auch QoS implementieren, indem Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) verwenden, um Clientgeräte zu verweisen, um eine DSCP-Markierung in IP-Paket Headern einzufügen, die diese als bestimmten Datenverkehrstyp identifizieren (beispielsweise "Voice"). Router und andere Netzwerkgeräte können konfiguriert werden, um dies zu erkennen und den Datenverkehr in eine separate Warteschlange mit höherer Priorität zu versetzen.

Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur bei Windows-Clients, die mit der Domäne verbunden sind. Jedes Gerät, das kein mit der Domäne verbundener Windows-Client ist, ist für DSCP-Tagging nicht aktiviert. Clients wie Mac OS verfügen über hart codierte Tags und kennzeichnen immer den Datenverkehr.

Auf der positiven Seite wird durch die Steuerung der DSCP-Kennzeichnung über GPO sichergestellt, dass alle von der Domäne verbundenen Computer die gleichen Einstellungen erhalten und dass nur ein Administrator Sie verwalten kann. Clients, die das Gruppenrichtlinienobjekt verwenden können, werden auf dem ursprünglichen Gerät markiert, und dann können konfigurierte Netzwerkgeräte den echtzeitdatenstrom mithilfe des DSCP-Codes erkennen und ihm eine entsprechende Priorität zuweisen.

### <a name="best-practice"></a>Bewährte Methode

Wenn möglich, empfehlen wir eine Kombination aus DSCP-Markierungen am Endpunkt und portbasierten ACLs für Router. Wenn Sie ein Gruppenrichtlinienobjekt verwenden, um die Mehrzahl der Clients zu erfassen, und außerdem mithilfe von Port basierter DSCP-Tagging, wird sichergestellt, dass Mobile, Mac und andere Clients weiterhin QoS-Behandlung erhalten (zumindest teilweise).

DSCP-Markierungen können mit Briefmarken verglichen werden, die für Postangestellte angeben, wie wichtig die Zustellung ist und wie Sie für eine schnelle Zustellung bestens sortiert werden. Nachdem Sie Ihr Netzwerk so konfiguriert haben, dass es den Medienströmen in Echtzeit Vorrang gibt, sollten verloren gegangene Pakete und verspätete Pakete erheblich abnehmen.

Nachdem alle Geräte im Netzwerk die gleichen Klassifizierungen, Markierungen und Prioritäten verwendet haben, ist es möglich, Verzögerungen, verworfene Pakete und Jitter zu verringern oder zu eliminieren, indem die Größe der Portbereiche geändert wird, die den für die einzelnen Datenverkehrstypen verwendeten Warteschlangen zugewiesen sind. Aus Sicht des Teams ist der wichtigste Konfigurationsschritt die Klassifizierung und Kennzeichnung von Paketen. Damit die End-to-End-QoS erfolgreich ist, müssen Sie die Konfiguration der Anwendung aber auch sorgfältig mit der zugrunde liegenden Netzwerkkonfiguration ausrichten. Sobald QoS vollständig implementiert ist, ist die laufende Verwaltung eine Frage der Anpassung der Portbereiche, die den einzelnen Datenverkehrstypen entsprechend den Anforderungen Ihrer Organisation und der tatsächlichen Nutzung zugewiesen sind.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Auswählen von anfänglichen Portbereichen für die einzelnen Medientypen

Der DSCP-Wert weist einem entsprechend konfigurierten Netzwerk die Priorität zu, die einem Paket oder Datenstrom zugewiesen werden soll, unabhängig davon, ob das DSCP-Zeichen von Clients oder dem Netzwerk selbst basierend auf ACL-Einstellungen zugewiesen wird. Jede Medien Auslastung erhält ihren eigenen eindeutigen DSCP-Wert (andere Dienste können es möglicherweise ermöglichen, dass Arbeitslasten eine DSCP-Markierung, Teams nicht) und einen definierten und separaten Portbereich für jeden Medientyp verwenden. In anderen Umgebungen ist möglicherweise eine vorhandene QoS-Strategie vorhanden, die Ihnen bei der Ermittlung der Priorität von Netzwerkarbeitsauslastungen hilft.

Die relative Größe der Portbereiche für verschiedene Echtzeit-Streaming-Arbeitsauslastungen legt den Anteil der gesamten verfügbaren Bandbreite für diese Arbeitsauslastung fest. So kehren Sie zu unserer früheren postalischen Analogie zurück: ein Brief mit dem Stempel "Luft Post" kann innerhalb einer Stunde zum nächstgelegenen Flughafen abgeholt werden, während ein kleines Paket, das als "Bulk-Mail" markiert ist, einen Tag warten kann, bevor er auf einer Reihe von Lastwagen über Land reist.

_Empfohlene anfängliche Portbereiche_

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Beachten Sie Folgendes, wenn Sie diese Einstellungen verwenden:

- Wenn Sie beabsichtigen, Express Route in Zukunft zu implementieren und QoS noch nicht implementiert haben, empfehlen wir, dass Sie die Richtlinien befolgen, damit DSCP-Werte vom Absender zum Empfänger identisch sind.
- Alle Clients, einschließlich mobiler Clients und Teams, verwenden diese Portbereiche und sind von der von Ihnen implementierten DSCP-Richtlinie betroffen, die diese Quell Portbereiche verwendet. Die einzigen Clients, die weiterhin dynamische Ports verwenden, sind die browserbasierten Clients (Clients, mit denen Teilnehmer mithilfe Ihres Browsers an Besprechungen teilnehmen können).
- Obwohl der Mac-Client dieselben Portbereiche verwendet, werden auch hart codierte Werte für Audio (EF) und Video (AF41) verwendet. Diese Werte sind nicht konfigurierbar.
- Wenn Sie die Portbereiche später anpassen müssen, um die Benutzerfreundlichkeit zu verbessern, können sich die Portbereiche nicht überlappen und benachbart sein.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie zuvor Skype for Business Online, einschließlich QoS-Tagging und Portbereiche, bereitgestellt haben und jetzt bereitstellen. Teams, Teams respektieren die vorhandene Konfiguration und verwenden die gleichen Portbereiche und Tagging wie der Skype for Business-Client. In den meisten Fällen wird keine zusätzliche Konfiguration benötigt.

> [!NOTE]
> Wenn Sie das QoS-Tagging von Anwendungsnamen über Gruppenrichtlinien verwenden, müssen Sie Teams.exe als Anwendungsnamen hinzufügen.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementieren von QoS in Microsoft Teams mithilfe von PowerShell

**QoS für Audio einstellen**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**QoS für Video einrichten**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**QoS für Freigaben einrichten**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Verwalten von Quell Anschlüssen im Team Admin Center

In Teams sollten QoS-Quell Anschlüsse, die von den unterschiedlichen Arbeitslasten verwendet werden, aktiv verwaltet und bei Bedarf angepasst werden. In Bezug auf die Tabelle in [Wählen Sie anfängliche Portbereiche für jeden Medientyp](#choose-initial-port-ranges-for-each-media-type)aus, sind die Portbereiche einstellbar, die DSCP-Markierungen können aber nicht konfiguriert werden. Nachdem Sie diese Einstellungen implementiert haben, stellen Sie möglicherweise fest, dass für einen bestimmten Medientyp mehr oder weniger Ports erforderlich sind. [Pro-Benutzer-anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) und [Anruf Qualitäts Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) sollten dazu verwendet werden, eine Entscheidung zur Anpassung von Portbereichen nach der Implementierung von Teams und in regelmäßigen Abständen zu ändern.

> [!NOTE]
> Wenn Sie QoS bereits auf der Grundlage von Quell Portbereichen und DSCP-Markierungen für Skype for Business Online konfiguriert haben, gilt die gleiche Konfiguration für Teams, und es werden keine weiteren Client-oder Netzwerkänderungen an der Zuordnung benötigt, obwohl Sie möglicherweise [die in Teams verwendeten Bereiche](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) entsprechend der Konfiguration für Skype for Business Online angeben müssen.

Wenn Sie zuvor Skype for Business Server lokal bereitgestellt haben, müssen Sie möglicherweise Ihre QoS-Richtlinien erneut überprüfen. Passen Sie die Richtlinien an die von Ihnen überprüfte Portbereichs Einstellungen an, um eine hohe Benutzerfreundlichkeit für Teams zu gewährleisten.

## <a name="validate-your-qos-implementation"></a>Überprüfen Ihrer QoS-Implementierung

Damit QoS effektiv ist, muss der DSCP-Wert, der vom GPO gesetzt wird, an beiden Enden eines Anrufs vorhanden sein. Durch Analysieren des vom Team Client generierten Datenverkehrs können Sie sicherstellen, dass der DSCP-Wert nicht geändert oder entfernt wird, wenn der Arbeits Auslastungsdaten Verkehr der Teams über das Netzwerk verschoben wird.

Am besten erfassen Sie den Datenverkehr am Netzwerk Ausgangspunkt. Sie können die Portspiegelung auf einem Switch oder Router verwenden, um dies zu unterstützen.

## <a name="implement-qos-for-other-devices"></a>Implementieren von QoS für andere Geräte

In diesen Themen finden Sie Informationen zum Implementieren von QoS für InTune, Surface, Ios, Android und Mac.

- [QoS für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS für Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS für IOS, Android und Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Verwandte Themen

- [Video: Netzwerkplanung](https://aka.ms/teams-networking)

- [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

- [Implementieren von QoS im Team-Client](QoS-in-Teams-clients.md)
