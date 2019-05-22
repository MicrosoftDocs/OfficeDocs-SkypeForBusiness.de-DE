---
title: Vorbereiten Ihres Netzwerks für Microsoft Teams |  Port Firewall-Anforderungen
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 5454c8d4a95a6a9d1d695f74497ccf5c022d062b
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344098"
---
![Phasen der Upgrade-Strategie, mit Schwerpunkt auf der technischen Bereitschaft](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Strategie, mit Schwerpunkt auf der technischen Bereitschaft")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams Ihr Netzwerk nutzen und wie Sie die optimale Netzwerkkonnektivität optimal planen: [Teams-Netzwerkplanung](https://aka.ms/teams-networking)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Vorbereiten Ihres Netzwerks für das Upgrade auf Teams

Wenn Sie Audio, Video oder Besprechungen bereitstellen, können Sie einige zusätzliche Schritte Unternehmen, um Ihr Netzwerk für diese Funktionalität zu optimieren. In Teams werden Audio-und Videotechnologien (Codecs) verwendet, die sich an die meisten Netzwerkbedingungen anpassen können und daher besser funktionieren. Um eine optimale und konsistente Leistung zu gewährleisten, sollten Sie Ihr Netzwerk für Teams vorbereiten.

![Diagramm, in dem die drei Komponenten der Qualität beschrieben sind und wie die Dienstverwaltung alle drei Komponenten überlappt] (media/evaluate-my-environment-image1.png "Diagramm, in dem die drei Komponenten der Qualität beschrieben sind und wie die Dienstverwaltung alle drei Komponenten überlappt. Mit einem Fokus auf das Netzwerk.")

## <a name="why-should-you-prepare-your-network"></a>Warum sollten Sie Ihr Netzwerk vorbereiten?

Bevor wir uns mit den erforderlichen Schritten befassen, ist es wichtig zu verstehen, was die Leistung von Teams beeinflussen kann, und dadurch das Glück und die Zufriedenheit des Benutzers. Drei wichtige Risikobereiche können sich darauf auswirken, wie Benutzer die Netzwerkqualität wahrnehmen:

- Unzureichende Bandbreite verfügbar

- Firewall-und Proxy-Blocker

- Netzwerkbeeinträchtigungen wie Jitter und Paketverlust

Mit den nachstehenden Schritten können Sie feststellen, ob Ihre Bereitstellung von einem dieser Faktoren beeinflusst werden kann, und Sie können Ihnen helfen, zu einer Lösung zu wechseln. Wenn Sie Ihr Netzwerk nicht vorbereiten, führt dies wahrscheinlich zu unzufriedenen Benutzern und kostspieligen Ad-hoc-Korrekturen. Indem Sie Ihr Netzwerk – und Ihre Organisation – für Teams vorbereiten, können Sie Ihre Erfolgschancen drastisch erhöhen.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Bandbreitenplanung

Microsoft Teams bietet Ihnen optimale Audio-, Video-und Inhaltsfreigabe Funktionen unabhängig von ihren Netzwerkbedingungen. Mit Variablen Codecs können Medien in Umgebungen mit begrenzter Bandbreite mit minimalen Auswirkungen ausgehandelt werden. Wenn die Bandbreite jedoch kein Problem darstellt, können die Erfahrungen für die Qualität optimiert werden, einschließlich einer Videoauflösung von bis zu 1080p, bis zu 30 bps für Video-und 15bps für Inhalte und HiFi-Audio.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>Lokaler Internetausgang

Viele Netzwerke wurden für die Verwendung einer Hub-Spoke-Topologie entworfen. In dieser Topologie durchläuft der Internetdatenverkehr normalerweise das WAN zu einem zentralen Datencenter und tritt dann in das Internet aus. Dies geschieht häufig, um die Netzwerksicherheitsgeräte zu zentralisieren und dadurch die Gesamtkosten zu reduzieren.

Der Rücktransport des Datenverkehrs durch das WAN erhöht die Latenz und hat negative Auswirkungen auf die Qualität und die Benutzerfreundlichkeit. Da Microsoft Teams im großen globalen Netzwerk von Microsoft ausgeführt wird, gibt es oft einen Netzwerkpeering-Standort in der Nähe des Benutzers. Benutzer erzielen wahrscheinlich eine bessere Leistung, indem sie ihre Daten so schnell wie möglich aus einem lokalen Internetpunkt in der Nähe ihres Standorts heraus und in unser für VoIP optimiertes Netzwerk leiten. Bei einigen Arbeitsauslastungen werden DNS-Anforderungen verwendet, um den Datenverkehr an den nächstgelegenen Front-End-Server zu senden. In diesen Fällen ist es wichtig, dass bei Verwendung eines lokalen Ausgangspunkts auch lokale DNS-Auflösung genutzt wird.

Durch Optimieren des Netzwerkpfads zum globalen Netzwerk von Microsoft wird die Leistung verbessert und letztendlich die größtmögliche Benutzerfreundlichkeit erzielt. Weitere Details finden Sie im Blogbeitrag [Erzielen der besten Konnektivität und Leistung in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Um eine optimale Nutzung von Echt Zeit Medien in Microsoft Teams zu erhalten, müssen Sie die Netzwerkanforderungen für Office 365 erfüllen. Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität für Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Die beiden definierenden Netzwerksegmente (Client zu Microsoft Edge und Customer Edge to Microsoft Edge) müssen die folgenden Anforderungen erfüllen:

|**Wert** |**Client zu Microsoft Edge** |**Kunden-Edge zu Microsoft Edge** |
|---|---|---|
|**Latenz (eine Möglichkeit)** |< 50 ms |< 30 ms |
|**Latenz (Roundtrip-Zeit oder RTT)** |< 100 MS |< 60 ms |
|**Burst-Paketverlust** |<10% während eines beliebigen 200-MS-Intervalls |<1% während eines beliebigen 200-MS-Intervalls |
|**Paketverlust** |<1% während eines 15-Sekunden-Intervalls |_lt_ 0,1% während eines 15-Sekunden-Intervalls |
|**Paket Inter-arrival Jitter** |<30 MS während eines 15-Sekunden-Intervalls |<15 MS während eines 15-Sekunden-Intervalls |
|**Paket Reihenfolge** |_lt_ 0,05% Pakete außerhalb der Reihenfolge |_lt_ 0,01% Pakete außerhalb der Reihenfolge |

Zum Testen beider Netzwerksegmente können Sie das [Tool Netzwerkbewertung](https://go.microsoft.com/fwlink/?linkid=855799)verwenden. Dieses Tool kann sowohl auf dem Client-PC direkt als auch auf einem PC bereitgestellt werden, der mit dem Kundennetzwerk-Edge verbunden ist. Das Tool enthält eine begrenzte Dokumentation, aber eine umfassendere Dokumentation rund um die Verwendung des Tools finden Sie hier: [Netzwerk Bereitschaftsbewertung](https://go.microsoft.com/fwlink/?linkid=855800). Wenn Sie diese Netzwerk Bereitschaftsbewertung ausführen, können Sie die Bereitschaft Ihres Netzwerks zur Ausführung von Echt Zeit Medienanwendungen wie Microsoft Teams überprüfen.

> [!NOTE]
> Hierbei handelt es sich um die gleiche Netzwerk Bereitschaftsbewertung, die von Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.

### <a name="vpn"></a>VPN

VPNs leisten vielen Organisationen wertvolle Dienste. Leider sind Sie in der Regel nicht für die Unterstützung von Echt Zeit Medien konzipiert oder konfiguriert. Manche VPNs unterstützen möglicherweise UDP nicht. VPNs führen auch eine zusätzliche Verschlüsselungsschicht über den bereits verschlüsselten Mediendatenverkehr ein. Darüber hinaus ist die Konnektivität mit dem Team Dienst möglicherweise aufgrund des Haar befestigenden Datenverkehrs über ein VPN-Gerät nicht effizient. Darüber hinaus werden Sie nicht unbedingt aus einer Kapazitäts Perspektive entwickelt, um die erwarteten Lasten zu berücksichtigen, die von Teams benötigt werden.

Es wird empfohlen, einen alternativen Pfad bereitzustellen, der das VPN für Teams-Datenverkehr umgeht. Dies wird gemeinhin als " *Split-Tunnel-VPN*" bezeichnet. Split-Tunneling bedeutet, dass der Datenverkehr für Office 365 das VPN nicht durchlaufen wird, sondern direkt zu Office 365 geht. Diese Änderung wirkt sich positiv auf die Qualität aus, bietet aber auch den sekundären Vorteil, dass die Last für die VPN-Geräte und das Netzwerk der Organisation reduziert wird.

Wenn Sie einen geteilten Tunnel implementieren möchten, erkundigen Sie sich bei Ihrem VPN-Anbieter nach den Konfigurationsdetails.

### <a name="wi-fi"></a>WLAN

Wie bei VPN sind WLAN-Netzwerke nicht unbedingt so konzipiert oder konfiguriert, dass Sie Echt Zeit Medien unterstützen. Die Planung oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Teams ist eine wichtige Überlegung für eine hochwertige Bereitstellung.

Es gibt mehrere Faktoren, die bei der Optimierung eines Wi-Fi-Netzwerks zum Tragen kommen:

- Implementieren Sie QoS oder Wi-Fi Multimedia (WMM), um sicherzustellen, dass Mediendatenverkehr gegenüber den WLAN-Netzwerken entsprechend priorisiert wird.

- Planen und Optimieren der Wi-Fi-Bänder und der Zugriffspunkt Platzierung Der 2,4-GHz-Bereich bietet je nach Position des Zugriffspunkts möglicherweise eine angemessene Funktionalität, aber Zugriffspunkte werden häufig von anderen Consumer-Geräten betroffen, die in diesem Bereich arbeiten. Der 5-GHz-Bereich ist aufgrund seiner Dichte besser für Echtzeitmedien geeignet, erfordert jedoch mehr Zugriffspunkte, um eine ausreichende Abdeckung zu erzielen. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.

- Wenn Dual-Band-Wi-Fi-Netzwerke bereitgestellt werden, sollten Sie die Bandsteuerung implementieren. _Band Lenkung_ ist eine Technik, die von WLAN-Anbietern implementiert wird, um die Nutzung des 5-GHz-Bereichs für Dual-Band-Clients zu beeinflussen.

- Wenn Zugriffspunkte desselben Kanals zu eng verbunden sind, können Sie zu einer Signal Überlappung führen und unbeabsichtigt konkurrieren, was zu einem schlechten Nutzererlebnis führt. Stellen Sie sicher, dass sich die benachbarten Zugriffspunkte auf Kanälen befinden, die sich nicht überlappen.

Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wir empfehlen Ihnen, sich bei Ihrem Anbieter nach konkreten Anleitungen zu erkundigen.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Firewall-und Proxyanforderungen

Microsoft Teams stellt eine Verbindung mit Microsoft Online Services her und benötigt dazu eine Internetverbindung. Damit Teams ordnungsgemäß funktionieren, müssen Sie die TCP-Ports 80 und 443 von den Clients im Internet und UDP-Ports 3478 bis 3481 von den Clients zum Internet öffnen. Die TCP-Ports werden verwendet, um eine Verbindung mit webbasierten Inhalten wie SharePoint Online, Exchange Online und den Team-Chat Diensten herzustellen. Plug-ins und Connectors können auch über diese TCP-Anschlüsse verbunden werden. Die vier UDP-Ports werden für Medien wie Audio und Video verwendet, um sicherzustellen, dass Sie ordnungsgemäß fließen.

Das Öffnen dieser Ports ist für eine zuverlässige Teams-Bereitstellung unerlässlich. Das Blockieren dieser Ports wird nicht unterstützt und hat Auswirkungen auf die Medienqualität.

Wenn Ihre Organisation erfordert, dass Sie die genauen IP-Adressbereiche und Domänen angeben, für die diese Ports geöffnet werden sollen, können Sie die Ziel-IP-Bereiche und-Domänen für diese Ports einschränken. Eine Liste der genauen Ports, Protokolle und IP-Bereiche finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Wenn Sie die Ziel-IP-Adressbereiche und-Domänen einschränken möchten, müssen Sie sicherstellen, dass Sie die Liste der Ports und Bereiche auf dem neuesten Stand halten, da Sie sich möglicherweise ändern. Sie können [diesen RSS-Feed](https://go.microsoft.com/fwlink/p/?linkid=236301) abonnieren, um beim Auftreten von Änderungen aktualisiert zu werden. Darüber hinaus empfiehlt es sich, zu testen, ob alle Ports geöffnet werden, indem Sie das [Skype for Business-Netzwerk Bewertungs Tool](https://www.microsoft.com/download/details.aspx?id=53885) regelmäßig ausführen. Weitere Informationen zu den Funktionen dieses Tools finden Sie im nächsten Abschnitt.

Für den Fall, dass ein Proxy Server bereitgestellt wird, empfehlen wir, den Proxy Server für alle Team Dienste zu umgehen. Obwohl die Verwendung eines Proxys möglicherweise funktioniert, ist es sehr wahrscheinlich, dass die Qualität reduziert wird, da Medien gezwungen sind, TCP anstelle von UDP zu verwenden. Weitere Informationen zu Proxyservern und zur Umgehung finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Zusätzliche Netzwerküberlegungen

### <a name="external-name-resolution"></a>Auflösung externer Namen

Stellen Sie sicher, dass alle Clientcomputer, auf denen der Team Client ausgeführt wird, externe DNS-Abfragen beheben können, um die von Office 365 bereitgestellten Dienste zu ermitteln.

### <a name="nat-pool-size"></a>Größe des NAT-Pools

Wenn mehrere Benutzer und Geräte auf Office 365 mithilfe der Netzwerkadressübersetzung (Network Address Translation, NAT) oder der Port Address Translation (Pat) zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Nummer nicht überschreiten.

Um dieses Risiko zu verringern, stellen Sie sicher, dass den NAT-Pools angemessene öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern. Die Port Erschöpfung führt zu internen Endbenutzern und Geräten, die Probleme beim Herstellen einer Verbindung mit den Office 365-Diensten verursachen. Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Leitfaden zur Intrusionserkennung und-Prävention

Wenn in Ihrer Umgebung ein Intrusion Detection-System und/oder ein Intrusion Prevention-System für eine zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt wird, stellen Sie sicher, dass jeder Datenverkehr, der Office 365-URLs als Ziel hat, in Whitelist steht.

## <a name="test-the-network"></a>Testen des Netzwerks

Nachdem Sie Ihre Planung und Netzwerk Vorbereitung abgeschlossen haben, einschließlich der Aktualisierung der Bandbreite und Öffnen von Ports in der Firewall, sollten Sie die Leistung Ihres Netzwerks testen. Die Ergebnisse dieser Tests zeichnen ein klareres Bild von Netzwerkoptimierungen oder-Behebungen, die für den Erfolg Ihrer Teams-Implementierung erforderlich sind.

Sie können das [Skype for Business-Netzwerk Bewertungs Tool](https://www.microsoft.com/download/details.aspx?id=53885) herunterladen, um zu testen, ob Ihr Netzwerk für Teams bereit ist. Das Tool bietet zwei Funktionen: Es kann testen, ob alle richtigen Ports geöffnet wurden, und es kann auf Netzwerkbeeinträchtigungen getestet werden.

Nachdem Sie das Tool heruntergeladen und installiert haben, können Sie es in C:\Program Files (x86) \Microsoft Skype for Business Network Assessment Tool finden. Eine ausführliche Anleitung zur Verwendung des Tools, Verwendung. docx, ist in diesem Verzeichnis enthalten.

### <a name="test-for-opened-ports"></a>Testen auf geöffnete Ports

Öffnen Sie ein Eingabeaufforderungsfenster, und navigieren Sie zum Verzeichnis des Netzwerk Beurteilungs Tools, indem Sie das **Tool CD C:\Program Files (x86) \Microsoft Skype for Business-Netzwerkbewertung**eingeben. Starten Sie an der Eingabeaufforderung den Test für geöffnete Ports, indem Sie **networkassessmenttool. exe eingeben/connectivitycheck**

Nach dem Ausführen der Überprüfungen zeigt das Tool entweder die Meldung "Überprüfungen erfolgreich abgeschlossen" an oder meldet die blockierten Ports. Außerdem wird eine Datei mit dem Namen "Connectivity_results. txt" generiert, die die Ausgabe des Tools enthält und im Verzeichnis "%\\User\\profile\\% AppData Local Microsoft Skype for Business\\ Network Assessment Tool" gespeichert ist.

Wir empfehlen, dass Sie die Verbindungs Überprüfungen regelmäßig ausführen, um sicherzustellen, dass die Ports geöffnet wurden und ordnungsgemäß funktionieren.

### <a name="test-for-network-impairments"></a>Testen auf Netzwerkbeeinträchtigungen

Um die Nutzerzufriedenheit zu erhöhen, sollten Sie alle Beeinträchtigungen in Ihrem Netzwerk einschränken. Die häufigsten Netzwerkbeeinträchtigungen sind Verzögerung (Latenz), Paketverlust und Jitter:

- **Latenz:** Dies ist die Zeit, die erforderlich ist, um ein IP-Paket von Punkt a nach Punkt B im Netzwerk abzurufen. Diese Verzögerung der Netzwerk Propagierung ist im Wesentlichen an den physikalischen Abstand zwischen den beiden Punkten und der Lichtgeschwindigkeit gebunden, einschließlich des zusätzlichen Overhead, der von den verschiedenen Routern dazwischen genommen wird. Latenz wird als unidirektionale oder Roundtrip-Zeit gemessen.

- **Paketverlust**: Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen auf Burst Verluste haben, die dazu führen, dass Audiodaten vollständig ausgeschnitten werden.

- **Zwischen Paket-Ankunfts Jitter oder einfach Jitter:** Dies ist die durchschnittliche Verzögerungs Änderung zwischen aufeinanderfolgenden Paketen. Die meisten modernen VoIP-Software, einschließlich Skype for Business, kann sich durch Pufferung an einige Ebenen des Jitters anpassen. Dies ist nur der Fall, wenn der Jitter die Pufferzeit überschreitet, die ein Teilnehmer auf die Effekte von Jitter hinweist.

Die Höchstwerte für diese Beeinträchtigungen werden unter [Medienqualität und Leistung der Netzwerkkonnektivität](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)beschrieben. Beim Testen dieser Beeinträchtigungen unterscheiden wir zwischen zwei getrennten Segmenten:

- Das *Edge-Segment* ist das Segment, in dem der Router lebt. Hierbei handelt es sich um das nächstgelegene logische Netzwerksegment, das an jedem Standort mit dem Internet verbunden ist. In den meisten Fällen handelt es sich hierbei um den Verbindungspunkt des Routers oder möglicherweise um ein Umkreisnetzwerk (auch bekannt als *DMZ*, demilitarisierte *Zone*und abgeschirmtes *Subnetz*). Kein weiterer Datenverkehr, der andere Geräte als den Router betrifft, sollte zwischen diesem Segment und dem Internet erfolgen.

- Das *Client Segment* ist das logische Netzwerksegment, in dem sich Ihre Clients befinden.

Sie sollten beide Segmente mithilfe des Tools für die Netzwerkbewertung testen. Navigieren Sie zum Testen des Segments zu dem Verzeichnis, und geben Sie **networkassessmenttool. exe** an der Eingabeaufforderung ein. Die Ergebnisse werden in eine Datei mit dem Namen results. TSV geschrieben, und Sie können Sie mit den [Anforderungen](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) für jedes Segment vergleichen.

Beachten Sie, dass beide Segmente die Anforderungen für eine hochwertige Bereitstellung erfüllen müssen. Wir empfehlen, dass Sie das Tool für eine Stunde direkt mehrmals ausführen, um einen guten Überblick über die Leistung Ihres Netzwerks zu erhalten.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Netzwerk Sanierung

Wenn die Ergebnisse der Bandbreitenplanung, Port Tests oder Netzwerk anforderungstests zeigen, dass Ihr aktuelles Netzwerk vor der Bereitstellung von Teams eine Korrektur erfordert, können Sie dies auf verschiedene Arten erreichen:

- Für unzureichende Bandbreite aktualisieren Sie Verbindungen, damit der Datenverkehr zu Office 365 ungehindert fließen kann.

- Für blockierte Ports ändern Sie die Firewall-Regeln und testen Sie die Ports erneut.

- Führen Sie bei Netzwerkbeeinträchtigungen immer eine Ursachenanalyse durch.

Quality of Service (QoS) kann verwendet werden, um Beeinträchtigungen zu bekämpfen, indem der Datenverkehr priorisiert und getrennt wird. Einige Unternehmen entscheiden sich für die Bereitstellung von QoS zur Überwindung von Bandbreitenproblemen oder zum Einschränken der Datenströme. Dadurch wird die Qualität nicht verbessert und es entstehen neue Probleme. Es sollte immer eine Ursachenanalyse durchgeführt werden, wenn Netzwerkbeeinträchtigungen die Anforderungen überschreiten. QoS kann eine Lösung sein. Weitere Informationen finden Sie unter [Quality of Service in Microsoft Teams](qos-in-teams.md).

>[!NOTE]
>Viele Netzwerke entwickeln sich im Lauf der Zeit weiter, sei es durch Upgrades, durch Erweiterung oder durch andere geschäftliche Anforderungen. Stellen Sie sicher, dass Sie über betriebliche Prozesse verfügen, mit denen diese Bereiche im Rahmen der Planung der Dienstverwaltung gewartet werden.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul><li>Wer ist für die ordnungsgemäße Netzwerk Beurteilung über alle Netzwerksegmente und Organisationsstandorte verantwortlich?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Sie können eine detaillierte Netzwerkbewertung durchführen, um sicherzustellen, dass Ihr Netzwerk für Ihre Microsoft Teams-Bereitstellung bereit ist. Weitere Informationen finden Sie unter <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Netzwerk Bereitschaftsbewertung</a>.</li><li>Führen Sie die Netzwerk Bereinigung basierend auf den Ergebnissen der Netzwerk Readiness-Bewertung für jedes Netzwerksegment durch.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Wichtige Imbissbuden

Dies sind die wichtigsten Hinweise aus dieser Anleitung. Du musst:

- Öffnen Sie die TCP-Ports 80 und 443, die von Clients ausgehenden, die Teams verwenden werden.

- Öffnen Sie die UDP-Ports 3478 bis 3481, die von Clients, die Teams verwenden, abgehenden werden.

- Stellen Sie sicher, dass genügend Bandbreite für die Bereitstellung von Teams vorhanden ist, indem Sie den [Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)ausfüllen.

- Führen Sie das Tool für die [Netzwerkbewertung](https://www.microsoft.com/download/details.aspx?id=53885) aus, und stellen Sie sicher, dass Sie die Anforderungen unter [Medienqualität und Netzwerk Verbindungsleistung](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) sowohl im Edge-Segment als auch im Client Segment erfüllen.

## <a name="related-topics"></a>Verwandte Themen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)
