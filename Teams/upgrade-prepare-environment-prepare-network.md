---
title: Bereiten Sie Ihr Netzwerk für Microsoft-Teams |  Firewall-Portanforderungen
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Verwenden Sie diese Anleitung, um Ihr Netzwerk für die Bereitstellung und den Rollout von Microsoft Teams vorzubereiten.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 950786a6d1014b322c76d1f4cd35afaec789f177
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771782"
---
![Phasen der Upgrade-Strategie, mit Schwerpunkt auf der technischen Bereitschaft](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Strategie, mit Schwerpunkt auf der technischen Bereitschaft")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Sehen Sie sich die folgenden Sitzung erfahren, wie Sie Teams nutzt Ihr Netzwerk und am besten für die optimale Netzwerkkonnektivität planen: [Teams Netzwerkplanung](https://aka.ms/teams-networking)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Bereiten Sie Ihr Netzwerk für das Upgrade auf Teams

Wenn Sie Audio-, Video- oder Besprechungen bereitstellen, können Sie einige zusätzliche Schritte zur Optimierung Ihres Netzwerks für diese Funktionalität nutzen. Teams verwendet die Audio- und Videodaten-Technologie (Codecs), die für geeignet – und daher eine bessere Leistung unter – am Netzwerk-Bedingungen. Um eine optimale und konsistente Leistung sichergestellt ist, sollten Sie Ihr Netzwerk für Teams vorbereiten.

![Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf das Netzwerk.] (media/evaluate-my-environment-image1.png "Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf das Netzwerk.")

## <a name="why-should-you-prepare-your-network"></a>Warum sollten Sie Ihr Netzwerk vorbereiten?

Bevor wir die auszuführenden Schritte betrachten, ist es wichtig zu verstehen, was die Leistung des Teams und zum anschließenden Benutzer Glück und Kundenzufriedenheit auswirken können. Drei wichtigsten Risikobereiche können wie Benutzer Netzwerkqualität Wahrnehmung beeinflussen:

- Nicht genügend Bandbreite

- Firewall und des Proxys Popupblockern

- Netzwerk Hörvermögen wie Jitter und Paketverlust

Die unten beschriebenen Schritte helfen Ihnen bei der Bestimmung, ob Ihre Bereitstellung möglicherweise durch eine der folgenden Faktoren beeinflusst werden und helfen, die Sie nach einer Lösung bewegen. Ihr Netzwerk vorbereiten, die Fehler aufweisen führt zum unzufrieden Benutzer wahrscheinlich und kostspielig und Ad-hoc-behebt. Nach der Vorbereitung Ihres Netzwerks – und Ihre Organisation – für Teams, Sie Ihre Chancen, Erfolg drastisch erhöhen.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Bandbreitenplanung


Microsoft-Teams, können Sie die beste Audio-, Video- und unabhängig von den netzwerkbedingungen Erfahrung von Inhalten. Mit den Variablen Codecs können Medien in Umgebungen mit minimaler Beeinträchtigung eingeschränkter Bandbreite ausgehandelt werden. Aber wo Bandbreite kein Belang ist, können Erfahrungen optimiert für die Qualität, videoauflösung 1080p, einschließlich von bis zu 30 f/s für Video und 15fps für Inhalte und Audio mit hoher Qualität.


Dieser Artikel beschreibt eine präzise Version wie Bandbreite von Teams Echtzeit Audio-, Video- und Desktopfreigabe Modalitäten in verschiedene Anwendungsfälle genutzt wird. Teams ist immer auf bandbreitenauslastung konservativ und HD-Videoqualität in unter 1.2Mbps realisiert werden können. Die tatsächlichen Bandbreitenverbrauch in einzelnen a/v-Anruf oder Besprechung, hängt Grundlage verschiedener Faktoren, wie video Layout, Auflösung und Videoframes pro Sekunde.Wenn mehr Bandbreite verfügbar ist werden die Qualität und Nutzung am besten zu erhöhen.

|Bandwidth(Up/Down) |Szenarien |
|---|---|
|30 Kbit/s |Aufrufen von Peer-zu-Peer-audio |
|130 Kbit/s |Peer-zu-Peer-audio Anruf- und Bildschirmfreigabe |
|500 KBit/s |Peer-zu-Peer-Bildqualität 360p mit 30fps aufrufen |
|1.2 Mbit/s |Durch den Aufruf von Auflösung von HD 720p mit 30fps Videoqualität HD Peer-zu-peer |
|1,5 Mbit/s |Durch den Aufruf von Auflösung von HD 1080p mit 30fps Videoqualität HD Peer-zu-peer |
|500 KBit/s/1 Mbit/s |Gruppe Video aufrufen |
|1 Mbit/s/2 Mbit/s |HD-Gruppe video aufrufen (540p Videos auf 1080p Bildschirm) |

### <a name="local-internet-egress"></a>Lokaler Internetausgang

Viele Netzwerke wurden für die Verwendung einer Hub-Spoke-Topologie entworfen. In dieser Topologie durchläuft der Internetdatenverkehr normalerweise das WAN zu einem zentralen Datencenter und tritt dann in das Internet aus. Dies geschieht häufig, um die Netzwerksicherheitsgeräte zu zentralisieren und dadurch die Gesamtkosten zu reduzieren.

Der Rücktransport des Datenverkehrs durch das WAN erhöht die Latenz und hat negative Auswirkungen auf die Qualität und die Benutzerfreundlichkeit. Da Microsoft Teams im großen globalen Netzwerk von Microsoft ausgeführt wird, gibt es oft einen Netzwerkpeering-Standort in der Nähe des Benutzers. Benutzer erzielen wahrscheinlich eine bessere Leistung, indem sie ihre Daten so schnell wie möglich aus einem lokalen Internetpunkt in der Nähe ihres Standorts heraus und in unser für VoIP optimiertes Netzwerk leiten. Bei einigen Arbeitsauslastungen werden DNS-Anforderungen verwendet, um den Datenverkehr an den nächstgelegenen Front-End-Server zu senden. In diesen Fällen ist es wichtig, dass bei Verwendung eines lokalen Ausgangspunkts auch lokale DNS-Auflösung genutzt wird.

Durch Optimieren des Netzwerkpfads zum globalen Netzwerk von Microsoft wird die Leistung verbessert und letztendlich die größtmögliche Benutzerfreundlichkeit erzielt. Weitere Details finden Sie im Blogbeitrag [Erzielen der besten Konnektivität und Leistung in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Wenn Sie optimal Real-Time Media in Microsoft-Teams verwenden möchten, müssen Sie die Netzwerken Anforderungen für Office 365 erfüllen. Weitere Informationen finden Sie unter [Medienqualität und Leistung des Netzwerks Konnektivität für Skype für Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Zwei definierenden Netzwerksegmente (Client Microsoft Edge) und Customer Kante Microsoft Edge müssen die folgenden Anforderungen erfüllen:

|**Wert** |**Client für Microsoft-Edge** |**Customer Edge zum Microsoft Rand** |
|---|---|---|
|**Wartezeit (unidirektional)** |< 50 ms |< 30 ms |
|**Wartezeit (Roundtripzeit oder Zeit)** |< 100 ms |< 60 ms |
|**Bursts von Paketverlusten** |<10 % Intervall 200 ms |<1 % Intervall 200 ms |
|**Paketverlust** |<1 % Intervall 15 s |<0.1% Intervall 15 s |
|**Die Kommunikation zwischen hinzukommen Jitter Paket** |<30 ms Intervall 15 s |<15 ms Intervall 15 s |
|**Paket neu anordnen** |<0.05% außerhalb der Reihenfolge Pakete |<0.01% außerhalb der Reihenfolge Pakete |

Um beide Netzwerksegmente zu testen, können Sie das [Tool zur Bewertung der Netzwerk](https://go.microsoft.com/fwlink/?linkid=855799)verwenden. Dieses Tool kann auf dem Client PC direkt und auf einem PC verbunden mit dem Kunden Netzwerkgrenze bereitgestellt werden. Das Tool umfasst begrenzte Dokumentation, aber eine tiefere Dokumentation entsprechend der Verwendung des Tools finden Sie hier: [Bereitschaft des Netzwerks](https://go.microsoft.com/fwlink/?linkid=855800). Diese Bereitschaft Netzwerk ausführen, können Sie Netzwerks auszuführenden Real-Time Media-Anwendungen wie Microsoft-Teams überprüfen.

> [!NOTE]
> Dies ist die gleiche Netzwerk Bereitschaft, die wir empfehlen von Kunden, die zum Bereitstellen von Skype für Business erfolgreich ausgeführt werden.

### <a name="vpn"></a>VPN

VPNs leisten vielen Organisationen wertvolle Dienste. Leider sind sie in der Regel nicht entwickelt und Real-Time Media-Unterstützung konfiguriert. Manche VPNs unterstützen möglicherweise UDP nicht. VPNs einführen auch eine zusätzliche Sicherheitsebene Verschlüsselung auf der Basis Mediendatenverkehr, die bereits verschlüsselt ist. Darüber hinaus Konnektivität mit dem Dienst Teams effiziente aufgrund haarstrich Verankern-Datenverkehr über ein VPN-Gerät möglicherweise nicht. Darüber hinaus sie unbedingt aus Sicht der Kapazität eignen sich nicht um die erwarteten Lasten aufzunehmen, die Teams erforderlich ist.

Es wird empfohlen, einen alternativen Pfad bereitzustellen, der das VPN für Teams-Datenverkehr umgeht. Dies wird auch als *Split-Tunnel VPN*bezeichnet. Split-tunneling bedeutet, dass Datenverkehr für Office 365 wird nicht das VPN durchlaufen jedoch direkt an den Office 365. Diese Änderung wirkt sich positiv auf die Qualität aus, bietet aber auch den sekundären Vorteil, dass die Last für die VPN-Geräte und das Netzwerk der Organisation reduziert wird.

Wenn Sie einen geteilten Tunnel implementieren möchten, erkundigen Sie sich bei Ihrem VPN-Anbieter nach den Konfigurationsdetails.

### <a name="wi-fi"></a>WLAN

Wi-Fi-Netzwerke sind nicht wie VPN unbedingt entwickelt oder Real-Time Media-Unterstützung konfiguriert. Planen oder optimieren, ist ein Wi-Fi-Netzwerk zur Unterstützung von Teams ein wichtiger Aspekt für eine hohe Qualität-Bereitstellung.

Es gibt mehrere Faktoren, die ins Spiel für ein WLAN Netzwerk optimieren:

- Implementieren Sie QoS oder Wi-Fi Multimedia (WMM), um sicherzustellen, dass Mediendatenverkehr gegenüber den WLAN-Netzwerken entsprechend priorisiert wird.

- Planung und Optimierung der Wi-Fi-Bereichen und Access zeigen Platzierung. Der Bereich mit 2,4 GHz möglicherweise eine angemessene wünschen, abhängig davon, wie Access Point bieten, jedoch Zugriffspunkte unterliegen häufig durch andere Consumer-Geräte, die in diesem Bereich verwendet werden. Der 5-GHz-Bereich ist aufgrund seiner Dichte besser für Echtzeitmedien geeignet, erfordert jedoch mehr Zugriffspunkte, um eine ausreichende Abdeckung zu erzielen. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.

- Wenn Dual-Band-Wi-Fi-Netzwerke bereitgestellt werden, sollten Sie die Steuerung Band implementieren. _Band Steuerung_ ist eine Technik implementiert Wi-Fi-Anbieter, Dual-Band-Clients für die Verwendung von 5 GHz-Bereich zu beeinflussen.

- Wenn Zugriffspunkte im gleichen Kanal zu nahe beieinander können dazu führen, dass Signal Überlappung und versehentlich konkurrieren, wodurch eine schlechte Erfahrung für den Benutzer. Stellen Sie sicher, dass Zugriffspunkte, die nebeneinander auf Kanäle sind, die sich nicht überlappen.

Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wir empfehlen Ihnen, sich bei Ihrem Anbieter nach konkreten Anleitungen zu erkundigen.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Firewall- und Anforderungen

Microsoft-Teams, wird die Verbindung zum Microsoft Online Services und Internetkonnektivität für diesen benötigt. Für Teams ordnungsgemäß funktioniert müssen Sie TCP-Ports 80 und 443 von den Clients an das Internet und UDP-Ports 3478 über 3481 von den Clients an das Internet öffnen. Die TCP-Ports werden verwendet, Verbindung mit webbasiertem Inhalt wie SharePoint Online, Exchange Online und die Dienste Teams Chat. Plug-ins und Connectors verbinden auch über diese TCP-Ports. Die vier UDP-Ports werden für Medien wie Audio- und Videofunktionen, um sicherzustellen, dass sie ordnungsgemäß flow verwendet.

Diese Ports öffnen ist für eine zuverlässige Teams Bereitstellung entscheidend. Diese Ports blockiert wird nicht unterstützt und wirkt sich auf die Medienqualität.

Wenn Ihre Organisation erfordert, dass Geben Sie die genauen IP-Adressbereiche und Domänen zu denen diese Ports geöffnet werden soll, können Sie die Ziel-IP-Adressbereiche und Domänen für diese Ports einschränken. Eine Liste der genauen Ports Protokolle und IP-Adressbereichen, finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Wenn Sie zum Einschränken der Ziel-IP-Adressbereiche und Domänen auswählen, müssen Sie sicherstellen, dass Sie die Liste der Ports und Bereiche Stand halten, da sie möglicherweise ändert. Sie können [diesen RSS-feed](https://go.microsoft.com/fwlink/p/?linkid=236301) aktualisiert werden, wenn Änderungen auftreten abonnieren. Es ist außerdem ratsam zu prüfen, ob alle Ports durch Ausführen der [Skype für Tool zur Bewertung der Business Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) in regelmäßigen Abständen geöffnet werden. Sie können die Funktionalität von diesem Tool im nächsten Abschnitt erkunden.

Im Falle eines Proxyservers bereitgestellt wird wird empfohlen, dass der Proxyserver für alle Teams-Dienste. Obwohl über einen Proxyserver arbeiten kann, ist es sehr wahrscheinlich, dass die Qualität gekürzt aufgrund des Mediums gezwungen TCP anstelle von UDP verwendet wird. Weitere Informationen zu Proxyservern und umgehen finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Zusätzliche Netzwerkaspekte

### <a name="external-name-resolution"></a>Externe namensauflösung

Stellen Sie sicher, dass alle Clientcomputer wird der Client Teams ausgeführt externe DNS-Abfragen zum Ermitteln der Dienste von Office 365 auflösen können.

### <a name="nat-pool-size"></a>NAT-Pool-Größe

Wenn Sie mehrere Benutzer und Geräte Access Office 365 mithilfe von (Network Address Translation, NAT) oder Port Address Translation (PAT), müssen Sie sicherstellen, dass nicht die Geräte hinter jeder öffentlich routingfähige IP-Adresse ausgeblendet unterstützte Anzahl nicht überschreiten.

Um dieses Risiko zu verringern, stellen Sie sicher, über ausreichend öffentliche IP-Adressen in der NAT-Pools zu verhindern, dass Port Erschöpfung zugewiesen sind. Port Erschöpfung bewirkt, dass interne Endbenutzer und Geräten, um Probleme mit der Vorderseite nach beim Verbinden mit Office 365-Dienste. Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Hinweise zur Intrusion Erkennung und Datenausführungsverhinderung

Achten Sie Ihre Umgebung eine von Eindringlingen und/oder System für Intrusionsprävention für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt hat, darauf, dass alle-Datenverkehr, der Office 365-URLs hat, als Ziel weißen Liste enthalten ist.

## <a name="test-the-network"></a>Testen des Netzwerks

Nach Abschluss der Vorbereitung der Planung und Netzwerk – einschließlich der Aktualisierung Bandbreite und Öffnen von Ports in der Firewall – testen Sie die Leistung Ihres Netzwerks. Die Ergebnisse dieser Tests wird ein besseres Verständnis der Netzwerk-Optimierung und-Wartung erforderlich für den Erfolg Ihrer Implementierung Teams zu zeichnen.

Sie können die [Skype für Tool zur Bewertung der Business Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) zu prüfen, ob Ihr Netzwerk für Teams bereit ist herunterladen. Das Tool bietet zwei Funktionen: sie können prüfen, ob alle die richtigen Ports geöffnet sein, und es für Netzwerk Hörvermögen testen kann.

Nachdem Sie herunterladen und installieren Sie das Tool, finden es Sie in c:\Programme\Gemeinsame Dateien (x86) \Microsoft Skype für Tool zur Bewertung der Business-Netzwerk. Ein ausführlicher Leitfaden für die Verwendung der Tools, Usage.docx, ist in diesem Verzeichnis enthalten.

### <a name="test-for-opened-ports"></a>Test für geöffnete ports

Öffnen Sie ein Eingabeaufforderungsfenster, und navigieren Sie zu dem Tool zur Bewertung der Netzwerk-Verzeichnis, indem Sie **cd c:\Programme\Gemeinsame Dateien (x86) \Microsoft Skype für Tool zur Bewertung der Business Netzwerk**eingeben. Starten Sie an der Befehlszeile den Test für geöffnete Ports durch Eingabe **networkassessmenttool.exe /connectivitycheck**

Nach dem Ausführen der Überprüfungen, das Tool wird die Meldung "Überprüfungen erfolgreich abgeschlossen" angezeigt oder Berichten über die Ports, die blockiert wurden. Generiert außerdem eine Datei namens Connectivity_results.txt, die die Ausgabe aus dem Tool enthält und speichert sie in der "UserProfile" %\\Anwendungsdaten\\lokale\\Microsoft Skype für Tool zur Bewertung der Business Netzwerk\\ Directory.

Es wird empfohlen, dass Sie die Prüfungen der Netzwerkkonnektivität in regelmäßigen Abständen um sicherzustellen, dass die Ports geöffnet worden sein und arbeiten ordnungsgemäß ausgeführt.

### <a name="test-for-network-impairments"></a>Test für Netzwerk Hörvermögen

Um die Benutzerzufriedenheit erhöhen, sollten Sie alle Hörvermögen in Ihrem Netzwerk einschränken. Die am häufigsten verwendeten Netzwerk Hörvermögen sind Verzögerung (Latenz), Paketverlust, und jitter:

- **Wartezeit:** Dies ist der Zeitaufwand für das ein IP-Paket von Punkt A nach Punkt B im Netzwerk erhalten. Diese Netzwerk Verteilung Verzögerung ist im Wesentlichen an physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit, einschließlich zusätzlichen Aufwand zwischen den verschiedenen Routern geschaltet gebunden. Wartezeit wird als unidirektionale oder Round-Trip Zeit gemessen.

- **Paketverlust**: Dies ist häufig definiert als Prozentsatz der Pakete, die in einem angegebenen Fenster Zeit verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, verloren Person Pakete mit fast keine Auswirkung auf Back Bursts von Verlusten, Ursache Audio vollständig Ausschneiden.

- **Kommunikation zwischen Paket hinzukommen Jitter oder einfach Jitter:** Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Die meisten modernen VoIP-Software, einschließlich Skype für Unternehmen, kann einige Ebenen der Jitter über Pufferung anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerken.

Die maximale Werte für diese Hörvermögen werden in [der Leistung für die Qualität und Netzwerk Konnektivität Media](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)beschrieben. Beim Testen der für diese Hörvermögen unterscheiden wir zwischen zwei separaten Segmenten:

- Der *Edge-Segment* ist das Segment, in dem sich Ihr Router befindet. Dies ist die am nächsten logischen Netzwerksegment mit dem Internet über die einzelnen Standorten verbunden. In den meisten Fällen ist dies der Verbindungspunkt des Routers oder möglicherweise ein Umkreisnetzwerk (auch als *DMZ*, *demilitarisierte Zone*und *überwachtes Subnetz*). Keine weiteren Datenverkehr, der Geräte außer dem Router wirkt sich auf sollte zwischen diesem Segment und dem Internet auftreten.

- Der *Client-Segment* ist die logische Netzwerksegment in dem sich die Clients befinden.

Sie sollten beide Segmente testen, mit dem Netzwerk Assessment-Tool. Testen das Segment, navigieren Sie zum Verzeichnis und **networkassessmenttool.exe** an der Eingabeaufforderung eingeben. Die Ergebnisse werden in eine Datei namens Results.tsv geschrieben, und Sie können sie die [Anforderungen](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) für jedes Segment vergleichen.

Beachten Sie, dass beide Segmente müssen die Anforderungen für eine hohe Qualität Bereitstellung erfüllen. Es wird empfohlen, dass Sie das Tool mehrere Male für eine Stunde ausführen, wenn Sie gerade einen guten Überblick die Leistung Ihres Netzwerks über erhalten möchten.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Netzwerk-Wartung

Wenn die Ergebnisse der Bandbreite planen, Port testen oder netzwerkanforderungen testen zeigt an, dass das aktuelle Netzwerk vor der Bereitstellung von Teams Remediation benötigt, können Sie dies auf verschiedene Arten ausführen:

- Für unzureichende Bandbreite ungehinderte Upgrade Verbindungen, damit dieser Datenverkehr zu Office 365 gesendet werden kann.

- Für blockierte Ports Firewallregeln ändern, und Testen Sie die Ports erneut.

- Führen Sie für die Netzwerk-Hörvermögen immer eine Ursachenanalyse.

Dienstqualität (QoS) kann auf müssen Hörvermögen durch Priorisierung und Trennen von Datenverkehr verwendet werden. Einige Organisationen entscheiden sich für das Bereitstellen von QoS zum überwinden Bandbreitenprobleme oder schränken Sie den Umfang der Datenverkehr fließt. Dadurch werden nicht zur Verbesserung der Qualität und wird zu neuen Problemen führen. Eine Ursachenanalyse sollte immer ausgeführt werden, wenn Netzwerk Hörvermögen Anforderungen überschreiten. QoS kann es sich um eine Lösung sein. Weitere Informationen finden Sie unter [Quality of Service in Microsoft-Teams](qos-in-teams.md).

>[!NOTE]
>Viele Netzwerke entwickeln sich im Lauf der Zeit weiter, sei es durch Upgrades, durch Erweiterung oder durch andere geschäftliche Anforderungen. Stellen Sie sicher, dass Sie über betriebliche Prozesse verfügen, mit denen diese Bereiche im Rahmen der Planung der Dienstverwaltung gewartet werden.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkt</td><td><ul><li>Wer wird für die Durchführung der richtigen Netzwerk Bewertung in allen Netzwerksegmenten und Organisation Speicherorte verantwortlich sein?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Bewertung detaillierte Netzwerk, um sicherzustellen, dass Ihr Netzwerk für die Bereitstellung von Microsoft-Teams bereit ist. Weitere Informationen finden Sie unter <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Bereitschaft des Netzwerks</a>.</li><li>Führen Sie basierend auf den Ergebnissen der Netzwerk-Bereitschaft für jedes Netzwerksegment Netzwerk Remediation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Die wichtigsten Vorteile

Dies sind die wichtigsten Vorteile aus diesem Handbuch. Du musst:

- Öffnen Sie TCP-Ports 80 und 443 ausgehend von Clients, auf denen Teams verwendet werden.

- Öffnen Sie UDP-Ports 3478 über 3481 ausgehend von Clients, auf denen Teams verwendet werden.

- Stellen Sie sicher, dass Sie genügend Bandbreite für die Bereitstellung von Teams anhand der [Planner Netzwerk](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)verfügen.

- Führen Sie das [Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) , und stellen Sie sicher, dass die in [der Leistung für die Qualität und Netzwerk Konnektivität Medien](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) aus der Edge-Segment und die Client-Segment beschriebenen Anforderungen erfüllt.

## <a name="related-topics"></a>Verwandte Themen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)
