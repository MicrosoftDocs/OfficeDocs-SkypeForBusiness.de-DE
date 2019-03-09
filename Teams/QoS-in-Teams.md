---
title: Quality of Service in Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Bereiten Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vor.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.qos
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e72b4b4fdfdbe6d31ca3543d23b67cb515568e4f
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494029"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft-Teams

In diesem Artikel helfen Ihnen bei der Vorbereitung des Netzwerks Ihrer Organisation für Quality of Service (QoS) in Microsoft-Teams. Wenn Sie eine große Gruppe von Benutzern unterstützen, und sie die unten aufgeführten Probleme auftreten, müssen Sie QoS zu implementieren. Ein kleines Unternehmen mit wenigen Benutzern möglicherweise QoS nicht erforderlich, aber auch es sollte es hilfreich sein.

QoS ist eine Möglichkeit in Echtzeit Netzwerkverkehr (wie VoIP oder Video-Streams) zulassen, die Beachtung von netzwerkverzögerungen "in der Zeile vor den Datenverkehr, der weniger vertrauliche (wie eine neue app, wobei eine zusätzliche Sekunde bis zu herunterladen große Sache ist nicht herunterladen) ist schneiden" ist. QoS identifiziert und markiert alle Pakete in Echtzeit Streams (mithilfe von Windows Group Policy Objects und routing sogenannten Port-basierte Access Control Lists, Weitere Informationen zu den liegt unter) die dann hilft, Ihr Netzwerk so Sprach-, Video- und Bildschirm freigeben Streams übergeben Sie einen dedizierte Teil der Netzwerkbandbreite.

Ohne eine Form von QoS möglicherweise die folgenden Qualitätsprobleme in Sprach- und Videofunktionen angezeigt:

- Jitter – unterschiedlich dazu führen kann, fehlende Wörter oder Silbenschrift verwenden Anrufe eingehenden Media-Pakete.
- Paketverlust – Pakete, der auch in niedrigeren Sprachqualität und schwerer um zu verstehen, Speech führen kann.
- Roundtripzeit (Zeit) – Media-Pakete, die auf einen längeren Zeitraum ihre Ziele erreichen verzögert wodurch Renderingzeit Verzögerungen zwischen zwei Parteien in einer Unterhaltung verursacht Personen über miteinander kommunizieren.

Die einfachste Möglichkeit, um diese Probleme beheben, so vergrößern Sie die Verbindungen Daten ist sowohl intern und ausgehend in das Internet. QoS bietet, die häufig kostspielig ist, eine Möglichkeit, die Ressourcen effektiver verwalten, anstatt neue Ressourcen haben. Zum vollständig Qualität Beheben von Problemen würden Sie QoS über die Implementierung verwenden und dann hinzufügen Connectivity nur bei Bedarf.

Für QoS wirksam werden, müssen die konsistente QoS-Einstellungen durchgehende in Ihrer Organisation (Dies umfasst alle Benutzer PCs, Netzwerk-Switches und Router mit dem Internet), anwenden, da jeder Teil des Pfads, die zur Unterstützung von QoS-Prioritäten nicht beeinträchtigt werden kann die Qualität der Anrufe, Video- und Bildschirm gemeinsam verwendet.

_Abbildung 1. Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste_

![Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste: lokale Netzwerk und Geräte Kontaktaufnahme mit einem Interconnect-Netzwerk, das wiederum eine Verbindung mit Office 365-Cloud-VoIP und Audiokonferenzen Services herstellt.](media/Qos-in-Teams-Image1.png)

In den meisten Fällen werden im Netzwerk herstellen einer Verbindung mit Ihrem Unternehmen in die Cloud ein nicht verwalteten Netzwerk, in dem Sie zuverlässig QoS-Optionen festgelegt werden können. Eine Auswahl erhältlich, End-to-End-Dienstqualität ist [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), aber es weiterhin wird empfohlen, dass Sie QoS auf Ihrem lokalen Netzwerk implementieren. Die Qualität der Kommunikation in Echtzeit Arbeitslasten in Ihrer Bereitstellung zu erhöhen wird und verringern so genannten Chokepunkten gewährleistet.

