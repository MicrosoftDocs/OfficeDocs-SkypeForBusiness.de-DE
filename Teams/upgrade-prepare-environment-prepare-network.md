---
title: Vorbereiten Ihres Netzwerks für Microsoft Teams| Port-Firewallanforderungen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Verwenden Sie diese Anleitung, um Ihr Netzwerk für die Bereitstellung und den Rollout von Microsoft Teams vorzubereiten.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d58613bc3455d5467e9e6c6589f73d498c6e1e3b
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706905"
---
# <a name="prepare-your-network-for-upgrading-to-teams"></a>Vorbereiten Ihres Netzwerks für das Upgrade auf Microsoft Teams

![Diagramm zum Upgrade von Fahrten mit Hervorhebung der technischen Bereitschaftsstufe](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der technischen Bereitschaftsstufe liegt")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Bevor Sie fortfahren, bestätigen Sie, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> In der folgenden Sitzung erfahren Sie mehr darüber, wie Teams Ihr Netzwerk nutzt und wie Sie für eine optimale Netzwerkkonnektivität sorgen können: [Teams-Netzwerkplanung](https://aka.ms/teams-networking)

Wenn Sie Audio, Video oder Besprechungen bereitstellen, können Sie einige zusätzliche Schritte Unternehmen, um Ihr Netzwerk für diese Funktionalität zu optimieren. Microsoft Teams verwendet Audio- und Videotechnologien (Codecs), die sich an die meisten Netzwerkbedingungen anpassen können, was sich positiv auf die Leistung auswirkt. Um eine optimale und gleichbleibende Leistung sicherzustellen, sollten Sie das Netzwerk für Microsoft Teams vorbereiten.

![Diagramm, in dem die drei Komponenten der Qualität beschrieben werden](media/evaluate-my-environment-image1.png "Diagramm, in dem die drei Komponenten der Qualität beschrieben sind und wie die Dienstverwaltung alle drei Komponenten überlappt. Mit einem Fokus auf das Netzwerk.")

## <a name="why-should-you-prepare-your-network"></a>Warum sollten Sie Ihr Netzwerk vorbereiten?

Bevor wir uns mit den erforderlichen Schritten befassen, ist es wichtig zu verstehen, was die Leistung von Teams beeinflussen kann, und dadurch das Glück und die Zufriedenheit des Benutzers. Es gibt im Wesentlichen drei Risikobereiche, die sich auf die Wahrnehmung der Netzwerkqualität durch die Benutzer auswirken:

- Unzureichende verfügbare Bandbreite

- Firewalls und Proxyblocker

- Netzwerkbeeinträchtigungen wie beispielsweise Jitter und Paketverlust

Mithilfe der unten beschriebenen Schritte können Sie ermitteln, ob Ihre Bereitstellung von einem dieser Faktoren betroffen sein könnte, und eine Lösung finden. Wenn Sie das Netzwerk nicht vorbereiten, führt dies wahrscheinlich zu unzufriedenen Benutzern und kostspieligen Ad-hoc-Korrekturen. Durch die Vorbereitung Ihres Netzwerks – und Ihrer Organisation – für Microsoft Teams können Sie Ihre Erfolgschancen deutlich erhöhen.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Bandbreitenplanung

Microsoft Teams bietet unabhängig von Ihren Netzwerkbedingungen optimale Funktionen für Audio, Video und Inhaltsfreigabe. Mit variablen Codecs können Medien in Umgebungen mit eingeschränkter Bandbreite mit minimalen Auswirkungen ausgehandelt werden. Wenn hingegen die Bandbreite kein Problem darstellt, kann die Benutzererfahrung qualitativ optimiert werden, bis hin zu einer Videoauflösung von 1080p, 30 fps für Video und 15fps für Inhalte sowie HiFi-Audio.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>Lokaler Internetausgang

Viele Netzwerke wurden für die Verwendung einer Hub-Spoke-Topologie entworfen. In dieser Topologie durchläuft der Internetdatenverkehr normalerweise das WAN zu einem zentralen Datencenter und tritt dann in das Internet aus. Dies geschieht häufig, um die Netzwerksicherheitsgeräte zu zentralisieren und dadurch die Gesamtkosten zu reduzieren.

Der Rücktransport des Datenverkehrs durch das WAN erhöht die Latenz und hat negative Auswirkungen auf die Qualität und die Benutzerfreundlichkeit. Da Microsoft Teams im umfangreichen globalen Microsoft-Netzwerk ausgeführt wird, gibt es häufig einen Netzwerk Peering-Standort in der Nähe des Benutzers. Benutzer erzielen wahrscheinlich eine bessere Leistung, indem sie ihre Daten so schnell wie möglich aus einem lokalen Internetpunkt in der Nähe ihres Standorts heraus und in unser für VoIP optimiertes Netzwerk leiten. Bei einigen Arbeitsauslastungen werden DNS-Anforderungen verwendet, um den Datenverkehr an den nächstgelegenen Front-End-Server zu senden. In solchen Fällen ist es wichtig, dass Sie bei Verwendung eines lokalen Ausgangspunkts mit der lokalen DNS-Auflösung gekoppelt sind.

Durch Optimieren des Netzwerkpfads zum globalen Microsoft-Netzwerk wird die Leistung verbessert und letztendlich die optimale Benutzererfahrung bereitgestellt. Weitere Details finden Sie im Blogbeitrag [Erzielen der besten Konnektivität und Leistung in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein. Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) müssen die folgenden Anforderungen erfüllen:

|**Wert** |**Vom Client zum Edge von Microsoft** |**Vom Kundenedge zum Edge von Microsoft** |
|---|---|---|
|**Latenz (unidirektional)** |< 50 ms |< 30 ms |
|**Latenz (Roundtripzeit oder RTT)** |< 100 ms |< 60 ms |
|**Burstverlust von Paketen** |< 10 % in einem Intervall von 200 ms |< 1 % in einem Intervall von 200 ms |
|**Paketverlust** |< 1 % in einem Intervall von 15 s |< 0,1 % in einem Intervall von 15 s |
|**Jitter zwischen der Ankunftszeit von Paketen** |< 30 ms in einem Intervall von 15 s |< 15 ms in einem Intervall von 15 s |
|**Neuanordnung von Paketen** |< 0,05 % Pakete in falscher Reihenfolge |< 0,01 % Pakete in falscher Reihenfolge |

Um beide Netzwerksegmente zu testen, können Sie das [Netzwerkbewertungstool](https://go.microsoft.com/fwlink/?linkid=855799) verwenden. Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden. Das Tool selbst enthält eine begrenzte Dokumentation, eine umfassendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800). Wenn Sie diese Netzwerk Bereitschaftsbewertung ausführen, können Sie die Bereitschaft Ihres Netzwerks zur Ausführung von Echt Zeit Medienanwendungen wie Microsoft Teams überprüfen.

> [!NOTE]
> Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung wir Kunden empfehlen, die eine erfolgreiche Bereitstellung von Skype for Business anstreben.

### <a name="vpn"></a>VPN

VPNs leisten vielen Organisationen wertvolle Dienste. Leider sind Sie in der Regel nicht für die Unterstützung von Echt Zeit Medien konzipiert oder konfiguriert. Manche VPNs unterstützen möglicherweise UDP nicht. VPNs führen auch eine zusätzliche Verschlüsselungsschicht über den bereits verschlüsselten Mediendatenverkehr ein. Zudem leidet möglicherweise aufgrund des Hairpinnings des Datenverkehrs durch ein VPN-Gerät die Effizienz der Konnektivität mit dem Microsoft Teams-Dienst. Darüber hinaus werden Sie nicht unbedingt aus einer Kapazitäts Perspektive entwickelt, um die erwarteten Lasten zu berücksichtigen, die von Teams benötigt werden.

Es wird empfohlen, für Teams-Datenverkehr einen alternativen Pfad bereitzustellen, der das VPN umgeht. Dies wird allgemein als *VPN mit geteiltem Tunnel* bezeichnet. Split-Tunneling bedeutet, dass der Datenverkehr für Office 365 das VPN nicht durchlaufen wird, sondern direkt zu Office 365 geht. Diese Änderung hat eine positive Auswirkung auf die Qualität, bietet aber auch den sekundären Vorteil, dass die Auslastung von den VPN-Geräten und dem Netzwerk der Organisation verringert wird.

Wenn Sie einen geteilten Tunnel implementieren möchten, erkundigen Sie sich bei Ihrem VPN-Anbieter nach den Konfigurationsdetails.

### <a name="wi-fi"></a>WLAN

Wie bei VPN sind WLAN-Netzwerke nicht unbedingt so konzipiert oder konfiguriert, dass Sie Echt Zeit Medien unterstützen. Die Planung oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Microsoft Teams ist bei einer Bereitstellung von hoher Qualität eine wichtige Überlegung.

Beim Optimieren eines WLAN-Netzwerks kommen verschiedene Faktoren zum Tragen:

- Implementieren Sie QoS oder Wi-Fi Multimedia (WMM), um sicherzustellen, dass Mediendatenverkehr gegenüber den WLAN-Netzwerken entsprechend priorisiert wird.

- Planen und optimieren Sie die WLAN-Bänder und die Platzierung der Zugriffspunkte. Der 2,4-GHz-Bereich bietet zwar möglicherweise je nach Platzierung des Zugriffspunkts eine angemessene Qualität, Zugriffspunkte werden jedoch oft durch andere Heimanwendergeräte beeinflusst, die im gleichen Bereich betrieben werden. Der 5-GHz-Bereich ist aufgrund seiner Dichte besser für Echtzeitmedien geeignet, erfordert jedoch mehr Zugriffspunkte, um eine ausreichende Abdeckung zu erzielen. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.

- Wenn Dual-Band-WLAN-Netzwerke bereitgestellt werden, ziehen Sie die Implementierung von Bandsteuerung in Betracht. Bei der _Bandsteuerung_ handelt es sich um eine Technik, die von WLAN-Anbietern implementiert wird, um Dual-Band-Clients zur Verwendung des 5-GHz-Bereichs zu veranlassen.

- Wenn Zugriffspunkte im gleichen Kanal zu nah beieinander positioniert sind, können sie Signalüberlappung verursachen und unbeabsichtigt in Wettstreit miteinander treten. Dies führt zu einer mangelhaften Benutzererfahrung. Stellen Sie sicher, dass sich die benachbarten Zugriffspunkte auf Kanälen befinden, die sich nicht überlappen.

Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wir empfehlen Ihnen, sich bei Ihrem Anbieter nach konkreten Anleitungen zu erkundigen.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Anforderungen an Firewalls und Proxys

Microsoft Teams stellt Verbindungen mit Microsoft Online Services her und benötigt dazu eine Internetverbindung. Damit Microsoft Teams richtig funktioniert, müssen Sie die TCP-Ports 80 und 443 sowie die UDP-Ports 3478 bis 3481 jeweils für ausgehende Verbindungen der Clients mit dem Internet öffnen. Die TCP-Ports werden für Verbindungen mit webbasierten Inhalten wie SharePoint Online, Exchange Online und den Microsoft Teams-Chatdiensten verwendet. Auch Plug-Ins und Connectors stellen Verbindungen über diese TCP-Ports her. Die vier UDP-Ports werden für Medien wie beispielsweise Audio und Video verwendet, um deren ordnungsgemäßen Fluss sicherzustellen.

Das Öffnen dieser Ports ist für eine zuverlässige Microsoft Teams-Bereitstellung zwingend notwendig. Das Blockieren dieser Ports wird nicht unterstützt und wirkt sich auf die Medienqualität aus.

Wenn es in Ihrer Organisation erforderlich ist, die genauen IP-Adressbereiche und Domänen anzugeben, für die diese Ports geöffnet werden sollen, können Sie die Ziel-IP-Bereiche und Zieldomänen für die Ports einschränken. Eine Liste der konkreten Ports, Protokolle und IP-Bereiche finden Sie unter [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Wenn Sie die Ziel-IP-Adressbereiche und Zieldomänen einschränken möchten, müssen Sie die Liste der Ports und Bereiche unbedingt stets auf dem aktuellen Stand halten, da sich diese Angaben ändern können. Sie können [diesen RSS-Feed](https://go.microsoft.com/fwlink/p/?linkid=236301) abonnieren, um sich über Änderungen auf dem Laufenden zu halten. Darüber hinaus empfiehlt es sich, zu testen, ob alle Ports geöffnet werden, indem Sie das [Skype for Business-Netzwerk Bewertungs Tool](https://www.microsoft.com/download/details.aspx?id=53885) regelmäßig ausführen. Weitere Informationen zu den Funktionen dieses Tools finden Sie im nächsten Abschnitt.

Falls ein Proxyserver bereitgestellt wird, empfehlen wir, den Proxyserver für alle Microsoft Teams-Dienste zu umgehen. Obwohl die Verwendung eines Proxys möglicherweise funktioniert, ist es sehr wahrscheinlich, dass die Qualität reduziert wird, da Medien gezwungen sind, TCP anstelle von UDP zu verwenden. Weitere Informationen zu Proxyservern und Umgehungen finden Sie unter [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Zusätzliche Überlegungen zu Netzwerken

### <a name="external-name-resolution"></a>Externe Namensauflösung

Stellen Sie sicher, dass alle Clientcomputer, auf denen der Microsoft Teams-Client ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.

### <a name="nat-pool-size"></a>Größe der NAT-Pools

Wenn mehrere Benutzer und Geräte auf Office 365 mithilfe der Netzwerkadressübersetzung (Network Address Translation, NAT) oder der Port Address Translation (Pat) zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Nummer nicht überschreiten.

Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern. Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Leitfaden zur Angriffserkennung und zum Eindringschutz

Wenn in Ihrer Umgebung ein Angriffserkennungs- und/oder Eindringschutzsystem als zusätzliche Sicherheitsstufe für ausgehende Verbindungen eingerichtet ist, stellen Sie sicher, dass Datenverkehr, dessen Ziel Office 365-URLs sind, in der Whitelist enthalten ist.

## <a name="test-the-network"></a>Testen des Netzwerks

Nachdem Sie Ihre Planung und Netzwerk Vorbereitung abgeschlossen haben, einschließlich der Aktualisierung der Bandbreite und Öffnen von Ports in der Firewall, sollten Sie die Leistung Ihres Netzwerks testen. Die Ergebnisse dieser Tests zeichnen ein klares Bild der für eine erfolgreiche Microsoft Teams-Implementierung erforderlichen Maßnahmen zur Netzwerkoptimierung oder -verbesserung.

Sie können das [Skype for Business-Netzwerkbewertungstool](https://www.microsoft.com/download/details.aspx?id=53885) herunterladen, um zu testen, ob Ihr Netzwerk für Microsoft Teams bereit ist. Das Tool bietet zwei Funktionen: Es kann zum einen testen, ob die richtigen Ports geöffnet sind, und zum anderen, ob Netzwerkbeeinträchtigungen vorliegen.

Wenn Sie das Tool heruntergeladen und installiert haben, finden Sie es unter „C:\Programme (x86)\Microsoft Skype for Business Network Assessment Tool“. Dieses Verzeichnis enthält außerdem ein detailliertes Handbuch zur Verwendung des Tools („Usage.docx“).

### <a name="test-for-opened-ports"></a>Testen auf geöffnete Ports

Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zum Verzeichnis des Netzwerkbewertungstools, indem Sie **cd C:\Programme (x86)\Microsoft Skype for Business Network Assessment Tool** eingeben. Starten Sie an der Eingabeaufforderung den Test auf geöffnete Ports, indem Sie **networkassessmenttool.exe /connectivitycheck** eingeben.

Nach dem Ausführen der Überprüfungen zeigt das Tool entweder die Meldung "Überprüfungen erfolgreich abgeschlossen" an oder meldet die blockierten Ports. Außerdem wird die Datei „Connectivity_results.txt“ generiert. Diese enthält die Ausgabe des Tools und wird im Verzeichnis „%userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\“ gespeichert.

Am besten führen Sie die Konnektivitätsüberprüfungen regelmäßig aus, um sicherzustellen, dass die Ports geöffnet sind und richtig funktionieren.

### <a name="test-for-network-impairments"></a>Testen auf Netzwerkbeeinträchtigungen

Sie sollten Beeinträchtigungen im Netzwerk begrenzen, um die Benutzerzufriedenheit zu erhöhen. Bei Netzwerkbeeinträchtigungen handelt es sich meist um Verzögerungen (Latenzen), Paketverluste und Jitter:

- **Latenz:** Diese Eigenschaft gibt an, wie lange ein IP-Paket im Netzwerk von Punkt A nach Punkt B unterwegs ist. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router. Die Latenz wird als unidirektionale Latenz oder Roundtripzeit gemessen.

- **Paketverlust:** Diese Eigenschaft wird oft als prozentualer Anteil der Pakete gemessen, die in einem bestimmten Zeitfenster verloren gegangen sind. Paketverluste wirken sich direkt auf die Audioqualität aus. Sie reichen vom Verlust einzelner kleiner Pakete, der fast keine Auswirkung hat, bis hin zu direkt aufeinander folgenden Burstverlusten, die zu Tonaussetzern führen.

- **Jitter zwischen der Ankunftszeit von Paketen oder einfach Jitter:** Dies ist die durchschnittliche Änderung bei der Verzögerung zwischen aufeinander folgenden Paketen. Die meisten modernen VoIP-Softwareprogramme, wie auch Skype for Business, können ein gewisses Maß an Jitter durch Pufferung ausgleichen. Erst wenn der Jitter die Pufferung übersteigt, bemerken die Teilnehmer die Auswirkungen.

Die Maximalwerte für diese Beeinträchtigungen werden unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) beschrieben. Beim Testen auf diese Beeinträchtigungen unterscheiden wir zwischen zwei separaten Segmenten:

- Das *Edgesegment* ist das Segment, in dem sich Ihr Router befindet. Dabei handelt es sich um das nächstgelegene logische Netzwerksegment, das an allen Ihren Standorten mit dem Internet verbunden ist. In den meisten Fällen ist dies der Verbindungspunkt des Routers oder möglicherweise ein Umkreisnetzwerk (auch bekannt als *DMZ*, *demilitarisierte Zone* und *überwachtes Subnetz*). Zwischen diesem Segment und dem Internet sollte kein weiterer Datenverkehr fließen, der sich auf andere Geräte als den Router auswirkt.

- Das *Clientsegment* ist das logische Netzwerksegment, in dem sich Ihre Clients befinden.

Sie sollten beide Segmente mit dem Netzwerkbewertungstool testen. Zum Testen eines Segments navigieren Sie zu dem Verzeichnis, und geben Sie an der Eingabeaufforderung die Zeichenfolge **networkassessmenttool.exe** ein. Die Ergebnisse werden in die Datei „Results.tsv“ geschrieben und können mit den [Anforderungen](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) an die einzelnen Segmente verglichen werden.

Beachten Sie, dass beide Segmente die Anforderungen für eine Bereitstellung von hoher Qualität erfüllen müssen. Wir empfehlen, dass Sie das Tool für eine Stunde direkt mehrmals ausführen, um einen guten Überblick über die Leistung Ihres Netzwerks zu erhalten.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Netzwerkverbesserung

Wenn aus den Ergebnissen der Bandbreitenplanung, der Porttests oder anderer Tests im Hinblick auf die Netzwerkanforderungen hervorgeht, dass das aktuelle Netzwerk vor der Bereitstellung von Microsoft Teams verbessert werden muss, haben Sie verschiedene Möglichkeiten:

- Bei unzureichender Bandbreite sollten Sie die Verbindungen aktualisieren, damit der Datenverkehr zu Office 365 ungehindert fließen kann.

- Bei blockierten Ports sollten Sie Firewallregeln ändern und die Ports dann erneut testen.

- Bei Netzwerkbeeinträchtigungen müssen Sie immer eine Ursachenanalyse durchführen.

Sie können Quality of Service (QoS) zur Behebung von Beeinträchtigungen verwenden, indem Sie den Datenverkehr priorisieren und trennen. Manche Organisationen stellen QoS bereit, um Bandbreitenprobleme zu bewältigen oder den Umfang des fließenden Datenverkehrs einzuschränken. Dadurch wird die Qualität nicht verbessert und es entstehen neue Probleme. Eine Ursachenanalyse sollte immer durchgeführt werden, wenn Netzwerkbeeinträchtigungen die Anforderungen überschreiten. QoS kann eine Lösung sein. Weitere Informationen finden Sie unter [Quality of Service in Microsoft Teams](qos-in-teams.md).

>[!NOTE]
>Viele Netzwerke entwickeln sich im Lauf der Zeit weiter, sei es durch Upgrades, durch Erweiterung oder durch andere geschäftliche Anforderungen. Stellen Sie sicher, dass Sie über betriebliche Prozesse verfügen, mit denen diese Bereiche im Rahmen der Planung der Dienstverwaltung gewartet werden.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul><li>Wer soll für die Ausführung ordnungsgemäßer Netzwerkbewertungen in allen Netzwerksegmenten und an allen Organisationsstandorten zuständig sein?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Sie können eine detaillierte Netzwerkbewertung ausführen, um sicherzustellen, dass Ihr Netzwerk für die Bereitstellung von Microsoft Teams bereit ist. </li><li>Nehmen Sie auf der Grundlage der Ergebnisse der Bewertung der Netzwerkbereitschaft für jedes Netzwerksegment eine Netzwerkverbesserung vor.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Wesentliche Punkte

Dies sind die wesentlichen Punkte dieser Anleitung. Sie müssen die folgenden Aufgaben ausführen:

- Öffnen Sie die TCP-Ports 80 und 443 für ausgehende Verbindungen von Clients, die Microsoft Teams verwenden sollen.

- Öffnen Sie die UDP-Ports 3478 bis 3481 für ausgehende Verbindungen von Clients, die Microsoft Teams verwenden sollen.

- Stellen Sie sicher, dass Sie über ausreichende Bandbreite für die Bereitstellung von Microsoft Teams verfügen.

- Führen Sie das [Netzwerkbewertungstool](https://www.microsoft.com/download/details.aspx?id=53885) aus, und stellen Sie sicher, dass die unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) beschriebenen Anforderungen sowohl im Edgesegment als auch im Clientsegment erfüllt sind.

## <a name="related-topics"></a>Verwandte Themen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)
