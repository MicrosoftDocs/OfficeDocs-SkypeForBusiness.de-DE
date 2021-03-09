---
title: Quality of Service in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für die Dienstqualität (Quality of Service, QoS) in Microsoft Teams vorbereiten.
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
ms.openlocfilehash: c07e3e71d391123d34ae64ebf5806c090c29a29d
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558204"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams

Quality of Service (QoS) in Microsoft Teams ermöglicht echtzeitmäßigen Netzwerkdatenverkehr, der auf Netzwerkverzögerungen (z. B. Sprach- oder Videodatenströme) reagieren muss, vor weniger sensiblem Datenverkehr "in Linie zu schneiden" (z. B. das Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum Herunterladen kein großer Deal ist). QoS verwendet Windows-Gruppenrichtlinienobjekte und portbasierte Zugriffssteuerungslisten, um alle Pakete in Echtzeitdatenströmen zu identifizieren und zu kennzeichnen. Dies hilft Ihrem Netzwerk, Sprach-, Video- und Bildschirmfreigabestreams einen dedizierten Teil der Netzwerkbandbreite zu verleihen.

Wenn Sie eine große Gruppe von Benutzern unterstützen, bei denen eines der in diesem Artikel beschriebenen Probleme auftritt, müssen Sie wahrscheinlich QoS implementieren. Ein kleines Unternehmen mit wenigen Benutzern benötigt möglicherweise kein QoS, aber auch dort sollte es hilfreich sein.

Ohne eine Form von QoS werden möglicherweise die folgenden Qualitätsprobleme in Sprache und Video angezeigt:

- Jitter – Medienpakete, die zu unterschiedlichen Tarifen eintreffen, was dazu führen kann, dass Wörter oder Silben in Anrufen fehlen
- Paketverlust – Pakete werden verworfen, was auch zu einer geringeren Sprachqualität und schwer verständlichen Spracherkennung führen kann
- Verzögerte Roundtripzeit (RTT) – Medienpakete, die lange dauern, bis sie ihre Ziele erreicht haben, was zu merklichen Verzögerungen zwischen zwei Parteien in einer Unterhaltung führt und dazu führt, dass die Personen miteinander sprechen.

Die am wenigsten komplexe Möglichkeit, diese Probleme zu beheben, besteht in der Erhöhung der Größe der Datenverbindungen, sowohl intern als auch aus dem Internet heraus. Da dies häufig kostenentsprechend ist, bietet QoS eine Möglichkeit, die verfügbaren Ressourcen effektiver zu verwalten, anstatt Bandbreite zu addieren. Um Qualitätsprobleme zu beheben, empfiehlt es sich, zuerst QoS zu verwenden und dann nur bei Bedarf Bandbreite hinzuzufügen.

Damit QoS wirksam ist, müssen Sie in der gesamten Organisation konsistente QoS-Einstellungen anwenden. Jeder Teil des Pfads, der Ihre QoS-Prioritäten nicht unterstützt, kann die Qualität von Anrufen, Videos und Bildschirmfreigaben beeinträchtigen. Dies umfasst das Anwenden von Einstellungen auf alle Benutzer-PCs oder -Geräte, Netzwerkschalter, Router für das Internet und den Teams-Dienst.

_Abbildung 1. Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365- oder Office 365-Diensten_

![Abbildung der Beziehung zwischen Netzwerken und Diensten](media/Qos-in-Teams-Image1.png "Die Beziehung zwischen den Netzwerken einer Organisation und Microsoft 365- oder Office 365-Diensten: Lokale Netzwerke und Geräte verbinden sich mit einem Verbindungsnetzwerk, das wiederum eine Verbindung mit Microsoft 365- oder Office 365-Cloud-Voice- und Audiokonferenzdiensten herstellt.")

## <a name="qos-implementation-checklist"></a>Prüfliste für die QoS-Implementierung

Gehen Sie auf hoher Ebene wie folgt vor, um QoS zu implementieren:

1. [Stellen Sie sicher, dass Ihr Netzwerk bereit ist.](#make-sure-your-network-is-ready)

1. [Wählen Sie eine QoS-Implementierungsmethode aus.](#select-a-qos-implementation-method)

1. [Wählen Sie erste Portbereiche für jeden Medientyp aus.](#choose-initial-port-ranges-for-each-media-type)

1. Implementieren von QoS-Einstellungen:
   1. Auf Clients, die ein Gruppenrichtlinienobjekt (GPO) zum Festlegen [von Clientgeräteportbereichen und -markierungen verwenden.](QoS-in-Teams-clients.md)
   2. Auf Routern (siehe Herstellerdokumentation) oder anderen Netzwerkgeräten. Dies kann portbasierte Zugriffssteuerungslisten (Access Control Lists, ACLs) oder einfach die Definition der QoS-Warteschlangen und DSCP-Markierungen oder alle diese umfassen.

      > [!IMPORTANT]
      > Es wird empfohlen, diese QoS-Richtlinien mithilfe der Clientquellenports und einer Quell- und Ziel-IP-Adresse von "any" zu implementieren. Dadurch wird sowohl der eingehende als auch der ausgehende Mediendatenverkehr im internen Netzwerk abfangen.  

   3. [Legen Sie die Art und Weise für die Verarbeitung des Mediendatenverkehrs für Teams-Besprechungen ein.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Überprüfen Sie Ihre QoS-Implementierung,](#validate-your-qos-implementation) indem Sie den Datenverkehr von Teams im Netzwerk analysieren.

Beachten Sie bei der Vorbereitung der Implementierung von QoS die folgenden Richtlinien:

- Der kürzeste Weg zu Microsoft 365 ist am besten.
- Das Schließen von Ports führt nur zu einer Qualitätsverschlechterung.
- Alle Zwischenhindernisse, z. B. Proxys, werden nicht empfohlen.
- Beschränken Sie die Anzahl der Hops:
  - Client-zu-Netzwerk-Edge – 3 bis 5 Hops
  - ISP zu Microsoft Network Edge – 3 Hops
  - Microsoft-Netzwerkkante bis zum endgültigen Ziel – irrelevant

Informationen zum Konfigurieren von Firewallports finden Sie unter UrLs und [IP-Bereiche von Office 365.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Stellen Sie sicher, dass Ihr Netzwerk bereit ist

Wenn Sie eine QoS-Implementierung in Erwägung ziehen, sollten Sie ihre Bandbreitenanforderungen und andere Netzwerkanforderungen bereits [festgelegt haben.](prepare-network.md)
  
Die Überlastung des Datenverkehrs über ein Netzwerk wirkt sich stark auf die Medienqualität aus. Fehlende Bandbreite führt zu Leistungseinbußen und einer schlechten Benutzererfahrung. Wenn die Akzeptanz und Nutzung von Teams zunimmt, verwenden Sie [Berichte,](use-call-analytics-to-troubleshoot-poor-call-quality.md)Anrufanalyse pro Benutzer und Anrufqualitätsdashboard [(CQD),](turning-on-and-using-call-quality-dashboard.md) um Probleme zu identifizieren und dann Anpassungen mithilfe von QoS und selektiven Bandbreitenzuwächsen zu vornehmen.

### <a name="vpn-considerations"></a>Überlegungen zu VPN

QoS funktioniert nur wie erwartet, wenn es für alle Links zwischen Anrufern implementiert wird. Wenn Sie QoS in einem internen Netzwerk verwenden und sich ein Benutzer von einem Remotespeicherort aus meldet, können Sie nur innerhalb Ihres internen, verwalteten Netzwerks Prioritäten setzen. Obwohl Remotestandorte eine verwaltete Verbindung empfangen können, indem sie ein virtuelles privates Netzwerk (VPN) implementieren, fügt ein VPN inhärent den Paketaufwand hinzu und führt zu Verzögerungen beim Echtzeitdatenverkehr. Es wird empfohlen, den Echtzeitkommunikationsverkehr über ein VPN zu vermeiden.

In einer globalen Organisation mit verwalteten Links, die Kontinente umfassen, empfehlen wir QoS dringend, da die Bandbreite für diese Links im Vergleich zum LAN begrenzt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in QoS-Warteschlangen

Um QoS bereitstellen zu können, müssen Netzwerkgeräte über eine Möglichkeit zum Klassifizieren von Datenverkehr verfügen und in der Lage sein, Sprach- oder Videodaten von anderen Netzwerkdatenverkehren zu unterscheiden.

Wenn der Netzwerkdatenverkehr in einen Router einfing, wird der Datenverkehr in eine Warteschlange gesetzt. Wenn eine QoS-Richtlinie nicht konfiguriert ist, gibt es nur eine Warteschlange, und alle Daten werden als first-in und first-out mit derselben Priorität behandelt. Dies bedeutet, dass der Sprachdatenverkehr (der sehr anfällig für Verzögerungen ist) hinter dem Datenverkehr stecken bleibt, bei dem eine Verzögerung von ein paar zusätzlichen Millisekunden kein Problem wäre.

Wenn Sie QoS implementieren, definieren Sie mehrere Warteschlangen mit einem von mehreren Überlastungsverwaltungsfeatures, z. B. ciscos Prioritätswarteschlange und Klassenbasiertes Gewichtetes Fair [Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) und Features zur Vermeidung von Überlastungen, z. B. gewichtete Zufällige Früherkennung [(WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Abbildung 2. Beispiele für QoS-Warteschlangen_

![Abbildung von QoS-Warteschlangen und Bandbreitenteilung](media/Qos-in-Teams-Image2.png "Die gesamte verfügbare Bandbreite ist auf mehrere Warteschlangen –Audio, Video und anderen Datenverkehr – aufgeteilt, denen unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache Analogie ist, dass QoS virtuelle "Fahrgemeinschaftsspuren" in Ihrem Datennetzwerk erstellt, sodass einige Arten von Daten nie oder nur selten auf eine Verzögerung stoßen. Nachdem Sie diese Fahrspuren erstellt haben, können Sie deren relative Größe anpassen und die verfügbare Verbindungsbandbreite wesentlich effektiver verwalten, während Sie den Benutzern Ihrer Organisation dennoch Unternehmenserfahrungen bieten.

## <a name="select-a-qos-implementation-method"></a>Auswählen einer QoS-Implementierungsmethode

Sie können QoS über portbasierte Tagging implementieren, indem Sie Zugriffssteuerungslisten (Access Control Lists, ACLs) auf den Routern Ihres Netzwerks verwenden. Portbasiertes Tagging ist die zuverlässigste Methode, da es in gemischten Windows-, Mac- und Linux-Umgebungen funktioniert und am einfachsten implementiert werden kann. Mobile Clients bieten keinen Mechanismus zum Kennzeichnen von Datenverkehr mithilfe von DSCP-Werten, daher ist diese Methode erforderlich.  

Mithilfe portbasierter Tagging überprüft der Router Ihres Netzwerks ein eingehendes Paket. Wenn das Paket über einen bestimmten Port oder einen bestimmten Portbereich von Ports eingetroffen ist, identifiziert es es als einen bestimmten Medientyp und fügt es in die Warteschlange für diesen Typ ein, und fügt dem IP-Paketheader eine vordefinierte [DSCP-Markierung](https://tools.ietf.org/html/rfc2474) hinzu, damit andere Geräte den Datenverkehrstyp erkennen und ihm in der Warteschlange Priorität geben können.

Das portbasierte Tagging funktioniert zwar plattformübergreifend, kennzeichnet aber nur den Datenverkehr am WAN-Rand (nicht bis zum Clientcomputer) und verursacht Verwaltungsaufwand. Anweisungen zur Implementierung dieser Methode finden Sie in der Dokumentation des Routerherstellers.

### <a name="insert-dscp-markers"></a>Einfügen von DSCP-Markierungen

Sie können QoS auch implementieren, indem Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) verwenden, um Clientgeräte an das Einfügen einer DSCP-Markierung in IP-Paketüberschriften zu senden, die sie als bestimmten Datenverkehrstyp (z. B. Voice) identifiziert. Router und andere Netzwerkgeräte können so konfiguriert werden, dass sie dies erkennen und den Datenverkehr in eine separate Warteschlange mit höherer Priorität setzen.

Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur für Windows-Clients, die mit der Domäne verbunden sind. Jedes Gerät, das kein mit der Domäne verbundener Windows-Client ist, wird nicht für das DSCP-Tagging aktiviert. Andere Clients, z. B. macOS, verfügen über hart codierte Tags und markieren den Datenverkehr immer.

Auf der Plusseite stellt das Steuern der DSCP-Markierung über GPO sicher, dass alle computer mit Domänen verbunden dieselben Einstellungen erhalten und dass nur ein Administrator sie verwalten kann. Clients, die GPO verwenden können, werden auf dem Ursprungsgerät markiert, und dann können konfigurierte Netzwerkgeräte den Echtzeitdatenstrom durch den DSCP-Code erkennen und ihm eine entsprechende Priorität geben.

### <a name="best-practice"></a>Bewährte Methode

Wir empfehlen, möglichst eine Kombination aus DSCP-Markierungen am Endpunkt und portbasierten ACLs auf Routern zu verwenden. Wenn Sie ein Gruppenrichtlinienobjekt verwenden, um die meisten Clients zu fangen, und auch portbasierte DSCP-Taggings verwenden, wird sichergestellt, dass Mobile, Mac und andere Clients weiterhin (zumindest teilweise) QoS-Behandlung erhalten.

DSCP-Markierungen können mit Portostempeln gleicht werden, die postmitarbeitern angeben, wie dringend die Zustellung ist und wie sie für eine schnelle Zustellung am besten sortiert werden können. Nachdem Sie Ihr Netzwerk so konfiguriert haben, dass Medienstreams in Echtzeit Priorität eingeräumt werden, sollten verlorene Pakete und verspätete Pakete stark abnehmen.

Sobald alle Geräte im Netzwerk die gleichen Klassifizierungen, Markierungen und Prioritäten verwenden, ist es möglich, Verzögerungen, verworfene Pakete und Jitter zu verringern oder zu beseitigen, indem sie die Größe der Portbereiche ändern, die den Warteschlangen zugewiesen sind, die für jeden Datenverkehrstyp verwendet werden. Aus Sicht von Teams ist der wichtigste Konfigurationsschritt die Klassifizierung und Kennzeichnung von Paketen. Damit End-to-End-QoS erfolgreich ist, müssen Sie jedoch auch die Konfiguration der Anwendung sorgfältig an der zugrunde liegenden Netzwerkkonfiguration ausrichten. Sobald QoS vollständig implementiert wurde, stellt die fortlaufende Verwaltung eine Frage der Anpassung der Portbereiche, die jedem Datenverkehrstyp zugewiesen sind, basierend auf den Anforderungen Ihrer Organisation und der tatsächlichen Nutzung.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Auswählen von anfänglichen Portbereichen für jeden Medientyp

Der DSCP-Wert teilt einem entsprechend konfigurierten Netzwerk mit, welche Priorität einem Paket oder Stream zugewiesen werden soll, unabhängig davon, ob die DSCP-Markierung von Clients oder dem Netzwerk selbst basierend auf den ACL-Einstellungen zugewiesen wird. Jede Medienarbeitsauslastung erhält einen eigenen eindeutigen DSCP-Wert (andere Dienste ermöglichen es Workloads möglicherweise, eine DSCP-Markierung gemeinsam zu nutzen, Teams nicht) und einen definierten und separaten Portbereich, der für jeden Medientyp verwendet wird. In anderen Umgebungen ist möglicherweise eine QoS-Strategie vorhanden, die Ihnen hilft, die Priorität von Netzwerkarbeitslasten zu bestimmen.

Die relative Größe der Portbereiche für unterschiedliche Streamingworkloads in Echtzeit legt den Anteil der für diese Arbeitsauslastung verfügbaren Gesamtbandbreite fest. Um zu unserer früheren Post analog zurückzukehren: Ein Brief mit dem Stempel "Air Mail" kann innerhalb einer Stunde zum nächstgelegenen Flughafen genommen werden, während ein kleines Paket mit der Kennzeichnung "Massen-E-Mail" einen Tag warten kann, bevor er auf einer Reihe von Lastwagen landet.

_Empfohlene anfängliche Portbereiche_

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Beachten Sie folgendes, wenn Sie diese Einstellungen verwenden:

- Wenn Sie ExpressRoute in Zukunft implementieren möchten und QoS noch nicht implementiert haben, empfehlen wir, die Richtlinien zu befolgen, damit die DSCP-Werte von Absender zu Empfänger identisch sind.

- Alle Clients, einschließlich mobiler Clients und Teams-Geräte, verwenden diese Portbereiche und sind von jeder von Ihnen implementierten DSCP-Richtlinie betroffen, die diese Quellportbereiche verwendet. Die einzigen Clients, die weiterhin dynamische Ports verwenden, sind browserbasierte Clients (Clients, mit deren Hilfe Teilnehmer an Besprechungen teilnehmen können, indem sie ihren Browser verwenden).

- Obwohl der Mac-Client dieselben Portbereiche verwendet, verwendet er auch hart codierte Werte für Audio (EF) und Video (AF41). Diese Werte können nicht konfiguriert werden.

- Wenn Sie die Portbereiche später anpassen müssen, um die Benutzerfreundlichkeit zu verbessern, können sich die Portbereiche nicht überlappen und sollten aneinandergrenzen.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie zuvor Skype for Business Online, einschließlich QoS-Tagging und Portbereiche, bereitgestellt haben und jetzt bereitstellen. Teams, Teams respektieren die vorhandene Konfiguration und verwenden die gleichen Portbereiche und -tags wie der Skype for Business-Client. In den meisten Fällen ist keine zusätzliche Konfiguration erforderlich.

> [!NOTE]
> Wenn Sie das QoS-Tagging für Anwendungsname über gruppenrichtlinien verwenden, müssen Sie Teams.exe als Anwendungsnamen hinzufügen.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementieren von QoS in Teams unter Windows mit PowerShell

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

In Teams sollten die von den verschiedenen Workloads verwendeten QoS-Quellports aktiv verwaltet und bei Bedarf angepasst werden. Bezogen auf die Tabelle unter [Erste Portbereiche](#choose-initial-port-ranges-for-each-media-type)für jeden Medientyp auswählen, sind die Portbereiche anpassbar, die DSCP-Markierungen können jedoch nicht konfiguriert werden. Nachdem Sie diese Einstellungen implementiert haben, können Sie feststellen, dass für einen bestimmten Medientyp mehr oder weniger Ports erforderlich sind. [Die Anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) pro Benutzer und das Anrufqualitätsdashboard [(Call Quality Dashboard, CQD)](turning-on-and-using-call-quality-dashboard.md) sollten bei der Entscheidung verwendet werden, portierte Bereiche anzupassen, nachdem Teams implementiert wurde, und in regelmäßigen Abständen, wenn sich die Anforderungen ändern.

> [!NOTE]
> Wenn Sie QoS bereits basierend auf Quellportbereichen und DSCP-Markierungen für Skype for Business Online konfiguriert haben, gilt dieselbe Konfiguration für Teams, und es sind keine weiteren Client- oder Netzwerkänderungen an der Zuordnung erforderlich, obwohl Sie möglicherweise die [in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) verwendeten Bereiche so festlegen müssen, dass sie den für Skype for Business Online konfigurierten Einstellungen entsprechen.

Wenn Sie Skype for Business Server zuvor lokal bereitgestellt haben, müssen Sie möglicherweise Ihre QoS-Richtlinien erneut überprüfen. Passen Sie die Richtlinien an die von Ihnen überprüften Portbereichseinstellungen an, um eine benutzerfreundliche Benutzererfahrung für Teams zu bieten.

## <a name="validate-your-qos-implementation"></a>Überprüfen der QoS-Implementierung

Damit QoS wirksam wird, muss der vom Gruppenrichtlinienobjekt festgelegte DSCP-Wert an beiden Enden eines Aufrufs vorhanden sein. Durch Analysieren des vom Teams-Client generierten Datenverkehrs können Sie überprüfen, ob der DSCP-Wert nicht geändert oder entfernt wird, wenn der Datenverkehr der Teams-Arbeitsauslastung durch das Netzwerk bewegt wird.

Vorzugsweise erfassen Sie den Datenverkehr am Netzwerk-Ausgangspunkt. Dazu können Sie die Portspiegelung auf einem Switch oder Router verwenden.

## <a name="implement-qos-for-other-devices"></a>Implementieren von QoS für andere Geräte

In diesen Themen finden Sie Informationen zum Implementieren von QoS für Intune, Surface, iOS, Android und Mac.

- [QoS für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS für Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS für iOS, Android und Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Verwandte Themen

- [Video: Netzwerkplanung](https://aka.ms/teams-networking)

- [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

- [Implementieren von QoS im Teams-Client](QoS-in-Teams-clients.md)