## <a name="verify-your-network-is-ready"></a>Stellen Sie sicher, dass Ihr Netzwerk bereit ist.

Wenn Sie eine QoS-Implementierung in Betracht ziehen, sollten Sie bereits Standarddateispeicherort Bandbreite und andere [netzwerkanforderungen](prepare-network.md)ermittelt haben. Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt. Um den Rechner zuzugreifen, wechseln Sie zur [Netzwerk Planner](https://aka.ms/bwcalc/) in MyAdvisor.
  
  Überlastung über ein Netzwerk wird Medienqualität erheblich beeinträchtigen. Fehlender Bandbreite führt zu Leistungseinbußen und benutzerfreundlich. Zunehmender Teams Annahme und Nutzung Verwendung von Berichterstattung, [rufen Sie Analyse, und rufen Sie Qualitätsdashboard](difference-between-call-analytics-and-call-quality-dashboard.md) Probleme zu identifizieren, und stellen Sie mithilfe von QoS und selektive Bandbreite Ergänzungen Adjustments.

### <a name="vpn-considerations"></a>VPN-Aspekte

QoS funktioniert nur wie erwartet, wenn Sie auf alle Verknüpfungen zwischen Anrufer implementiert. Wenn Sie QoS auf einem internen Netzwerk und ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur innerhalb des internen, verwalteten Netzwerks priorisieren. Obwohl Remotestandorten eine verwaltete Verbindung durch die Implementierung eines virtuellen privaten Netzwerks (VPN) empfangen können, fügt Paket Aufwand ein VPN grundsätzlich und erstellt Verzögerungen in Echtzeit-Datenverkehr. Es wird empfohlen, dass Sie vermeiden Sie die Ausführung von Real-Time Communications-Datenverkehr über ein VPN.

> [!NOTE]
> VPN-verbundenen Remotebenutzer sollten implementieren Split-tunneling, um die Qualität des Benutzererlebnisses zu maximieren. Das Dokument [Bereitstellen-Anweisungen-VPN-Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) ist über MyAdvisor verfügbar und finden Sie weitere Informationen.

In einem globalen Unternehmen mit verwalteten Links, die Kontinente umfassen, wird dringend empfohlen QoS, da die Bandbreite für diese Links im Vergleich zu den LAN eingeschränkt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in die QoS-Warteschlangen

Um QoS zu ermöglichen, Netzwerkgeräten benötigen eine Möglichkeit zum Klassifizieren von Datenverkehr und müssen in der Lage, VoIP oder Video von anderen Netzwerkverkehr zu unterscheiden.

Netzwerkverkehr einen Router eingibt, wird der Datenverkehr in einer Warteschlange abgelegt. Wenn eine QoS-Richtlinie ist nicht konfiguriert, es nur eine einzige Warteschlange wird und alle Daten wird behandelt, wie First in, First Out mit derselben Priorität. Dies bedeutet, dass VoIP-Datenverkehr (, sehr groß-und Kleinschreibung zu Verzögerungen) hinter Datenverkehr Neustartzyklus möglicherweise, in dem wäre eine Verzögerung von ein paar zusätzliche Millisekunden ein Problem nicht.

Wenn Sie QoS implementieren, definieren Sie mehrere Warteschlangen mithilfe eines mehrere Überlastung Management-Features (wie Cisco Reihenfolge in der Warteschlange und Klassen basierende gewichteten Fair Berichterstellungsdienst [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) und eine Überlastung Vermeidung Features (z. B. früh zufällige gewichteten Erkennung [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_Abbildung 2. Beispiele für die QoS-Warteschlangen_

![Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.] (media/Qos-in-Teams-Image2.png "Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache entsprechend besteht darin, dass QoS virtuellen erstellt "Fahrgemeinschaften Spuren" in den Daten Netzwerk, sodass einige Datentypen nie oder selten eine Verzögerung auftritt. Nachdem Sie diese Bereiche erstellt haben, können Sie ihre relativen Größe anpassen und viel effektiver verwalten, die Verbindungsbandbreite, die Ihnen beim Übermitteln von weiterhin Business-Klasse Erfahrungen für Benutzer in Ihrer Organisation.

## <a name="select-a-qos-implementation-method"></a>Wählen Sie eine QoS-Implementierung-Methode

Sie konnte QoS über Port-basierte mit Tags auf Routern für Ihr Netzwerk mit Zugriffssteuerungslisten (ACLs) implementieren. Port-basierte tagging ist die zuverlässigste Methode, da es in gemischten Umgebungen für Windows und Mac funktioniert und am einfachsten zu implementieren ist. Mobile-Clients stellen keinen Mechanismus zum Markieren von Datenverkehr mithilfe von DSCP-Werte, damit sie diese Methode erforderlich ist.  

Mit dieser Methode Ihres Netzwerks Router untersucht eingehende Pakete, und wenn das Paket mit einer bestimmten Port oder Bereich von Ports traf, wird als einen bestimmten Medientyp identifiziert und legt es in der Warteschlange für dieses Typs, die IP-Adresse eine festgelegten [DSCP](https://tools.ietf.org/html/rfc2474) -Markierung hinzugefügt Paket-Header, damit andere Geräte dieses Typs Datenverkehr erkennen können, und weisen Sie ihr Priorität in der Warteschlange.

Obwohl dies plattformübergreifend funktioniert, es nur Datenverkehr an den WAN-Rand (ganz nicht auf den Clientcomputer) markiert und Verwaltungsaufwand erstellt. Lesen Sie in der Dokumentation des Herstellers Router Anweisungen zum Implementieren dieser Methode.

* * *

Sie können auch QoS implementiert, indem Sie ein Gruppenrichtlinienobjekt (GPO) Clientgeräte angewiesen, um eine DSCP-Markierung im IP-Paket-Header, die sie als bestimmten Typ Datenverkehr (beispielsweise Voice) identifiziert einzufügen implementieren. Router und andere Netzwerkgeräte können konfiguriert werden, um dies zu erkennen, und platzieren Sie den Datenverkehr in einer separaten, eine höhere Priorität Warteschlange.

Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur für die Domäne eingebundener Windows-Clients. Jedes Gerät, das ein in die Domäne eingebundener Windows-Client wird nicht nicht aktiviert werden, für DSCP markieren. Clients wie Mac OS hartcodierte Tags haben und Datenverkehr werden immer markieren.

Klicken Sie auf das Pluszeichen gewährleistet steuern den DSCP-Markierung über GPO-Seite, dass alle Domäne gehörenden Computer mit denselben Einstellungen empfangen und nur von einem Administrator verwaltet werden kann. Clients, mit dem Gruppenrichtlinienobjekt können auf dem ursprünglichen Gerät markiert, und klicken Sie dann konfigurierten Netzwerkgeräte erkennen, indem Sie die DSCP-Code in Echtzeit Streams und ihm eine entsprechende Priorität können.

* * *

Wir empfehlen eine Kombination von DSCP Auswahlmöglichkeiten an den Endpunkt und Port-basierte ACLs für Router, sofern möglich. Mithilfe eines Gruppenrichtlinienobjekts die meisten Clients abgefangen und auch mithilfe der Port-basierte DSCP-Markierung wird sichergestellt, dass diese Mobile, Mac und andere Clients weiterhin QoS-Behandlung (zumindest teilweise) relevanten Informationen erhalten.

DSCP Auswahlmöglichkeiten können zu Stempeln Porto Statusmodul vergleichbar, die Postleitzahl Mitarbeiter wie dringende die Übermittlung wird und wie am besten für die schnelle Übermittlung Sortierung angeben. Nachdem Sie Ihr Netzwerk in Echtzeit Mediendatenströme Priorität zuweisen, um konfiguriert haben, sollten verloren gegangene Pakete und spät Pakete stark abnehmen.

Nachdem alle Geräte im Netzwerk die gleichen Klassifikationen, Auswahlmöglichkeiten und Prioritäten verwenden, es ist möglich, weniger oder verzögert, Paketverluste und Jitter durch Ändern der Größe des die Portbereiche, die für jeden Datenverkehrstyp verwendeten Warteschlangen zugewiesen. Aus der Sicht Teams die wichtigsten Konfigurationsschritt ist die Klassifizierung und Kennzeichnung der Pakete, aber für End-to-End-QoS erfolgreich durchgeführt werden müssen Sie auch die Konfiguration der Anwendung mit der zugrunde liegenden Netzwerkkonfiguration sorgfältig ausrichten. Sobald QoS vollständig implementiert ist, ist die laufende Verwaltung Frage anpassen die Portbereiche auf jeden Datenverkehrstyp basierend auf den Anforderungen Ihrer Organisation und dem tatsächlichen Verbrauch zugewiesen.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Wählen Sie die anfänglichen Portbereiche für jeden Medientyp

Der DSCP-Wert weist einer entsprechend konfigurierten Netzwerk welche Priorität fest, um ein Paket oder Stream-Objekt übergeben, ob die DSCP-Markierung von Clients oder im Netzwerk basierend auf der Zugriffssteuerungsliste Einstellungen zugewiesen ist. Jede Arbeitslast Media Ruft einen eigene eindeutigen DSCP-Wert (andere Dienste können Arbeitslasten DSCP-Markierung freigeben, Teams nicht) und eine definierte und separate Portbereich für jeden Medientyp verwendet. Anderen Umgebungen möglicherweise eine vorhandene QoS-Strategie an, die Hilfe Sie die Priorität der Netzwerk-Arbeitslasten zu bestimmen.

Die relative Größe die Portbereiche für unterschiedliche Real-Time streaming Arbeitslasten wird den Anteil der gesamten verfügbaren Bandbreite, die auf diese Arbeitslast dedizierten. Zurückkehren zu unserer zuvor postalische entsprechend: Buchstaben mit einer "Air Mail" Stempel möglicherweise gelangen innerhalb einer Stunde zum nächsten Flughafen, während kleinem "Bulk Mail" Mark, bis ein Tag warten vor einer Reihe von LKWs auf Reisen über Land gekennzeichnet.

Die folgende Tabelle zeigt die erforderlichen DSCP Auswahlmöglichkeiten für Teams mit ExpressRoute und die zugeordnete Ports für die Arbeitslast Warteschlangen. Diese Bereiche können als Ausgangspunkt für Kunden verwendet werden, die sich nicht sicher sind, was für die Verwendung in ihrer eigenen Umgebung befinden. Weitere Informationen finden Sie unter [QoS-Anforderungen für ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Anfängliche Portbereiche empfohlen_

|Media-Datenverkehrstyp| Client-Quellportbereich |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000 – 50,019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50,020 – 50,039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Achten Sie auf Folgendes, wenn Sie diese Einstellungen verwenden:

- Wenn Sie in der Zukunft ExpressRoute implementieren möchten und noch nicht noch QoS implementiert, wird empfohlen, dass Sie die Anleitung befolgen, sodass DSCP-Werte vom Absender zum Empfänger identisch sind.
- Alle Clients, einschließlich mobilen Clients und Geräten von Teams, verwenden diese Portbereiche und von einer DSCP-Richtlinie, die Sie implementieren, die diese Quelle Portbereiche verwendet betroffen sind. Die nur Clients, die weiterhin dynamische Ports verwenden, sind die Clients browserbasierte (d. h., diese Clients, mit denen Teilnehmer Besprechungen beitreten, indem Sie mit ihrem Browser).
- Obwohl der Mac-Client dieselben Portbereiche verwendet, verwendet er auch hartcodierte Werte für (Expedited FORWARDING) Audio- und Videofunktionen (AF41). Diese Werte sind nicht konfigurierbar.
- Wenn Sie später die Portbereiche zur Verbesserung der benutzerfreundlichkeit anpassen müssen, wird die Portbereiche können nicht überlappen und nebeneinander sein.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie zuvor Skype für Business Online, einschließlich QoS-Kategorien und Portbereiche bereitgestellt haben und sind nun die Bereitstellung von Teams, Teams werden von der vorhandenen Konfiguration berücksichtigt und verwenden dieselben Portbereiche und tagging als die Skype für Business-Client. In den meisten Fällen wird keine zusätzliche Konfiguration erforderlich sein.

> [!NOTE]
> Wenn Sie Anwendung Namen QoS tagging über Gruppenrichtlinien verwenden, müssen Sie Teams.exe als den Namen der Anwendung hinzufügen.

## <a name="qos-implementation-steps"></a>QoS Implementierungsschritte

Auf einer sehr hohen Ebene erfordert die Implementierung der QoS folgende Schritte aus:

1. [Stellen Sie sicher, dass Ihr Netzwerk bereit ist.](#verify-your-network-is-ready)
2. [Wählen Sie eine QoS-Implementierung-Methode](#select-a-qos-implementation-method)
3. [Wählen Sie die anfänglichen Portbereiche für jeden Medientyp](#choose-initial-port-ranges-for-each-media-type)
4. Implementieren Sie die QoS-Einstellungen:
   1. Auf Clients mithilfe eines Gruppenrichtlinienobjekts festzulegenden [Portbereiche für Client-Gerät und Kennzeichnungen](QoS-in-Teams-clients.md)
   2. Klicken Sie auf (siehe die Dokumentation des Herstellers) Router oder andere Netzwerkgeräte. Dies kann Port-basierte ACLs einschließen oder die QoS-Warteschlangen und DSCP Auswahlmöglichkeiten oder alle diese einfach zu definieren.

      > [!IMPORTANT]
      > Es wird empfohlen, implementieren diese QoS-Richtlinien mithilfe der Quelle Clientports und einer Quell- und Ziel-IP-Adresse des "beliebigen". Dies fängt beide ein- und ausgehenden Datenverkehr im internen Netzwerk.  

   3. [Teams Admin](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) Center
5. [Überprüfen Sie die QoS-Implementierung](#validate-the-qos-implementation) von Teams Datenverkehr im Netzwerk zu analysieren.

Als Vorbereitung der QoS zu implementieren, sollten beachten Sie die folgenden Richtlinien:

- Der kürzeste Pfad zu Office 365 ist am besten.
- Schließen von Ports wird nur zu Qualität Beeinträchtigung führen.
- Hindernisse dazwischen liegenden wie Proxys, werden nicht empfohlen.
- Grenzwert für die Anzahl von Hops:
  - Client Netzwerkgrenze – 3 bis 5 Hops.
  - Internetdienstanbieter Microsoft Netzwerkgrenze – 3 hops
  - Microsoft Netzwerkgrenze zum endgültigen Ziel – irrelevante

Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Verwalten von Quellports in der Verwaltungskonsole Teams

In Teams, sollte QoS-Quellports, die von den verschiedenen Arbeitslasten aktiv sein verwaltet und gegebenenfalls angepasst. In Bezug auf die Tabelle in [Portbereiche und DSCP Auswahlmöglichkeiten](#port-ranges-and-dscp-markings)Sie die Portbereiche veränderbaren sind, aber die DSCP-Auswahlmöglichkeiten sind nicht konfigurierbar. Nachdem Sie diese Einstellungen implementiert haben, können Sie feststellen, dass mehr oder weniger Ports für einen bestimmten Medientyp benötigt werden. [Analytics aufrufen, und rufen Sie Qualitätsdashboard](difference-between-call-analytics-and-call-quality-dashboard.md) sollte bei der Entscheidung Portbereiche anpassen, nachdem Teams implementiert wurde, sowie in regelmäßigen Abständen Änderung muss verwendet werden.

> [!NOTE]
> Wenn Sie QoS basierend auf Quelle Portbereiche und DSCP Auswahlmöglichkeiten für Skype für Business Online bereits konfiguriert haben, gilt die gleiche Konfiguration für Teams und keine weiteren Client oder netzwerkänderungen auf die Zuordnung ist erforderlich, festgelegt, wenn Sie auf [Bereiche festgelegt werden Teams Admin Center verwendet](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) übereinstimmen, was für Skype für Business Online konfiguriert wurde.

Wenn Sie zuvor Skype für Business Server lokal bereitgestellt haben, müssen Sie die QoS-Richtlinien neu zu überprüfen, und passen sie nach Bedarf Bereich Einstellungen für externe Ports entsprechen, die Sie sichergestellt haben, bieten eine Benutzeroberfläche zur Verfügung Qualität für Teams.

## <a name="validate-the-qos-implementation"></a>Überprüfen Sie die QoS-Implementierung

Für QoS wirksam werden, die DSCP durch das Gruppenrichtlinienobjekt festgelegter Wert müssen an beiden Enden eines Aufrufs vorhanden sein. Analysieren Sie den Datenverkehr vom Client Teams generiert, stellen Sie sicher, dass der DSCP-Wert wird nicht geändert oder entfernt, wenn der Teams Arbeitslast Datenverkehr Verschiebungen durchläuft über das Netzwerk.

Vorzugsweise, erfassen Sie Datenverkehr am Netzwerk Austritt. Sie können Anschluss Spiegelung für eine Switch- oder Router um dabei zu unterstützen.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Verwenden des Netzwerkmonitors DSCP-Werte überprüfen

Netzwerkmonitor ist ein Tool, um den Netzwerkverkehr zu analysieren [von Microsoft herunterladen](https://www.microsoft.com/download/4865) können.

1. Verbinden Sie auf dem PC Netzwerkmonitor ausgeführt wird auf den Port, der für die Spiegelung von Port und Erfassung von Paketen Start konfiguriert wurde.

2. Tätigen eines Anrufs mit dem Teams. Stellen Sie sicher, dass Media hergestellt wurde, bevor der Anruf wird beendet.

3. Beenden Sie die Aufzeichnung.

4. Klicken Sie im Feld **Anzeigefilter** verwenden Sie die Quell-IP-Adresse des Computers, der den Anruf getätigt hat, und verfeinern Sie den Filter, indem Sie definieren DSCP-Wert (hex-0xb8) 46 als Suchkriterien, wie im folgenden Beispiel dargestellt:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8

    ![Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.] (media/Qos-in-Teams-Image4.png "Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.")

5. **Übernehmen** Sie den Filter aktivieren auswählen.

6. Wählen Sie im Fenster **Zusammenfassung Frame** das erste UDP-Paket aus.

7. In Frame im Dialogfeld **Details** der erweitern Sie das Listenelement IPv4, und notieren Sie den Wert am Ende der Zeile, die mit **DSCP**beginnt.

    ![Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.] (media/Qos-in-Teams-Image5.png "Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.")

In diesem Beispiel wird der DSCP-Wert auf 46 festgelegt. Dies ist korrekt, da der verwendete Quellport 50019, ist gibt an, dass es sich um eine VoIP-Arbeitslast handelt.

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden.

## <a name="more-information"></a>Weitere Informationen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)

[Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

[ExpressRoute QoS-Anforderungen](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
